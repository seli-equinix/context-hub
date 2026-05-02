---
name: package
description: "Salt package guide for Python infrastructure automation, master/minion setup, states, and Python API usage"
metadata:
  languages: "python"
  versions: "3007.13"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "salt,python,configuration-management,orchestration,remote-execution,states,client,LocalClient,cmd,Version-Sensitive,NaclImporter,create_module,exec_module,find_module,extract_masters,is_non_string_iterable,is_non_string_sequence,parse_hostname,ArgumentValueError,pack,AuthenticationError,AuthorizationError,CheckError,CodePageError,CommandExecutionError,CommandNotFoundError,EauthAuthenticationError,FileLockError,FileserverConfigError,GitLockError,GitRemoteError,InvalidConfigError,InvalidEntityError,InvalidKeyError,LoaderError,LoggingRuntimeError,MasterExit,MinionError,MissingSmb,NotImplemented,NxosCliError,NxosClientError,NxosError,NxosRequestNotSupported,PkgParseError,PublishError,SaltCacheError,SaltClientError,SaltClientTimeout,SaltCloudConfigError,SaltCloudException,SaltCloudExecutionFailure,SaltCloudExecutionTimeout,SaltCloudNotFound,SaltCloudPasswordError,SaltCloudSystemExit,SaltConfigurationError,SaltDaemonNotRunning,SaltDeserializationError,SaltException,SaltInvocationError,SaltMasterError,SaltMasterUnresolvableError,SaltNoMinionsFound,SaltRenderError,SaltReqTimeoutError,SaltRunnerError,SaltSyndicMasterError,SaltSystemExit,SaltValidationError,SaltWheelError,TemplateError,TimedProcTimeoutError,TimeoutError,TokenAuthenticationError,UnsupportedAlgorithm,VMwareApiError,VMwareConnectionError,VMwareFileNotFoundError,VMwareMultipleObjectsError,VMwareNotFoundError,VMwareObjectExistsError,VMwareObjectNotFoundError,VMwareObjectRetrievalError,VMwarePowerOnError,VMwareRuntimeError,VMwareSaltError,VMwareSystemError,VMwareVmCreationError,VMwareVmRegisterError,get_error_message,execute,allow_missing_func,get_mro,mk_awaitable,mk_coroutine,mk_gen,old_style_mro,patch,Distribution,at,discover,from_name,locate_file,read_text,DistributionFinder,find_distributions,invalidate_caches,EntryPoint,load,FastPath,children,joinpath,search,zip_children,FileHash,MetadataPathFinder,find_spec,NullFinder,PackageMetadata,get_all,PackageNotFoundError,PackagePath,as_posix,as_uri,full_match,is_absolute,is_relative_to,is_reserved,locate,match,read_binary,relative_to,with_name"
---

# salt — package

Salt package

## Install

```bash
pip install salt
```

## Imports

```python
import salt
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `NaclImporter` | Class | Import hook to force PyNaCl to perform dlopen on libsodium with the RTLD_DEEPBI… |
| `create_module` | Method |  |
| `exec_module` | Method |  |
| `find_module` | Method |  |
| `extract_masters` | Function | Parses opts and generates a list of master (host,port) addresses. By default lo… |
| `is_non_string_iterable` | Function | Returns True if obj is non-string iterable, False otherwise  Future proof way t… |
| `is_non_string_sequence` | Function | Returns True if obj is non-string sequence, False otherwise  Future proof way t… |
| `parse_hostname` | Function | Parse hostname string and return a tuple of (host, port) If port missing in hos… |
| `ArgumentValueError` | Class | Used when an invalid argument was passed to a command execution |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `AuthenticationError` | Class | If sha256 signature fails during decryption |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `AuthorizationError` | Class | Thrown when runner or wheel execution fails due to permissions |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `CheckError` | Class | Used when a check fails |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `CodePageError` | Class | Raised when an error ocurs while getting or setting the windows code page |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `CommandExecutionError` | Class | Used when a module runs a command which returns an error and wants to show the… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `CommandNotFoundError` | Class | Used in modules or grains when a required binary is not available |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `EauthAuthenticationError` | Class | Thrown when eauth authentication fails |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `FileLockError` | Class | Used when an error occurs obtaining a file lock |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `FileserverConfigError` | Class | Used when invalid fileserver settings are detected |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `GitLockError` | Class | Raised when an uncaught error occurs in the midst of obtaining an update/checko… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `GitRemoteError` | Class | Used by GitFS to denote a problem with the existence of the "origin" remote or… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `InvalidConfigError` | Class | Used when the config is invalid |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `InvalidEntityError` | Class | Used when an entity fails validation |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `InvalidKeyError` | Class | Raised when we encounter an invalid RSA key. |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `LoaderError` | Class | Problems loading the right renderer |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `LoggingRuntimeError` | Class | Raised when we encounter an error while logging |
| `MasterExit` | Class | Rise when the master exits |
| `MinionError` | Class | Minion problems reading uris such as salt:// or http:// |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `MissingSmb` | Class | Raised when no smb library is found. |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `NotImplemented` | Class | Used when a module runs a command which returns an error and wants to show the… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `NxosCliError` | Class | NX-OS Cli Error raised when Cli command rejected by the NX-OS device |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `NxosClientError` | Class | NX-OS Client Error raised for problems connecting to the NX-OS device |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `NxosError` | Class | NX-OS Base Exception class |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `NxosRequestNotSupported` | Class | Raised for unsupported client requests |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `PkgParseError` | Class | Used when of the pkg modules cannot correctly parse the output from the CLI too… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `PublishError` | Class | Problems encountered when trying to publish a command |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltCacheError` | Class | Thrown when a problem was encountered trying to read or write from the salt cac… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltClientError` | Class | Problem reading the master root key |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltClientTimeout` | Class | Thrown when a job sent through one of the Client interfaces times out  Takes th… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltCloudConfigError` | Class | Raised when a configuration setting is not found and should exist. |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltCloudException` | Class | Generic Salt Cloud Exception |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltCloudExecutionFailure` | Class | Raised when too much failures have occurred while querying/waiting for data. |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltCloudExecutionTimeout` | Class | Raised when too much time has passed while querying/waiting for data. |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltCloudNotFound` | Class | Raised when some cloud provider function cannot find what's being searched. |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltCloudPasswordError` | Class | Raise when virtual terminal password input failed |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltCloudSystemExit` | Class | This exception is raised when the execution should be stopped. |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltConfigurationError` | Class | Configuration error |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltDaemonNotRunning` | Class | Throw when a running master/minion/syndic is not running but is needed to perfo… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltDeserializationError` | Class | Thrown when salt cannot deserialize data. |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltException` | Class | Base exception class; all Salt-specific exceptions should subclass this |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltInvocationError` | Class | Used when the wrong number of arguments are sent to modules or invalid argument… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltMasterError` | Class | Problem reading the master root key |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltMasterUnresolvableError` | Class | Problem resolving the name of the Salt master |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltNoMinionsFound` | Class | An attempt to retrieve a list of minions failed |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltRenderError` | Class | Used when a renderer needs to raise an explicit error. If a line number and buf… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltReqTimeoutError` | Class | Thrown when a salt master request call fails to return within the timeout |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltRunnerError` | Class | Problem in runner |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltSyndicMasterError` | Class | Problem while proxying a request in the syndication master |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltSystemExit` | Class | This exception is raised when an unsolvable problem is found. There's nothing e… |
| `SaltValidationError` | Class | Thrown when a value fails validation |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `SaltWheelError` | Class | Problem in wheel |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `TemplateError` | Class | Used when a custom error is triggered in a template |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `TimedProcTimeoutError` | Class | Thrown when a timed subprocess does not terminate within the timeout, or if the… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `TimeoutError` | Class | Thrown when an opration cannot be completet within a given time limit. |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `TokenAuthenticationError` | Class | Thrown when token authentication fails |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `UnsupportedAlgorithm` | Class | Thrown when a requested encryption or signing algorithm is un-supported. |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareApiError` | Class | Used when representing a generic VMware API error |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareConnectionError` | Class | Used when the client fails to connect to a either a VMware vCenter server or to… |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareFileNotFoundError` | Class | Used when representing a generic VMware error if a file not found |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareMultipleObjectsError` | Class | Used when multiple objects were retrieved (and one was expected) |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareNotFoundError` | Class | Used when a VMware object was not found |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareObjectExistsError` | Class | Used when a VMware object already exists |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareObjectNotFoundError` | Class | Used when a VMware object was not found |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareObjectRetrievalError` | Class | Used when a VMware object cannot be retrieved |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwarePowerOnError` | Class | Used when error occurred during power on |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareRuntimeError` | Class | Used when a runtime error is encountered when communicating with the vCenter |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareSaltError` | Class | Used when a VMware object cannot be retrieved |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareSystemError` | Class | Used when representing a generic VMware system error |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareVmCreationError` | Class | Used when a configuration parameter is incorrect |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `VMwareVmRegisterError` | Class | Used when a configuration parameter is incorrect |
| `pack` | Method | Pack this exception into a serializable dictionary that is safe for transport v… |
| `get_error_message` | Function | Get human readable message from Python Exception |
| `execute` | Function | Directly calls the given function with arguments |
| `allow_missing_func` | Function | Allow all calls to be passed through to docker container.  The docker call will… |
| `execute` | Function | Directly calls the given function with arguments |
| `execute` | Function | Splay a salt function call execution time across minions over a number of secon… |
| `get_mro` | Function |  |
| `mk_awaitable` | Function |  |
| `mk_coroutine` | Function |  |
| `mk_gen` | Function |  |
| `old_style_mro` | Function |  |
| `patch` | Function | Main entry point for patching the ``collections.abc`` and ``inspect`` standard… |
| `Distribution` | Class | A Python distribution package. |
| `at` | Method | Return a Distribution for the indicated metadata path  :param path: a string or… |
| `discover` | Method | Return an iterable of Distribution objects for all packages.  Pass a ``context`… |
| `from_name` | Method | Return the Distribution for the given package name.  :param name: The name of t… |
| `locate_file` | Method | Given a path to a file in this distribution, return a path to it. |
| `read_text` | Method | Attempt to load metadata file given by the name.  :param filename: The name of… |
| `DistributionFinder` | Class | A MetaPathFinder capable of discovering installed distributions. |
| `find_distributions` | Method | Find distributions.  Return an iterable of all Distribution instances capable o… |
| `invalidate_caches` | Method | An optional method for clearing the finder's cache, if any. This method is used… |
| `EntryPoint` | Class | An entry point as defined by Python packaging conventions.  See `the packaging… |
| `load` | Method | Load the entry point from its definition. If only a module is indicated by the… |
| `FastPath` | Class | Micro-optimized class for searching a path for children. |
| `children` | Method |  |
| `joinpath` | Method |  |
| `search` | Method |  |
| `zip_children` | Method |  |
| `FileHash` | Class |  |
| `MetadataPathFinder` | Class | A degenerate finder for distribution packages on the file system.  This finder… |
| `find_distributions` | Method | Find distributions.  Return an iterable of all Distribution instances capable o… |
| `find_module` | Method |  |
| `find_spec` | Method |  |
| `invalidate_caches` | Method | An optional method for clearing the finder's cache, if any. This method is used… |
| `NullFinder` | Class | A "Finder" (aka "MetaClassFinder") that never finds any modules, but may find d… |
| `find_module` | Method |  |
| `find_spec` | Method |  |
| `PackageMetadata` | Class |  |
| `get_all` | Method | Return all values associated with a possibly multi-valued key. |
| `PackageNotFoundError` | Class | The package was not found. |
| `PackagePath` | Class | A reference to a path in a package |
| `as_posix` | Method | Return the string representation of the path with forward (/) slashes. |
| `as_uri` | Method | Return the path as a URI. |
| `full_match` | Method | Return True if this path matches the given glob-style pattern. The pattern is m… |
| `is_absolute` | Method | True if the path is absolute (has both a root and, if applicable, a drive). |
| `is_relative_to` | Method | Return True if the path is relative to another path or False. |
| `is_reserved` | Method | Return True if the path contains one of the special names reserved by the syste… |
| `joinpath` | Method | Combine this path with one or several arguments, and return a new path represen… |
| `locate` | Method | Return a path-like object for this path |
| `match` | Method | Return True if this path matches the given pattern. If the pattern is relative,… |
| `read_binary` | Method |  |
| `read_text` | Method |  |
| `relative_to` | Method | Return the relative path to another path identified by the passed arguments.  I… |
| `with_name` | Method | Return a new path with the file name changed. |

## Classes

### `NaclImporter`

Import hook to force PyNaCl to perform dlopen on libsodium with the
RTLD_DEEPBIND flag. This is to work around an issue where pyzmq does a dlopen
with RTLD_GLOBAL which then causes calls to libsodium…

```python
salt.NaclImporter(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ArgumentValueError`

Used when an invalid argument was passed to a command execution

```python
salt.exceptions.ArgumentValueError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `AuthenticationError`

If sha256 signature fails during decryption

```python
salt.exceptions.AuthenticationError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `AuthorizationError`

Thrown when runner or wheel execution fails due to permissions

```python
salt.exceptions.AuthorizationError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `CheckError`

Used when a check fails

```python
salt.exceptions.CheckError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `CodePageError`

Raised when an error ocurs while getting or setting the windows code page

```python
salt.exceptions.CodePageError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `CommandExecutionError`

Used when a module runs a command which returns an error and wants
to show the user the output gracefully instead of dying

```python
salt.exceptions.CommandExecutionError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `CommandNotFoundError`

Used in modules or grains when a required binary is not available

```python
salt.exceptions.CommandNotFoundError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `EauthAuthenticationError`

Thrown when eauth authentication fails

```python
salt.exceptions.EauthAuthenticationError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `FileLockError`

Used when an error occurs obtaining a file lock

```python
salt.exceptions.FileLockError(self, message, time_start=None, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `—` | pos/kw |
| `time_start` | `—` | `None` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FileserverConfigError`

Used when invalid fileserver settings are detected

```python
salt.exceptions.FileserverConfigError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `GitLockError`

Raised when an uncaught error occurs in the midst of obtaining an
update/checkout lock in salt.utils.gitfs.

NOTE: While this uses the errno param similar to an OSError, this exception
class is *not*…

```python
salt.exceptions.GitLockError(self, errno, message, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `errno` | `—` | `—` | pos/kw |
| `message` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `GitRemoteError`

Used by GitFS to denote a problem with the existence of the "origin" remote
or part of its configuration

```python
salt.exceptions.GitRemoteError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `InvalidConfigError`

Used when the config is invalid

```python
salt.exceptions.InvalidConfigError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `InvalidEntityError`

Used when an entity fails validation

```python
salt.exceptions.InvalidEntityError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `InvalidKeyError`

Raised when we encounter an invalid RSA key.

```python
salt.exceptions.InvalidKeyError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `LoaderError`

Problems loading the right renderer

```python
salt.exceptions.LoaderError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `LoggingRuntimeError`

Raised when we encounter an error while logging

```python
salt.exceptions.LoggingRuntimeError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MasterExit`

Rise when the master exits

```python
salt.exceptions.MasterExit(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `MinionError`

Minion problems reading uris such as salt:// or http://

```python
salt.exceptions.MinionError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `MissingSmb`

Raised when no smb library is found.

```python
salt.exceptions.MissingSmb(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `NotImplemented`

Used when a module runs a command which returns an error and wants
to show the user the output gracefully instead of dying

```python
salt.exceptions.NotImplemented(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `NxosCliError`

NX-OS Cli Error raised when Cli command rejected by the NX-OS device

```python
salt.exceptions.NxosCliError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `NxosClientError`

NX-OS Client Error raised for problems connecting to the NX-OS device

```python
salt.exceptions.NxosClientError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `NxosError`

NX-OS Base Exception class

```python
salt.exceptions.NxosError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `NxosRequestNotSupported`

Raised for unsupported client requests

```python
salt.exceptions.NxosRequestNotSupported(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `PkgParseError`

Used when of the pkg modules cannot correctly parse the output from
the CLI tool (pacman, yum, apt, aptitude, etc)

```python
salt.exceptions.PkgParseError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `PublishError`

Problems encountered when trying to publish a command

```python
salt.exceptions.PublishError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltCacheError`

Thrown when a problem was encountered trying to read or write from the salt cache

```python
salt.exceptions.SaltCacheError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltClientError`

Problem reading the master root key

```python
salt.exceptions.SaltClientError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltClientTimeout`

Thrown when a job sent through one of the Client interfaces times out

Takes the ``jid`` as a parameter

```python
salt.exceptions.SaltClientTimeout(self, message, jid=None, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `—` | pos/kw |
| `jid` | `—` | `None` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `SaltCloudConfigError`

Raised when a configuration setting is not found and should exist.

```python
salt.exceptions.SaltCloudConfigError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltCloudException`

Generic Salt Cloud Exception

```python
salt.exceptions.SaltCloudException(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltCloudExecutionFailure`

Raised when too much failures have occurred while querying/waiting for data.

```python
salt.exceptions.SaltCloudExecutionFailure(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltCloudExecutionTimeout`

Raised when too much time has passed while querying/waiting for data.

```python
salt.exceptions.SaltCloudExecutionTimeout(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltCloudNotFound`

Raised when some cloud provider function cannot find what's being searched.

```python
salt.exceptions.SaltCloudNotFound(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltCloudPasswordError`

Raise when virtual terminal password input failed

```python
salt.exceptions.SaltCloudPasswordError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltCloudSystemExit`

This exception is raised when the execution should be stopped.

```python
salt.exceptions.SaltCloudSystemExit(self, message, exit_code=1)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `—` | pos/kw |
| `exit_code` | `—` | `1` | pos/kw |

### `SaltConfigurationError`

Configuration error

```python
salt.exceptions.SaltConfigurationError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltDaemonNotRunning`

Throw when a running master/minion/syndic is not running but is needed to
perform the requested operation (e.g., eauth).

```python
salt.exceptions.SaltDaemonNotRunning(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltDeserializationError`

Thrown when salt cannot deserialize data.

```python
salt.exceptions.SaltDeserializationError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltException`

Base exception class; all Salt-specific exceptions should subclass this

```python
salt.exceptions.SaltException(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltInvocationError`

Used when the wrong number of arguments are sent to modules or invalid
arguments are specified on the command line

```python
salt.exceptions.SaltInvocationError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltMasterError`

Problem reading the master root key

```python
salt.exceptions.SaltMasterError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltMasterUnresolvableError`

Problem resolving the name of the Salt master

```python
salt.exceptions.SaltMasterUnresolvableError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltNoMinionsFound`

An attempt to retrieve a list of minions failed

```python
salt.exceptions.SaltNoMinionsFound(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltRenderError`

Used when a renderer needs to raise an explicit error. If a line number and
buffer string are passed, get_context will be invoked to get the location
of the error.

```python
salt.exceptions.SaltRenderError(self, message, line_num=None, buf='', marker='    <======================', trace=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `—` | pos/kw |
| `line_num` | `—` | `None` | pos/kw |
| `buf` | `—` | `''` | pos/kw |
| `marker` | `—` | `'    <======================'` | pos/kw |
| `trace` | `—` | `None` | pos/kw |

### `SaltReqTimeoutError`

Thrown when a salt master request call fails to return within the timeout

```python
salt.exceptions.SaltReqTimeoutError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltRunnerError`

Problem in runner

```python
salt.exceptions.SaltRunnerError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltSyndicMasterError`

Problem while proxying a request in the syndication master

```python
salt.exceptions.SaltSyndicMasterError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltSystemExit`

This exception is raised when an unsolvable problem is found. There's
nothing else to do, salt should just exit.

```python
salt.exceptions.SaltSystemExit(self, code=0, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `code` | `—` | `0` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `SaltValidationError`

Thrown when a value fails validation

```python
salt.exceptions.SaltValidationError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `SaltWheelError`

Problem in wheel

```python
salt.exceptions.SaltWheelError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `TemplateError`

Used when a custom error is triggered in a template

```python
salt.exceptions.TemplateError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `TimedProcTimeoutError`

Thrown when a timed subprocess does not terminate within the timeout,
or if the specified timeout is not an int or a float

```python
salt.exceptions.TimedProcTimeoutError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `TimeoutError`

Thrown when an opration cannot be completet within a given time limit.

```python
salt.exceptions.TimeoutError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `TokenAuthenticationError`

Thrown when token authentication fails

```python
salt.exceptions.TokenAuthenticationError(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `UnsupportedAlgorithm`

Thrown when a requested encryption or signing algorithm is un-supported.

```python
salt.exceptions.UnsupportedAlgorithm(self, message='')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |

### `VMwareApiError`

Used when representing a generic VMware API error

```python
salt.exceptions.VMwareApiError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareConnectionError`

Used when the client fails to connect to a either a VMware vCenter server or
to a ESXi host

```python
salt.exceptions.VMwareConnectionError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareFileNotFoundError`

Used when representing a generic VMware error if a file not found

```python
salt.exceptions.VMwareFileNotFoundError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareMultipleObjectsError`

Used when multiple objects were retrieved (and one was expected)

```python
salt.exceptions.VMwareMultipleObjectsError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareNotFoundError`

Used when a VMware object was not found

```python
salt.exceptions.VMwareNotFoundError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareObjectExistsError`

Used when a VMware object already exists

```python
salt.exceptions.VMwareObjectExistsError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareObjectNotFoundError`

Used when a VMware object was not found

```python
salt.exceptions.VMwareObjectNotFoundError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareObjectRetrievalError`

Used when a VMware object cannot be retrieved

```python
salt.exceptions.VMwareObjectRetrievalError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwarePowerOnError`

Used when error occurred during power on

```python
salt.exceptions.VMwarePowerOnError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareRuntimeError`

Used when a runtime error is encountered when communicating with the
vCenter

```python
salt.exceptions.VMwareRuntimeError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareSaltError`

Used when a VMware object cannot be retrieved

```python
salt.exceptions.VMwareSaltError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareSystemError`

Used when representing a generic VMware system error

```python
salt.exceptions.VMwareSystemError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareVmCreationError`

Used when a configuration parameter is incorrect

```python
salt.exceptions.VMwareVmCreationError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `VMwareVmRegisterError`

Used when a configuration parameter is incorrect

```python
salt.exceptions.VMwareVmRegisterError(self, message='', info=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `message` | `—` | `''` | pos/kw |
| `info` | `—` | `None` | pos/kw |

### `Distribution`

A Python distribution package.

```python
salt.ext.importlib_metadata.Distribution(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DistributionFinder`

A MetaPathFinder capable of discovering installed distributions.

```python
salt.ext.importlib_metadata.DistributionFinder(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `EntryPoint`

An entry point as defined by Python packaging conventions.

See `the packaging docs on entry points
<https://packaging.python.org/specifications/entry-points/>`_
for more information.

```python
salt.ext.importlib_metadata.EntryPoint(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `FastPath`

Micro-optimized class for searching a path for
children.

```python
salt.ext.importlib_metadata.FastPath(self, root)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `root` | `—` | `—` | pos/kw |

### `FileHash`

```python
salt.ext.importlib_metadata.FileHash(self, spec)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `spec` | `—` | `—` | pos/kw |

### `MetadataPathFinder`

A degenerate finder for distribution packages on the file system.

This finder supplies only a find_distributions() method for versions
of Python that do not have a PathFinder find_distributions().

```python
salt.ext.importlib_metadata.MetadataPathFinder(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NullFinder`

A "Finder" (aka "MetaClassFinder") that never finds any modules,
but may find distributions.

```python
salt.ext.importlib_metadata.NullFinder(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PackageMetadata`

```python
salt.ext.importlib_metadata.PackageMetadata(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PackageNotFoundError`

The package was not found.

```python
salt.ext.importlib_metadata.PackageNotFoundError(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `PackagePath`

A reference to a path in a package

```python
salt.ext.importlib_metadata.PackagePath(self, *args)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |

## Functions

### `extract_masters`

Parses opts and generates a list of master (host,port) addresses.
By default looks for list of masters in opts['master'] and uses
opts['master_port'] as the default port when otherwise not provided.…

```python
salt.daemons.extract_masters(opts, masters='master', port=None, raise_if_empty=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `opts` | `—` | `—` | pos/kw |
| `masters` | `—` | `'master'` | pos/kw |
| `port` | `—` | `None` | pos/kw |
| `raise_if_empty` | `—` | `True` | pos/kw |

### `is_non_string_iterable`

Returns True if obj is non-string iterable, False otherwise

Future proof way that is compatible with both Python3 and Python2 to check
for non string iterables.
Assumes in Python3 that, basestring =…

```python
salt.daemons.is_non_string_iterable(obj)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `—` | pos/kw |

### `is_non_string_sequence`

Returns True if obj is non-string sequence, False otherwise

Future proof way that is compatible with both Python3 and Python2 to check
for non string sequences.
Assumes in Python3 that, basestring =…

```python
salt.daemons.is_non_string_sequence(obj)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `obj` | `—` | `—` | pos/kw |

### `parse_hostname`

Parse hostname string and return a tuple of (host, port)
If port missing in hostname string then use default_port
If anything is not a valid then return None

hostname should contain a host and an op…

```python
salt.daemons.parse_hostname(hostname, default_port)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `hostname` | `—` | `—` | pos/kw |
| `default_port` | `—` | `—` | pos/kw |

### `get_error_message`

Get human readable message from Python Exception

```python
salt.exceptions.get_error_message(error)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `error` | `—` | `—` | pos/kw |

### `execute`

Directly calls the given function with arguments

```python
salt.executors.direct_call.execute(opts, data, func, args, kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `opts` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |
| `func` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | pos/kw |

### `allow_missing_func`

Allow all calls to be passed through to docker container.

The docker call will use direct_call, which will return back if the module
was unable to be run.

```python
salt.executors.docker.allow_missing_func(function)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `function` | `—` | `—` | pos/kw |

### `execute`

Directly calls the given function with arguments

```python
salt.executors.docker.execute(opts, data, func, args, kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `opts` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |
| `func` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | pos/kw |

### `execute`

Splay a salt function call execution time across minions over
a number of seconds (default: 300)

.. note::
    You *probably* want to use --async here and look up the job results later.
    If you'r…

```python
salt.executors.splay.execute(opts, data, func, args, kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `opts` | `—` | `—` | pos/kw |
| `data` | `—` | `—` | pos/kw |
| `func` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | pos/kw |
| `kwargs` | `—` | `—` | pos/kw |

### `get_mro`

```python
salt.ext.backports_abc.get_mro(cls)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cls` | `—` | `—` | pos/kw |

### `mk_awaitable`

```python
salt.ext.backports_abc.mk_awaitable()
```

### `mk_coroutine`

```python
salt.ext.backports_abc.mk_coroutine()
```

### `mk_gen`

```python
salt.ext.backports_abc.mk_gen()
```

### `old_style_mro`

```python
salt.ext.backports_abc.old_style_mro(cls)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cls` | `—` | `—` | pos/kw |

### `patch`

Main entry point for patching the ``collections.abc`` and ``inspect``
standard library modules.

```python
salt.ext.backports_abc.patch(patch_inspect=True)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `patch_inspect` | `—` | `True` | pos/kw |

## Methods

### `salt.NaclImporter` methods

### `create_module`

```python
salt.NaclImporter.create_module(self, spec)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `spec` | `—` | `—` | pos/kw |

### `exec_module`

```python
salt.NaclImporter.exec_module(self, module)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `module` | `—` | `—` | pos/kw |

### `find_module`

```python
salt.NaclImporter.find_module(self, module_name, package_path=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `module_name` | `—` | `—` | pos/kw |
| `package_path` | `—` | `None` | pos/kw |

### `salt.exceptions.ArgumentValueError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.ArgumentValueError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.AuthenticationError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.AuthenticationError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.AuthorizationError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.AuthorizationError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.CheckError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.CheckError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.CodePageError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.CodePageError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.CommandExecutionError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.CommandExecutionError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.CommandNotFoundError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.CommandNotFoundError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.EauthAuthenticationError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.EauthAuthenticationError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.FileLockError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.FileLockError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.FileserverConfigError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.FileserverConfigError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.GitLockError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.GitLockError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.GitRemoteError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.GitRemoteError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.InvalidConfigError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.InvalidConfigError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.InvalidEntityError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.InvalidEntityError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.InvalidKeyError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.InvalidKeyError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.LoaderError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.LoaderError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.MinionError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.MinionError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.MissingSmb` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.MissingSmb.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.NotImplemented` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.NotImplemented.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.NxosCliError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.NxosCliError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.NxosClientError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.NxosClientError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.NxosError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.NxosError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.NxosRequestNotSupported` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.NxosRequestNotSupported.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.PkgParseError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.PkgParseError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.PublishError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.PublishError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltCacheError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltCacheError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltClientError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltClientError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltClientTimeout` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltClientTimeout.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltCloudConfigError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltCloudConfigError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltCloudException` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltCloudException.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltCloudExecutionFailure` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltCloudExecutionFailure.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltCloudExecutionTimeout` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltCloudExecutionTimeout.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltCloudNotFound` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltCloudNotFound.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltCloudPasswordError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltCloudPasswordError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltCloudSystemExit` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltCloudSystemExit.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltConfigurationError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltConfigurationError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltDaemonNotRunning` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltDaemonNotRunning.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltDeserializationError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltDeserializationError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltException` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltException.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltInvocationError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltInvocationError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltMasterError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltMasterError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltMasterUnresolvableError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltMasterUnresolvableError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltNoMinionsFound` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltNoMinionsFound.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltRenderError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltRenderError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltReqTimeoutError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltReqTimeoutError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltRunnerError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltRunnerError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltSyndicMasterError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltSyndicMasterError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltValidationError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltValidationError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.SaltWheelError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.SaltWheelError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.TemplateError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.TemplateError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.TimedProcTimeoutError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.TimedProcTimeoutError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.TimeoutError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.TimeoutError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.TokenAuthenticationError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.TokenAuthenticationError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.UnsupportedAlgorithm` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.UnsupportedAlgorithm.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareApiError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareApiError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareConnectionError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareConnectionError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareFileNotFoundError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareFileNotFoundError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareMultipleObjectsError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareMultipleObjectsError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareNotFoundError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareNotFoundError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareObjectExistsError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareObjectExistsError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareObjectNotFoundError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareObjectNotFoundError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareObjectRetrievalError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareObjectRetrievalError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwarePowerOnError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwarePowerOnError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareRuntimeError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareRuntimeError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareSaltError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareSaltError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareSystemError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareSystemError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareVmCreationError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareVmCreationError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.exceptions.VMwareVmRegisterError` methods

### `pack`

Pack this exception into a serializable dictionary that is safe for
transport via msgpack

```python
salt.exceptions.VMwareVmRegisterError.pack(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.ext.importlib_metadata.Distribution` methods

### `at`

Return a Distribution for the indicated metadata path

:param path: a string or path-like object
:return: a concrete Distribution instance for the path

```python
salt.ext.importlib_metadata.Distribution.at(path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `path` | `—` | `—` | pos/kw |

### `discover`

Return an iterable of Distribution objects for all packages.

Pass a ``context`` or pass keyword arguments for constructing
a context.

:context: A ``DistributionFinder.Context`` object.
:return: Ite…

```python
salt.ext.importlib_metadata.Distribution.discover(**kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `kwargs` | `—` | `—` | **kwargs |

### `from_name`

Return the Distribution for the given package name.

:param name: The name of the distribution package to search for.
:return: The Distribution instance (or subclass thereof) for the named
    packag…

```python
salt.ext.importlib_metadata.Distribution.from_name(name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |

### `locate_file`

Given a path to a file in this distribution, return a path
to it.

```python
salt.ext.importlib_metadata.Distribution.locate_file(self, path)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |

### `read_text`

Attempt to load metadata file given by the name.

:param filename: The name of the file in the distribution info.
:return: The text if found, otherwise None.

```python
salt.ext.importlib_metadata.Distribution.read_text(self, filename)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filename` | `—` | `—` | pos/kw |

### `salt.ext.importlib_metadata.DistributionFinder` methods

### `find_distributions`

Find distributions.

Return an iterable of all Distribution instances capable of
loading the metadata for packages matching the ``context``,
a DistributionFinder.Context instance.

```python
salt.ext.importlib_metadata.DistributionFinder.find_distributions(self, context=<salt.ext.importlib_metadata.DistributionFinder.Context object at 0x7f447e6c2510>)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `—` | `<salt.ext.importlib_metadata.DistributionFinder.Context object at 0x7f447e6c2510>` | pos/kw |

### `invalidate_caches`

An optional method for clearing the finder's cache, if any.
This method is used by importlib.invalidate_caches().

```python
salt.ext.importlib_metadata.DistributionFinder.invalidate_caches(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.ext.importlib_metadata.EntryPoint` methods

### `load`

Load the entry point from its definition. If only a module
is indicated by the value, return that module. Otherwise,
return the named object.

```python
salt.ext.importlib_metadata.EntryPoint.load(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.ext.importlib_metadata.FastPath` methods

### `children`

```python
salt.ext.importlib_metadata.FastPath.children(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `joinpath`

```python
salt.ext.importlib_metadata.FastPath.joinpath(self, child)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `child` | `—` | `—` | pos/kw |

### `search`

```python
salt.ext.importlib_metadata.FastPath.search(self, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `zip_children`

```python
salt.ext.importlib_metadata.FastPath.zip_children(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.ext.importlib_metadata.MetadataPathFinder` methods

### `find_distributions`

Find distributions.

Return an iterable of all Distribution instances capable of
loading the metadata for packages matching ``context.name``
(or all names if ``None`` indicated) along the paths in th…

```python
salt.ext.importlib_metadata.MetadataPathFinder.find_distributions(self, context=<salt.ext.importlib_metadata.DistributionFinder.Context object at 0x7f447e4dd310>)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `context` | `—` | `<salt.ext.importlib_metadata.DistributionFinder.Context object at 0x7f447e4dd310>` | pos/kw |

### `find_module`

```python
salt.ext.importlib_metadata.MetadataPathFinder.find_module(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `find_spec`

```python
salt.ext.importlib_metadata.MetadataPathFinder.find_spec(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `invalidate_caches`

An optional method for clearing the finder's cache, if any.
This method is used by importlib.invalidate_caches().

```python
salt.ext.importlib_metadata.MetadataPathFinder.invalidate_caches(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `salt.ext.importlib_metadata.NullFinder` methods

### `find_module`

```python
salt.ext.importlib_metadata.NullFinder.find_module(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `find_spec`

```python
salt.ext.importlib_metadata.NullFinder.find_spec(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `salt.ext.importlib_metadata.PackageMetadata` methods

### `get_all`

Return all values associated with a possibly multi-valued key.

```python
salt.ext.importlib_metadata.PackageMetadata.get_all(self, str, failobj=Ellipsis)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `str` | `—` | `—` | pos/kw |
| `failobj` | `—` | `Ellipsis` | pos/kw |

### `salt.ext.importlib_metadata.PackagePath` methods

### `as_posix`

Return the string representation of the path with forward (/)
slashes.

```python
salt.ext.importlib_metadata.PackagePath.as_posix(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `as_uri`

Return the path as a URI.

```python
salt.ext.importlib_metadata.PackagePath.as_uri(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `full_match`

Return True if this path matches the given glob-style pattern. The
pattern is matched against the entire path.

```python
salt.ext.importlib_metadata.PackagePath.full_match(self, pattern, *, case_sensitive=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `pattern` | `—` | `—` | pos/kw |
| `case_sensitive` | `—` | `None` | kw |

### `is_absolute`

True if the path is absolute (has both a root and, if applicable,
a drive).

```python
salt.ext.importlib_metadata.PackagePath.is_absolute(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `is_relative_to`

Return True if the path is relative to another path or False.

```python
salt.ext.importlib_metadata.PackagePath.is_relative_to(self, other, /, *_deprecated)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `other` | `—` | `—` | pos |
| `_deprecated` | `—` | `—` | *args |

### `is_reserved`

Return True if the path contains one of the special names reserved
by the system, if any.

```python
salt.ext.importlib_metadata.PackagePath.is_reserved(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `joinpath`

Combine this path with one or several arguments, and return a
new path representing either a subpath (if all arguments are relative
paths) or a totally different path (if one of the arguments is
anch…

```python
salt.ext.importlib_metadata.PackagePath.joinpath(self, *pathsegments)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `pathsegments` | `—` | `—` | *args |

### `locate`

Return a path-like object for this path

```python
salt.ext.importlib_metadata.PackagePath.locate(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `match`

Return True if this path matches the given pattern. If the pattern is
relative, matching is done from the right; otherwise, the entire path
is matched. The recursive wildcard '**' is *not* supported…

```python
salt.ext.importlib_metadata.PackagePath.match(self, path_pattern, *, case_sensitive=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path_pattern` | `—` | `—` | pos/kw |
| `case_sensitive` | `—` | `None` | kw |

### `read_binary`

```python
salt.ext.importlib_metadata.PackagePath.read_binary(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `read_text`

```python
salt.ext.importlib_metadata.PackagePath.read_text(self, encoding='utf-8')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `encoding` | `—` | `'utf-8'` | pos/kw |

### `relative_to`

Return the relative path to another path identified by the passed
arguments.  If the operation is not possible (because this is not
related to the other path), raise ValueError.

The *walk_up* parame…

```python
salt.ext.importlib_metadata.PackagePath.relative_to(self, other, /, *_deprecated, walk_up=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `other` | `—` | `—` | pos |
| `_deprecated` | `—` | `—` | *args |
| `walk_up` | `—` | `False` | kw |

### `with_name`

Return a new path with the file name changed.

```python
salt.ext.importlib_metadata.PackagePath.with_name(self, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |


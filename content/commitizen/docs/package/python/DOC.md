---
name: package
description: "Commitizen Python CLI for conventional commits, semantic version bumps, changelog generation, and release automation in Git repositories"
metadata:
  languages: "python"
  versions: "4.13.9"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "commitizen,python,git,conventional-commits,semver,changelog,release,toml,Version-Sensitive,BaseCommitizen,example,format_exception_message,info,message,questions,schema,schema_pattern,validate_commit_message,CurrentVersionNotFoundError,GitCommit,from_rev_and_commit,create_commit_message,find_increment,smart_open,update_version_in_files,IncrementalMergeInfo,InvalidConfigurationError,Metadata,NoCommitsFoundError,TagRules,extract_version,find_tag_for,from_settings,get_version_tags,include_in_changelog,is_ignored_tag,is_version_tag,normalize_tag,search_version,generate_ordered_changelog_tree,generate_tree_from_commits,get_changelog_template,get_commit_tag,get_next_tag_name_after_version,get_oldest_and_newest_rev,get_smart_tag_range,incremental_build,process_commit_message,render_changelog,ChangelogFormat,get_latest_full_release,get_metadata,ChangelogFormatUnknown,get_changelog_format,AsciiDoc,get_latest_full_release_from_file,get_metadata_from_file,parse_title_level,parse_version_from_title,BaseFormat,BaseConfig,contains_commitizen_section,init_empty_config_content,set_key,update,GitTag,from_line,VersionTag,get_version_scheme,Markdown,RestructuredText,Textile,CommitizenException,ExitCode,ExpectedExit,InvalidCommandArgumentError,NoCommandFoundError,ParseKwargs,format_usage,commitizen_excepthook,main,parse_no_raise,CharacterSetDecodeError,Command,run,Bump,Changelog,Check,Commit,manual_edit,Example,Info,Init,ListCz,Schema,Version,BumpArgs,BumpCommitFailedError,BumpTagFailedError,DryRunExit,InvalidManualVersion,NoPatternMapError,NoneIncrementExit,NotAGitProjectError,NotAllowed,Settings,VersionProtocol,bump,get_provider,ChangelogArgs,NoRevisionError"
---

# commitizen — package

## Install

```bash
pip install commitizen
```

## Imports

```python
import commitizen
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `BaseCommitizen` | Class |  |
| `example` | Method | Example of the commit message. |
| `format_exception_message` | Method | Format commit errors. |
| `info` | Method | Information about the standardized commit message. |
| `message` | Method | Format your git message. |
| `questions` | Method | Questions regarding the commit message. |
| `schema` | Method | Schema definition of the commit message. |
| `schema_pattern` | Method | Regex matching the schema used for message validation. |
| `validate_commit_message` | Method | Validate commit message against the pattern. |
| `CurrentVersionNotFoundError` | Class | Current version cannot be found in `version_files` |
| `GitCommit` | Class |  |
| `from_rev_and_commit` | Method | Create a GitCommit instance from a formatted commit string.  This method parses… |
| `create_commit_message` | Function |  |
| `find_increment` | Function |  |
| `smart_open` | Function | Open a file with the EOL style determined from Git. |
| `update_version_in_files` | Function | Change old version to the new one in every file given.  Note that this version… |
| `IncrementalMergeInfo` | Class | Information regarding the last non-pre-release, parsed from the changelog.  Req… |
| `InvalidConfigurationError` | Class | An error was found in the Commitizen Configuration, such as duplicates in `chan… |
| `Metadata` | Class | Metadata extracted from the changelog produced by a plugin |
| `NoCommitsFoundError` | Class | No commits found |
| `TagRules` | Class | Encapsulate tag-related rules.  It allows to filter or match tags according to… |
| `extract_version` | Method | Extract a version from the tag as defined in tag formats.  Raises `InvalidVersi… |
| `find_tag_for` | Method | Find the first matching tag for a given version. |
| `from_settings` | Method | Extract tag rules from settings |
| `get_version_tags` | Method | Filter in version tags and warn on unexpected tags |
| `include_in_changelog` | Method | Check if a tag should be included in the changelog |
| `is_ignored_tag` | Method | True if a given tag can be ignored |
| `is_version_tag` | Method | True if a given tag is a legit version tag.  if `warn` is `True`, it will print… |
| `normalize_tag` | Method | The tag and the software version might be different.  That's why this function… |
| `search_version` | Method | Search the first or last version tag occurrence in text.  It searches for compl… |

_Plus 170 more — see ## Classes / ## Functions / ## Methods below._


## Classes

### `BaseCommitizen`

```python
commitizen.BaseCommitizen(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `CurrentVersionNotFoundError`

Current version cannot be found in `version_files`

```python
commitizen.bump.CurrentVersionNotFoundError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `GitCommit`

```python
commitizen.bump.GitCommit(self, rev: 'str', title: 'str', body: 'str' = '', author: 'str' = '', author_email: 'str' = '', parents: 'list[str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `rev` | `str` | `—` | pos/kw |
| `title` | `str` | `—` | pos/kw |
| `body` | `str` | `''` | pos/kw |
| `author` | `str` | `''` | pos/kw |
| `author_email` | `str` | `''` | pos/kw |
| `parents` | `list[str] \| None` | `None` | pos/kw |

### `IncrementalMergeInfo`

Information regarding the last non-pre-release, parsed from the changelog.

Required to merge pre-releases on bump.
Separate from Metadata to not mess with the interface.

```python
commitizen.changelog.IncrementalMergeInfo(self, name: 'str | None' = None, index: 'int | None' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str \| None` | `None` | pos/kw |
| `index` | `int \| None` | `None` | pos/kw |

### `InvalidConfigurationError`

An error was found in the Commitizen Configuration, such as duplicates in `change_type_order`

```python
commitizen.changelog.InvalidConfigurationError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `Metadata`

Metadata extracted from the changelog produced by a plugin

```python
commitizen.changelog.Metadata(self, unreleased_start: 'int | None' = None, unreleased_end: 'int | None' = None, latest_version: 'str | None' = None, latest_version_position: 'int | None' = None, latest_version_tag: 'str | None' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `unreleased_start` | `int \| None` | `None` | pos/kw |
| `unreleased_end` | `int \| None` | `None` | pos/kw |
| `latest_version` | `str \| None` | `None` | pos/kw |
| `latest_version_position` | `int \| None` | `None` | pos/kw |
| `latest_version_tag` | `str \| None` | `None` | pos/kw |

### `NoCommitsFoundError`

No commits found

```python
commitizen.changelog.NoCommitsFoundError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `TagRules`

Encapsulate tag-related rules.

It allows to filter or match tags according to rules provided in settings:
- `tag_format`: the current format of the tags generated on `bump`
- `legacy_tag_formats`: p…

```python
commitizen.changelog.TagRules(self, scheme: 'VersionScheme' = <class 'commitizen.version_schemes.Pep440'>, tag_format: 'str' = '$version', legacy_tag_formats: 'Sequence[str]' = <factory>, ignored_tag_formats: 'Sequence[str]' = <factory>, merge_prereleases: 'bool' = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `scheme` | `VersionScheme` | `<class 'commitizen.version_schemes.Pep440'>` | pos/kw |
| `tag_format` | `str` | `'$version'` | pos/kw |
| `legacy_tag_formats` | `Sequence[str]` | `<factory>` | pos/kw |
| `ignored_tag_formats` | `Sequence[str]` | `<factory>` | pos/kw |
| `merge_prereleases` | `bool` | `False` | pos/kw |

### `ChangelogFormat`

Base class for protocol classes.

Protocol classes are defined as::

    class Proto(Protocol):
        def meth(self) -> int:
            ...

Such classes are primarily used with static type checke…

```python
commitizen.changelog_formats.ChangelogFormat(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `ChangelogFormatUnknown`

Unknown `changelog_format` or cannot be determined by the file extension

```python
commitizen.changelog_formats.ChangelogFormatUnknown(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `AsciiDoc`

Base class to extend to implement a changelog file format.

```python
commitizen.changelog_formats.asciidoc.AsciiDoc(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `BaseFormat`

Base class to extend to implement a changelog file format.

```python
commitizen.changelog_formats.asciidoc.BaseFormat(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `BaseConfig`

```python
commitizen.changelog_formats.base.BaseConfig(self) -> 'None'
```

### `BaseFormat`

Base class to extend to implement a changelog file format.

```python
commitizen.changelog_formats.base.BaseFormat(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `ChangelogFormat`

Base class for protocol classes.

Protocol classes are defined as::

    class Proto(Protocol):
        def meth(self) -> int:
            ...

Such classes are primarily used with static type checke…

```python
commitizen.changelog_formats.base.ChangelogFormat(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `GitTag`

```python
commitizen.changelog_formats.base.GitTag(self, name: 'str', rev: 'str', date: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `rev` | `str` | `—` | pos/kw |
| `date` | `str` | `—` | pos/kw |

### `IncrementalMergeInfo`

Information regarding the last non-pre-release, parsed from the changelog.

Required to merge pre-releases on bump.
Separate from Metadata to not mess with the interface.

```python
commitizen.changelog_formats.base.IncrementalMergeInfo(self, name: 'str | None' = None, index: 'int | None' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str \| None` | `None` | pos/kw |
| `index` | `int \| None` | `None` | pos/kw |

### `Metadata`

Metadata extracted from the changelog produced by a plugin

```python
commitizen.changelog_formats.base.Metadata(self, unreleased_start: 'int | None' = None, unreleased_end: 'int | None' = None, latest_version: 'str | None' = None, latest_version_position: 'int | None' = None, latest_version_tag: 'str | None' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `unreleased_start` | `int \| None` | `None` | pos/kw |
| `unreleased_end` | `int \| None` | `None` | pos/kw |
| `latest_version` | `str \| None` | `None` | pos/kw |
| `latest_version_position` | `int \| None` | `None` | pos/kw |
| `latest_version_tag` | `str \| None` | `None` | pos/kw |

### `TagRules`

Encapsulate tag-related rules.

It allows to filter or match tags according to rules provided in settings:
- `tag_format`: the current format of the tags generated on `bump`
- `legacy_tag_formats`: p…

```python
commitizen.changelog_formats.base.TagRules(self, scheme: 'VersionScheme' = <class 'commitizen.version_schemes.Pep440'>, tag_format: 'str' = '$version', legacy_tag_formats: 'Sequence[str]' = <factory>, ignored_tag_formats: 'Sequence[str]' = <factory>, merge_prereleases: 'bool' = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `scheme` | `VersionScheme` | `<class 'commitizen.version_schemes.Pep440'>` | pos/kw |
| `tag_format` | `str` | `'$version'` | pos/kw |
| `legacy_tag_formats` | `Sequence[str]` | `<factory>` | pos/kw |
| `ignored_tag_formats` | `Sequence[str]` | `<factory>` | pos/kw |
| `merge_prereleases` | `bool` | `False` | pos/kw |

### `VersionTag`

Represent a version and its matching tag form.

```python
commitizen.changelog_formats.base.VersionTag(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BaseFormat`

Base class to extend to implement a changelog file format.

```python
commitizen.changelog_formats.markdown.BaseFormat(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `Markdown`

Base class to extend to implement a changelog file format.

```python
commitizen.changelog_formats.markdown.Markdown(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `BaseFormat`

Base class to extend to implement a changelog file format.

```python
commitizen.changelog_formats.restructuredtext.BaseFormat(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `Metadata`

Metadata extracted from the changelog produced by a plugin

```python
commitizen.changelog_formats.restructuredtext.Metadata(self, unreleased_start: 'int | None' = None, unreleased_end: 'int | None' = None, latest_version: 'str | None' = None, latest_version_position: 'int | None' = None, latest_version_tag: 'str | None' = None) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `unreleased_start` | `int \| None` | `None` | pos/kw |
| `unreleased_end` | `int \| None` | `None` | pos/kw |
| `latest_version` | `str \| None` | `None` | pos/kw |
| `latest_version_position` | `int \| None` | `None` | pos/kw |
| `latest_version_tag` | `str \| None` | `None` | pos/kw |

### `RestructuredText`

Base class to extend to implement a changelog file format.

```python
commitizen.changelog_formats.restructuredtext.RestructuredText(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `BaseFormat`

Base class to extend to implement a changelog file format.

```python
commitizen.changelog_formats.textile.BaseFormat(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `Textile`

Base class to extend to implement a changelog file format.

```python
commitizen.changelog_formats.textile.Textile(self, config: 'BaseConfig') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

### `CommitizenException`

Common base class for all non-exit exceptions.

```python
commitizen.cli.CommitizenException(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `ExitCode`

Enum where members are also (and must be) ints

```python
commitizen.cli.ExitCode(self, *args, **kwds)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwds` | `—` | `—` | **kwargs |

### `ExpectedExit`

Common base class for all non-exit exceptions.

```python
commitizen.cli.ExpectedExit(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `InvalidCommandArgumentError`

The argument provided to the command is invalid (e.g. `cz check -commit-msg-file filename --rev-range master..`)

```python
commitizen.cli.InvalidCommandArgumentError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `NoCommandFoundError`

No command found when running Commitizen cli (e.g., `cz --debug`)

```python
commitizen.cli.NoCommandFoundError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `ParseKwargs`

Parse arguments in the for `key=value`.

Quoted strings are automatically unquoted.
Can be submitted multiple times:

ex:
    -k key=value -k double-quotes="value" -k single-quotes='value'

    will…

```python
commitizen.cli.ParseKwargs(self, option_strings, dest, nargs=None, const=None, default=None, type=None, choices=None, required=False, help=None, metavar=None, deprecated=False)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `option_strings` | `—` | `—` | pos/kw |
| `dest` | `—` | `—` | pos/kw |
| `nargs` | `—` | `None` | pos/kw |
| `const` | `—` | `None` | pos/kw |
| `default` | `—` | `None` | pos/kw |
| `type` | `—` | `None` | pos/kw |
| `choices` | `—` | `None` | pos/kw |
| `required` | `—` | `False` | pos/kw |
| `help` | `—` | `None` | pos/kw |
| `metavar` | `—` | `None` | pos/kw |
| `deprecated` | `—` | `False` | pos/kw |

### `CharacterSetDecodeError`

The character encoding of the command output could not be determined

```python
commitizen.cmd.CharacterSetDecodeError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `Command`

Command(out, err, stdout, stderr, return_code)

```python
commitizen.cmd.Command(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Bump`

Show prompt for the user to create a guided commit.

```python
commitizen.commands.Bump(self, config: 'BaseConfig', arguments: 'BumpArgs') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `arguments` | `BumpArgs` | `—` | pos/kw |

### `Changelog`

Generate a changelog based on the commit history.

```python
commitizen.commands.Changelog(self, config: 'BaseConfig', arguments: 'ChangelogArgs') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `arguments` | `ChangelogArgs` | `—` | pos/kw |

### `Check`

Check if the current commit msg matches the commitizen format.

```python
commitizen.commands.Check(self, config: 'BaseConfig', arguments: 'CheckArgs', *args: 'object') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `arguments` | `CheckArgs` | `—` | pos/kw |
| `args` | `object` | `—` | *args |

### `Commit`

Show prompt for the user to create a guided commit.

```python
commitizen.commands.Commit(self, config: 'BaseConfig', arguments: 'CommitArgs') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `arguments` | `CommitArgs` | `—` | pos/kw |

### `Example`

Show an example so people understands the rules.

```python
commitizen.commands.Example(self, config: commitizen.config.base_config.BaseConfig, *args: object) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `args` | `object` | `—` | *args |

### `Info`

Show in depth explanation of your rules.

```python
commitizen.commands.Info(self, config: commitizen.config.base_config.BaseConfig, *args: object) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `args` | `object` | `—` | *args |

### `Init`

```python
commitizen.commands.Init(self, config: 'BaseConfig', *args: 'object') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `args` | `object` | `—` | *args |

### `ListCz`

List currently installed rules.

```python
commitizen.commands.ListCz(self, config: commitizen.config.base_config.BaseConfig, *args: object) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `args` | `object` | `—` | *args |

### `Schema`

Show structure of the rule.

```python
commitizen.commands.Schema(self, config: commitizen.config.base_config.BaseConfig, *args: object) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `args` | `object` | `—` | *args |

### `Version`

Get the version of the installed commitizen or the current project.
Precedence:
1. report
2. commitizen
3. verbose, project

```python
commitizen.commands.Version(self, config: commitizen.config.base_config.BaseConfig, arguments: commitizen.commands.version.VersionArgs) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `arguments` | `VersionArgs` | `—` | pos/kw |

### `Bump`

Show prompt for the user to create a guided commit.

```python
commitizen.commands.bump.Bump(self, config: 'BaseConfig', arguments: 'BumpArgs') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `arguments` | `BumpArgs` | `—` | pos/kw |

### `BumpArgs`

dict() -> new empty dictionary
dict(mapping) -> new dictionary initialized from a mapping object's
    (key, value) pairs
dict(iterable) -> new dictionary initialized as if via:
    d = {}
    for k,…

```python
commitizen.commands.bump.BumpArgs(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `BumpCommitFailedError`

Commit failed when bumping version

```python
commitizen.commands.bump.BumpCommitFailedError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `BumpTagFailedError`

Tag failed when bumping version

```python
commitizen.commands.bump.BumpTagFailedError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `Changelog`

Generate a changelog based on the commit history.

```python
commitizen.commands.bump.Changelog(self, config: 'BaseConfig', arguments: 'ChangelogArgs') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `arguments` | `ChangelogArgs` | `—` | pos/kw |

### `DryRunExit`

Exit due to passing `--dry-run` option

```python
commitizen.commands.bump.DryRunExit(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `ExpectedExit`

Common base class for all non-exit exceptions.

```python
commitizen.commands.bump.ExpectedExit(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `InvalidManualVersion`

Manually provided version is invalid

```python
commitizen.commands.bump.InvalidManualVersion(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `NoCommitsFoundError`

No commits found

```python
commitizen.commands.bump.NoCommitsFoundError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `NoPatternMapError`

bump / changelog pattern or map can not be found in configuration file

```python
commitizen.commands.bump.NoPatternMapError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `NoneIncrementExit`

The commits found are not eligible to be bumped

```python
commitizen.commands.bump.NoneIncrementExit(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `NotAGitProjectError`

Not in a git project

```python
commitizen.commands.bump.NotAGitProjectError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `NotAllowed`

`--incremental` cannot be combined with a `rev_range`

```python
commitizen.commands.bump.NotAllowed(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `Settings`

dict() -> new empty dictionary
dict(mapping) -> new dictionary initialized from a mapping object's
    (key, value) pairs
dict(iterable) -> new dictionary initialized as if via:
    d = {}
    for k,…

```python
commitizen.commands.bump.Settings(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `TagRules`

Encapsulate tag-related rules.

It allows to filter or match tags according to rules provided in settings:
- `tag_format`: the current format of the tags generated on `bump`
- `legacy_tag_formats`: p…

```python
commitizen.commands.bump.TagRules(self, scheme: 'VersionScheme' = <class 'commitizen.version_schemes.Pep440'>, tag_format: 'str' = '$version', legacy_tag_formats: 'Sequence[str]' = <factory>, ignored_tag_formats: 'Sequence[str]' = <factory>, merge_prereleases: 'bool' = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `scheme` | `VersionScheme` | `<class 'commitizen.version_schemes.Pep440'>` | pos/kw |
| `tag_format` | `str` | `'$version'` | pos/kw |
| `legacy_tag_formats` | `Sequence[str]` | `<factory>` | pos/kw |
| `ignored_tag_formats` | `Sequence[str]` | `<factory>` | pos/kw |
| `merge_prereleases` | `bool` | `False` | pos/kw |

### `VersionProtocol`

Base class for protocol classes.

Protocol classes are defined as::

    class Proto(Protocol):
        def meth(self) -> int:
            ...

Such classes are primarily used with static type checke…

```python
commitizen.commands.bump.VersionProtocol(self, version: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `version` | `str` | `—` | pos/kw |

### `Changelog`

Generate a changelog based on the commit history.

```python
commitizen.commands.changelog.Changelog(self, config: 'BaseConfig', arguments: 'ChangelogArgs') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `arguments` | `ChangelogArgs` | `—` | pos/kw |

### `ChangelogArgs`

dict() -> new empty dictionary
dict(mapping) -> new dictionary initialized from a mapping object's
    (key, value) pairs
dict(iterable) -> new dictionary initialized as if via:
    d = {}
    for k,…

```python
commitizen.commands.changelog.ChangelogArgs(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DryRunExit`

Exit due to passing `--dry-run` option

```python
commitizen.commands.changelog.DryRunExit(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `GitTag`

```python
commitizen.commands.changelog.GitTag(self, name: 'str', rev: 'str', date: 'str') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `str` | `—` | pos/kw |
| `rev` | `str` | `—` | pos/kw |
| `date` | `str` | `—` | pos/kw |

### `NoCommitsFoundError`

No commits found

```python
commitizen.commands.changelog.NoCommitsFoundError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `NoPatternMapError`

bump / changelog pattern or map can not be found in configuration file

```python
commitizen.commands.changelog.NoPatternMapError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `NoRevisionError`

No revision found

```python
commitizen.commands.changelog.NoRevisionError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `NotAGitProjectError`

Not in a git project

```python
commitizen.commands.changelog.NotAGitProjectError(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `NotAllowed`

`--incremental` cannot be combined with a `rev_range`

```python
commitizen.commands.changelog.NotAllowed(self, *args: 'str', **kwargs: 'Any') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `str` | `—` | *args |
| `kwargs` | `Any` | `—` | **kwargs |

### `TagRules`

Encapsulate tag-related rules.

It allows to filter or match tags according to rules provided in settings:
- `tag_format`: the current format of the tags generated on `bump`
- `legacy_tag_formats`: p…

```python
commitizen.commands.changelog.TagRules(self, scheme: 'VersionScheme' = <class 'commitizen.version_schemes.Pep440'>, tag_format: 'str' = '$version', legacy_tag_formats: 'Sequence[str]' = <factory>, ignored_tag_formats: 'Sequence[str]' = <factory>, merge_prereleases: 'bool' = False) -> None
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `scheme` | `VersionScheme` | `<class 'commitizen.version_schemes.Pep440'>` | pos/kw |
| `tag_format` | `str` | `'$version'` | pos/kw |
| `legacy_tag_formats` | `Sequence[str]` | `<factory>` | pos/kw |
| `ignored_tag_formats` | `Sequence[str]` | `<factory>` | pos/kw |
| `merge_prereleases` | `bool` | `False` | pos/kw |

## Functions

### `create_commit_message`

```python
commitizen.bump.create_commit_message(current_version: 'Version | str', new_version: 'Version | str', message_template: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `current_version` | `Version \| str` | `—` | pos/kw |
| `new_version` | `Version \| str` | `—` | pos/kw |
| `message_template` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `find_increment`

```python
commitizen.bump.find_increment(commits: 'list[GitCommit]', regex: 'str', increments_map: 'dict | OrderedDict') -> 'Increment | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `commits` | `list[GitCommit]` | `—` | pos/kw |
| `regex` | `str` | `—` | pos/kw |
| `increments_map` | `dict \| OrderedDict` | `—` | pos/kw |

**Returns:** `Increment | None`

### `smart_open`

Open a file with the EOL style determined from Git.

```python
commitizen.bump.smart_open(*args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `update_version_in_files`

Change old version to the new one in every file given.

Note that this version is not the tag formatted one.
So for example, your tag could look like `v1.0.0` while your version in
the package like `…

```python
commitizen.bump.update_version_in_files(current_version: 'str', new_version: 'str', version_files: 'Iterable[str]', *, check_consistency: 'bool', encoding: 'str') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `current_version` | `str` | `—` | pos/kw |
| `new_version` | `str` | `—` | pos/kw |
| `version_files` | `Iterable[str]` | `—` | pos/kw |
| `check_consistency` | `bool` | `—` | kw |
| `encoding` | `str` | `—` | kw |

**Returns:** `list[str]`

### `generate_ordered_changelog_tree`

```python
commitizen.changelog.generate_ordered_changelog_tree(tree: 'Iterable[Mapping[str, Any]]', change_type_order: 'list[str]') -> 'Generator[dict[str, Any], None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tree` | `Iterable[Mapping[str, Any]]` | `—` | pos/kw |
| `change_type_order` | `list[str]` | `—` | pos/kw |

**Returns:** `Generator[dict[str, Any], None, None]`

### `generate_tree_from_commits`

```python
commitizen.changelog.generate_tree_from_commits(commits: 'list[GitCommit]', tags: 'list[GitTag]', commit_parser: 'str', changelog_pattern: 'str', unreleased_version: 'str | None' = None, change_type_map: 'dict[str, str] | None' = None, changelog_message_builder_hook: 'MessageBuilderHook | None' = None, changelog_release_hook: 'ChangelogReleaseHook | None' = None, rules: 'TagRules | None' = None, during_version_bump: 'bool' = False) -> 'Generator[dict[str, Any], None, None]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `commits` | `list[GitCommit]` | `—` | pos/kw |
| `tags` | `list[GitTag]` | `—` | pos/kw |
| `commit_parser` | `str` | `—` | pos/kw |
| `changelog_pattern` | `str` | `—` | pos/kw |
| `unreleased_version` | `str \| None` | `None` | pos/kw |
| `change_type_map` | `dict[str, str] \| None` | `None` | pos/kw |
| `changelog_message_builder_hook` | `MessageBuilderHook \| None` | `None` | pos/kw |
| `changelog_release_hook` | `ChangelogReleaseHook \| None` | `None` | pos/kw |
| `rules` | `TagRules \| None` | `None` | pos/kw |
| `during_version_bump` | `bool` | `False` | pos/kw |

**Returns:** `Generator[dict[str, Any], None, None]`

### `get_changelog_template`

```python
commitizen.changelog.get_changelog_template(loader: 'BaseLoader', template: 'str') -> 'Template'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `loader` | `BaseLoader` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |

**Returns:** `Template`

### `get_commit_tag`

```python
commitizen.changelog.get_commit_tag(commit: 'GitCommit', tags: 'list[GitTag]') -> 'GitTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `commit` | `GitCommit` | `—` | pos/kw |
| `tags` | `list[GitTag]` | `—` | pos/kw |

**Returns:** `GitTag | None`

### `get_next_tag_name_after_version`

```python
commitizen.changelog.get_next_tag_name_after_version(tags: 'Iterable[GitTag]', version: 'str') -> 'str | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tags` | `Iterable[GitTag]` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |

**Returns:** `str | None`

### `get_oldest_and_newest_rev`

Find the tags for the given version.

`version` may come in different formats:
- `0.1.0..0.4.0`: as a range
- `0.3.0`: as a single version

```python
commitizen.changelog.get_oldest_and_newest_rev(tags: 'Iterable[GitTag]', version: 'str', rules: 'TagRules') -> 'tuple[str | None, str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tags` | `Iterable[GitTag]` | `—` | pos/kw |
| `version` | `str` | `—` | pos/kw |
| `rules` | `TagRules` | `—` | pos/kw |

**Returns:** `tuple[str | None, str]`

### `get_smart_tag_range`

Smart because it finds the N+1 tag.

This is because we need to find until the next tag

```python
commitizen.changelog.get_smart_tag_range(tags: 'Sequence[GitTag]', newest: 'str', oldest: 'str | None' = None) -> 'list[GitTag]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tags` | `Sequence[GitTag]` | `—` | pos/kw |
| `newest` | `str` | `—` | pos/kw |
| `oldest` | `str \| None` | `None` | pos/kw |

**Returns:** `list[GitTag]`

### `incremental_build`

Takes the original lines and updates with new_content.

The metadata governs how to remove the old unreleased section and where to place the
new content.

Args:
    lines: The lines from the changelo…

```python
commitizen.changelog.incremental_build(new_content: 'str', lines: 'list[str]', metadata: 'Metadata') -> 'list[str]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `new_content` | `str` | `—` | pos/kw |
| `lines` | `list[str]` | `—` | pos/kw |
| `metadata` | `Metadata` | `—` | pos/kw |

**Returns:** `list[str]`

### `process_commit_message`

```python
commitizen.changelog.process_commit_message(hook: 'MessageBuilderHook | None', parsed: 're.Match[str]', commit: 'GitCommit', ref_changes: 'MutableMapping[str | None, list]', change_type_map: 'Mapping[str, str] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `hook` | `MessageBuilderHook \| None` | `—` | pos/kw |
| `parsed` | `re.Match[str]` | `—` | pos/kw |
| `commit` | `GitCommit` | `—` | pos/kw |
| `ref_changes` | `MutableMapping[str \| None, list]` | `—` | pos/kw |
| `change_type_map` | `Mapping[str, str] \| None` | `None` | pos/kw |

### `render_changelog`

```python
commitizen.changelog.render_changelog(tree: 'Iterable', loader: 'BaseLoader', template: 'str', **kwargs: 'Any') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tree` | `Iterable` | `—` | pos/kw |
| `loader` | `BaseLoader` | `—` | pos/kw |
| `template` | `str` | `—` | pos/kw |
| `kwargs` | `Any` | `—` | **kwargs |

**Returns:** `str`

### `get_changelog_format`

Get a format from its name

:raises FormatUnknown: if a non-empty name is provided but cannot be found in the known formats

```python
commitizen.changelog_formats.get_changelog_format(config: 'BaseConfig', filename: 'str | None' = None) -> 'ChangelogFormat'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `filename` | `str \| None` | `None` | pos/kw |

**Returns:** `ChangelogFormat`

### `get_version_scheme`

Get the version scheme as defined in the configuration
or from an overridden `name`.



:raises VersionSchemeUnknown: if the version scheme is not found.

```python
commitizen.changelog_formats.base.get_version_scheme(settings: 'Settings', name: 'str | None' = None) -> 'VersionScheme'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `settings` | `Settings` | `—` | pos/kw |
| `name` | `str \| None` | `None` | pos/kw |

**Returns:** `VersionScheme`

### `commitizen_excepthook`

```python
commitizen.cli.commitizen_excepthook(exctype: 'type[BaseException]', value: 'BaseException', traceback: 'TracebackType | None', debug: 'bool' = False, no_raise: 'list[int] | None' = None) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `exctype` | `type[BaseException]` | `—` | pos/kw |
| `value` | `BaseException` | `—` | pos/kw |
| `traceback` | `TracebackType \| None` | `—` | pos/kw |
| `debug` | `bool` | `False` | pos/kw |
| `no_raise` | `list[int] \| None` | `None` | pos/kw |

### `main`

```python
commitizen.cli.main() -> 'None'
```

### `parse_no_raise`

Convert the given string to exit codes.

Receives digits and strings and outputs the parsed integer which
represents the exit code found in exceptions.

```python
commitizen.cli.parse_no_raise(comma_separated_no_raise: 'str') -> 'list[int]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `comma_separated_no_raise` | `str` | `—` | pos/kw |

**Returns:** `list[int]`

### `run`

```python
commitizen.cmd.run(cmd: 'str', env: 'Mapping[str, str] | None' = None) -> 'Command'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `cmd` | `str` | `—` | pos/kw |
| `env` | `Mapping[str, str] \| None` | `None` | pos/kw |

**Returns:** `Command`

### `get_changelog_format`

Get a format from its name

:raises FormatUnknown: if a non-empty name is provided but cannot be found in the known formats

```python
commitizen.commands.bump.get_changelog_format(config: 'BaseConfig', filename: 'str | None' = None) -> 'ChangelogFormat'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |
| `filename` | `str \| None` | `None` | pos/kw |

**Returns:** `ChangelogFormat`

### `get_provider`

Get the version provider as defined in the configuration

:raises VersionProviderUnknown: if the provider named by `version_provider` is not found.

```python
commitizen.commands.bump.get_provider(config: 'BaseConfig') -> 'VersionProvider'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `config` | `BaseConfig` | `—` | pos/kw |

**Returns:** `VersionProvider`

### `get_version_scheme`

Get the version scheme as defined in the configuration
or from an overridden `name`.



:raises VersionSchemeUnknown: if the version scheme is not found.

```python
commitizen.commands.bump.get_version_scheme(settings: 'Settings', name: 'str | None' = None) -> 'VersionScheme'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `settings` | `Settings` | `—` | pos/kw |
| `name` | `str \| None` | `None` | pos/kw |

**Returns:** `VersionScheme`

## Methods

### `commitizen.BaseCommitizen` methods

### `example`

Example of the commit message.

```python
commitizen.BaseCommitizen.example(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `format_exception_message`

Format commit errors.

```python
commitizen.BaseCommitizen.format_exception_message(self, invalid_commits: 'list[tuple[git.GitCommit, list]]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `invalid_commits` | `list[tuple[git.GitCommit, list]]` | `—` | pos/kw |

**Returns:** `str`

### `info`

Information about the standardized commit message.

```python
commitizen.BaseCommitizen.info(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `message`

Format your git message.

```python
commitizen.BaseCommitizen.message(self, answers: 'Mapping[str, Any]') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `answers` | `Mapping[str, Any]` | `—` | pos/kw |

**Returns:** `str`

### `questions`

Questions regarding the commit message.

```python
commitizen.BaseCommitizen.questions(self) -> 'list[CzQuestion]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `list[CzQuestion]`

### `schema`

Schema definition of the commit message.

```python
commitizen.BaseCommitizen.schema(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `schema_pattern`

Regex matching the schema used for message validation.

```python
commitizen.BaseCommitizen.schema_pattern(self) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `str`

### `validate_commit_message`

Validate commit message against the pattern.

```python
commitizen.BaseCommitizen.validate_commit_message(self, *, commit_msg: 'str', pattern: 're.Pattern[str]', allow_abort: 'bool', allowed_prefixes: 'list[str]', max_msg_length: 'int | None', commit_hash: 'str') -> 'ValidationResult'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `commit_msg` | `str` | `—` | kw |
| `pattern` | `re.Pattern[str]` | `—` | kw |
| `allow_abort` | `bool` | `—` | kw |
| `allowed_prefixes` | `list[str]` | `—` | kw |
| `max_msg_length` | `int \| None` | `—` | kw |
| `commit_hash` | `str` | `—` | kw |

**Returns:** `ValidationResult`

### `commitizen.bump.GitCommit` methods

### `from_rev_and_commit`

Create a GitCommit instance from a formatted commit string.

This method parses a multi-line string containing commit information in the following format:
```
<rev>
<parents>
<title>
<author>
<author…

```python
commitizen.bump.GitCommit.from_rev_and_commit(rev_and_commit: 'str') -> 'GitCommit'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `rev_and_commit` | `str` | `—` | pos/kw |

**Returns:** `GitCommit`

### `commitizen.changelog.TagRules` methods

### `extract_version`

Extract a version from the tag as defined in tag formats.

Raises `InvalidVersion` if the tag does not match any format.

```python
commitizen.changelog.TagRules.extract_version(self, tag: 'GitTag') -> 'Version'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `GitTag` | `—` | pos/kw |

**Returns:** `Version`

### `find_tag_for`

Find the first matching tag for a given version.

```python
commitizen.changelog.TagRules.find_tag_for(self, tags: 'Iterable[GitTag]', version: 'Version | str') -> 'GitTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tags` | `Iterable[GitTag]` | `—` | pos/kw |
| `version` | `Version \| str` | `—` | pos/kw |

**Returns:** `GitTag | None`

### `from_settings`

Extract tag rules from settings

```python
commitizen.changelog.TagRules.from_settings(settings: 'Settings') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `settings` | `Settings` | `—` | pos/kw |

**Returns:** `Self`

### `get_version_tags`

Filter in version tags and warn on unexpected tags

```python
commitizen.changelog.TagRules.get_version_tags(self, tags: 'Iterable[GitTag]', warn: 'bool' = False) -> 'list[GitTag]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tags` | `Iterable[GitTag]` | `—` | pos/kw |
| `warn` | `bool` | `False` | pos/kw |

**Returns:** `list[GitTag]`

### `include_in_changelog`

Check if a tag should be included in the changelog

```python
commitizen.changelog.TagRules.include_in_changelog(self, tag: 'GitTag') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `GitTag` | `—` | pos/kw |

**Returns:** `bool`

### `is_ignored_tag`

True if a given tag can be ignored

```python
commitizen.changelog.TagRules.is_ignored_tag(self, tag: 'str | GitTag') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `str \| GitTag` | `—` | pos/kw |

**Returns:** `bool`

### `is_version_tag`

True if a given tag is a legit version tag.

if `warn` is `True`, it will print a warning message if the tag is not a version tag.

```python
commitizen.changelog.TagRules.is_version_tag(self, tag: 'str | GitTag', warn: 'bool' = False) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `str \| GitTag` | `—` | pos/kw |
| `warn` | `bool` | `False` | pos/kw |

**Returns:** `bool`

### `normalize_tag`

The tag and the software version might be different.

That's why this function exists.

Example:
| tag | version (PEP 0440) |
| --- | ------- |
| v0.9.0 | 0.9.0 |
| ver1.0.0 | 1.0.0 |
| ver1.0.0.a0 |…

```python
commitizen.changelog.TagRules.normalize_tag(self, version: 'Version | str', tag_format: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `version` | `Version \| str` | `—` | pos/kw |
| `tag_format` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `search_version`

Search the first or last version tag occurrence in text.

It searches for complete versions only (aka `major`, `minor` and `patch`)

```python
commitizen.changelog.TagRules.search_version(self, text: 'str', last: 'bool' = False) -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |
| `last` | `bool` | `False` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.changelog_formats.ChangelogFormat` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.ChangelogFormat.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.ChangelogFormat.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `commitizen.changelog_formats.asciidoc.AsciiDoc` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.asciidoc.AsciiDoc.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_latest_full_release_from_file`

```python
commitizen.changelog_formats.asciidoc.AsciiDoc.get_latest_full_release_from_file(self, file: 'IO[Any]') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.asciidoc.AsciiDoc.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `get_metadata_from_file`

```python
commitizen.changelog_formats.asciidoc.AsciiDoc.get_metadata_from_file(self, file: 'IO[Any]') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `Metadata`

### `parse_title_level`

Get the title level/type of a line if any

```python
commitizen.changelog_formats.asciidoc.AsciiDoc.parse_title_level(self, line: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `parse_version_from_title`

Extract the version from a title line if any

```python
commitizen.changelog_formats.asciidoc.AsciiDoc.parse_version_from_title(self, line: 'str') -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.changelog_formats.asciidoc.BaseFormat` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.asciidoc.BaseFormat.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_latest_full_release_from_file`

```python
commitizen.changelog_formats.asciidoc.BaseFormat.get_latest_full_release_from_file(self, file: 'IO[Any]') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.asciidoc.BaseFormat.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `get_metadata_from_file`

```python
commitizen.changelog_formats.asciidoc.BaseFormat.get_metadata_from_file(self, file: 'IO[Any]') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `Metadata`

### `parse_title_level`

Get the title level/type of a line if any

```python
commitizen.changelog_formats.asciidoc.BaseFormat.parse_title_level(self, line: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `parse_version_from_title`

Extract the version from a title line if any

```python
commitizen.changelog_formats.asciidoc.BaseFormat.parse_version_from_title(self, line: 'str') -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.changelog_formats.base.BaseConfig` methods

### `contains_commitizen_section`

Check if the config file contains a commitizen section.

The implementation is different for each config file type.

```python
commitizen.changelog_formats.base.BaseConfig.contains_commitizen_section(self) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

**Returns:** `bool`

### `init_empty_config_content`

Create a config file with the empty config content.

The implementation is different for each config file type.

```python
commitizen.changelog_formats.base.BaseConfig.init_empty_config_content(self) -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `set_key`

Set or update a key in the config file.

Currently, only strings are supported for the parameter key.

```python
commitizen.changelog_formats.base.BaseConfig.set_key(self, key: 'str', value: 'object') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `key` | `str` | `—` | pos/kw |
| `value` | `object` | `—` | pos/kw |

**Returns:** `Self`

### `update`

```python
commitizen.changelog_formats.base.BaseConfig.update(self, data: 'Settings') -> 'None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `data` | `Settings` | `—` | pos/kw |

### `commitizen.changelog_formats.base.BaseFormat` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.base.BaseFormat.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_latest_full_release_from_file`

```python
commitizen.changelog_formats.base.BaseFormat.get_latest_full_release_from_file(self, file: 'IO[Any]') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.base.BaseFormat.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `get_metadata_from_file`

```python
commitizen.changelog_formats.base.BaseFormat.get_metadata_from_file(self, file: 'IO[Any]') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `Metadata`

### `parse_title_level`

Get the title level/type of a line if any

```python
commitizen.changelog_formats.base.BaseFormat.parse_title_level(self, line: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `parse_version_from_title`

Extract the version from a title line if any

```python
commitizen.changelog_formats.base.BaseFormat.parse_version_from_title(self, line: 'str') -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.changelog_formats.base.ChangelogFormat` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.base.ChangelogFormat.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.base.ChangelogFormat.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `commitizen.changelog_formats.base.GitTag` methods

### `from_line`

```python
commitizen.changelog_formats.base.GitTag.from_line(line: 'str', inner_delimiter: 'str') -> 'GitTag'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `str` | `—` | pos/kw |
| `inner_delimiter` | `str` | `—` | pos/kw |

**Returns:** `GitTag`

### `commitizen.changelog_formats.base.TagRules` methods

### `extract_version`

Extract a version from the tag as defined in tag formats.

Raises `InvalidVersion` if the tag does not match any format.

```python
commitizen.changelog_formats.base.TagRules.extract_version(self, tag: 'GitTag') -> 'Version'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `GitTag` | `—` | pos/kw |

**Returns:** `Version`

### `find_tag_for`

Find the first matching tag for a given version.

```python
commitizen.changelog_formats.base.TagRules.find_tag_for(self, tags: 'Iterable[GitTag]', version: 'Version | str') -> 'GitTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tags` | `Iterable[GitTag]` | `—` | pos/kw |
| `version` | `Version \| str` | `—` | pos/kw |

**Returns:** `GitTag | None`

### `from_settings`

Extract tag rules from settings

```python
commitizen.changelog_formats.base.TagRules.from_settings(settings: 'Settings') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `settings` | `Settings` | `—` | pos/kw |

**Returns:** `Self`

### `get_version_tags`

Filter in version tags and warn on unexpected tags

```python
commitizen.changelog_formats.base.TagRules.get_version_tags(self, tags: 'Iterable[GitTag]', warn: 'bool' = False) -> 'list[GitTag]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tags` | `Iterable[GitTag]` | `—` | pos/kw |
| `warn` | `bool` | `False` | pos/kw |

**Returns:** `list[GitTag]`

### `include_in_changelog`

Check if a tag should be included in the changelog

```python
commitizen.changelog_formats.base.TagRules.include_in_changelog(self, tag: 'GitTag') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `GitTag` | `—` | pos/kw |

**Returns:** `bool`

### `is_ignored_tag`

True if a given tag can be ignored

```python
commitizen.changelog_formats.base.TagRules.is_ignored_tag(self, tag: 'str | GitTag') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `str \| GitTag` | `—` | pos/kw |

**Returns:** `bool`

### `is_version_tag`

True if a given tag is a legit version tag.

if `warn` is `True`, it will print a warning message if the tag is not a version tag.

```python
commitizen.changelog_formats.base.TagRules.is_version_tag(self, tag: 'str | GitTag', warn: 'bool' = False) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `str \| GitTag` | `—` | pos/kw |
| `warn` | `bool` | `False` | pos/kw |

**Returns:** `bool`

### `normalize_tag`

The tag and the software version might be different.

That's why this function exists.

Example:
| tag | version (PEP 0440) |
| --- | ------- |
| v0.9.0 | 0.9.0 |
| ver1.0.0 | 1.0.0 |
| ver1.0.0.a0 |…

```python
commitizen.changelog_formats.base.TagRules.normalize_tag(self, version: 'Version | str', tag_format: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `version` | `Version \| str` | `—` | pos/kw |
| `tag_format` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `search_version`

Search the first or last version tag occurrence in text.

It searches for complete versions only (aka `major`, `minor` and `patch`)

```python
commitizen.changelog_formats.base.TagRules.search_version(self, text: 'str', last: 'bool' = False) -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |
| `last` | `bool` | `False` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.changelog_formats.markdown.BaseFormat` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.markdown.BaseFormat.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_latest_full_release_from_file`

```python
commitizen.changelog_formats.markdown.BaseFormat.get_latest_full_release_from_file(self, file: 'IO[Any]') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.markdown.BaseFormat.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `get_metadata_from_file`

```python
commitizen.changelog_formats.markdown.BaseFormat.get_metadata_from_file(self, file: 'IO[Any]') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `Metadata`

### `parse_title_level`

Get the title level/type of a line if any

```python
commitizen.changelog_formats.markdown.BaseFormat.parse_title_level(self, line: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `parse_version_from_title`

Extract the version from a title line if any

```python
commitizen.changelog_formats.markdown.BaseFormat.parse_version_from_title(self, line: 'str') -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.changelog_formats.markdown.Markdown` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.markdown.Markdown.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_latest_full_release_from_file`

```python
commitizen.changelog_formats.markdown.Markdown.get_latest_full_release_from_file(self, file: 'IO[Any]') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.markdown.Markdown.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `get_metadata_from_file`

```python
commitizen.changelog_formats.markdown.Markdown.get_metadata_from_file(self, file: 'IO[Any]') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `Metadata`

### `parse_title_level`

Get the title level/type of a line if any

```python
commitizen.changelog_formats.markdown.Markdown.parse_title_level(self, line: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `parse_version_from_title`

Extract the version from a title line if any

```python
commitizen.changelog_formats.markdown.Markdown.parse_version_from_title(self, line: 'str') -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.changelog_formats.restructuredtext.BaseFormat` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.restructuredtext.BaseFormat.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_latest_full_release_from_file`

```python
commitizen.changelog_formats.restructuredtext.BaseFormat.get_latest_full_release_from_file(self, file: 'IO[Any]') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.restructuredtext.BaseFormat.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `get_metadata_from_file`

```python
commitizen.changelog_formats.restructuredtext.BaseFormat.get_metadata_from_file(self, file: 'IO[Any]') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `Metadata`

### `parse_title_level`

Get the title level/type of a line if any

```python
commitizen.changelog_formats.restructuredtext.BaseFormat.parse_title_level(self, line: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `parse_version_from_title`

Extract the version from a title line if any

```python
commitizen.changelog_formats.restructuredtext.BaseFormat.parse_version_from_title(self, line: 'str') -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.changelog_formats.restructuredtext.RestructuredText` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.restructuredtext.RestructuredText.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_latest_full_release_from_file`

```python
commitizen.changelog_formats.restructuredtext.RestructuredText.get_latest_full_release_from_file(self, file: 'IO[Any]') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.restructuredtext.RestructuredText.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `get_metadata_from_file`

RestructuredText section titles are not one-line-based,
they spread on 2 or 3 lines and levels are not predefined
but determined by their occurrence order.

It requires its own algorithm.

For a more…

```python
commitizen.changelog_formats.restructuredtext.RestructuredText.get_metadata_from_file(self, file: 'IO[str]') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[str]` | `—` | pos/kw |

**Returns:** `Metadata`

### `parse_title_level`

Get the title level/type of a line if any

```python
commitizen.changelog_formats.restructuredtext.RestructuredText.parse_title_level(self, line: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `parse_version_from_title`

Extract the version from a title line if any

```python
commitizen.changelog_formats.restructuredtext.RestructuredText.parse_version_from_title(self, line: 'str') -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.changelog_formats.textile.BaseFormat` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.textile.BaseFormat.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_latest_full_release_from_file`

```python
commitizen.changelog_formats.textile.BaseFormat.get_latest_full_release_from_file(self, file: 'IO[Any]') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.textile.BaseFormat.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `get_metadata_from_file`

```python
commitizen.changelog_formats.textile.BaseFormat.get_metadata_from_file(self, file: 'IO[Any]') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `Metadata`

### `parse_title_level`

Get the title level/type of a line if any

```python
commitizen.changelog_formats.textile.BaseFormat.parse_title_level(self, line: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `parse_version_from_title`

Extract the version from a title line if any

```python
commitizen.changelog_formats.textile.BaseFormat.parse_version_from_title(self, line: 'str') -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.changelog_formats.textile.Textile` methods

### `get_latest_full_release`

Extract metadata for the last non-pre-release.

```python
commitizen.changelog_formats.textile.Textile.get_latest_full_release(self, filepath: 'str') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_latest_full_release_from_file`

```python
commitizen.changelog_formats.textile.Textile.get_latest_full_release_from_file(self, file: 'IO[Any]') -> 'IncrementalMergeInfo'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `IncrementalMergeInfo`

### `get_metadata`

Extract the changelog metadata.

```python
commitizen.changelog_formats.textile.Textile.get_metadata(self, filepath: 'str') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filepath` | `str` | `—` | pos/kw |

**Returns:** `Metadata`

### `get_metadata_from_file`

```python
commitizen.changelog_formats.textile.Textile.get_metadata_from_file(self, file: 'IO[Any]') -> 'Metadata'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `file` | `IO[Any]` | `—` | pos/kw |

**Returns:** `Metadata`

### `parse_title_level`

Get the title level/type of a line if any

```python
commitizen.changelog_formats.textile.Textile.parse_title_level(self, line: 'str') -> 'int | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `int | None`

### `parse_version_from_title`

Extract the version from a title line if any

```python
commitizen.changelog_formats.textile.Textile.parse_version_from_title(self, line: 'str') -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `line` | `str` | `—` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.cli.ParseKwargs` methods

### `format_usage`

```python
commitizen.cli.ParseKwargs.format_usage(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `commitizen.commands.Commit` methods

### `manual_edit`

```python
commitizen.commands.Commit.manual_edit(self, message: 'str') -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `str` | `—` | pos/kw |

**Returns:** `str`

### `commitizen.commands.bump.TagRules` methods

### `extract_version`

Extract a version from the tag as defined in tag formats.

Raises `InvalidVersion` if the tag does not match any format.

```python
commitizen.commands.bump.TagRules.extract_version(self, tag: 'GitTag') -> 'Version'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `GitTag` | `—` | pos/kw |

**Returns:** `Version`

### `find_tag_for`

Find the first matching tag for a given version.

```python
commitizen.commands.bump.TagRules.find_tag_for(self, tags: 'Iterable[GitTag]', version: 'Version | str') -> 'GitTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tags` | `Iterable[GitTag]` | `—` | pos/kw |
| `version` | `Version \| str` | `—` | pos/kw |

**Returns:** `GitTag | None`

### `from_settings`

Extract tag rules from settings

```python
commitizen.commands.bump.TagRules.from_settings(settings: 'Settings') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `settings` | `Settings` | `—` | pos/kw |

**Returns:** `Self`

### `get_version_tags`

Filter in version tags and warn on unexpected tags

```python
commitizen.commands.bump.TagRules.get_version_tags(self, tags: 'Iterable[GitTag]', warn: 'bool' = False) -> 'list[GitTag]'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tags` | `Iterable[GitTag]` | `—` | pos/kw |
| `warn` | `bool` | `False` | pos/kw |

**Returns:** `list[GitTag]`

### `include_in_changelog`

Check if a tag should be included in the changelog

```python
commitizen.commands.bump.TagRules.include_in_changelog(self, tag: 'GitTag') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `GitTag` | `—` | pos/kw |

**Returns:** `bool`

### `is_ignored_tag`

True if a given tag can be ignored

```python
commitizen.commands.bump.TagRules.is_ignored_tag(self, tag: 'str | GitTag') -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `str \| GitTag` | `—` | pos/kw |

**Returns:** `bool`

### `is_version_tag`

True if a given tag is a legit version tag.

if `warn` is `True`, it will print a warning message if the tag is not a version tag.

```python
commitizen.commands.bump.TagRules.is_version_tag(self, tag: 'str | GitTag', warn: 'bool' = False) -> 'bool'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `str \| GitTag` | `—` | pos/kw |
| `warn` | `bool` | `False` | pos/kw |

**Returns:** `bool`

### `normalize_tag`

The tag and the software version might be different.

That's why this function exists.

Example:
| tag | version (PEP 0440) |
| --- | ------- |
| v0.9.0 | 0.9.0 |
| ver1.0.0 | 1.0.0 |
| ver1.0.0.a0 |…

```python
commitizen.commands.bump.TagRules.normalize_tag(self, version: 'Version | str', tag_format: 'str | None' = None) -> 'str'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `version` | `Version \| str` | `—` | pos/kw |
| `tag_format` | `str \| None` | `None` | pos/kw |

**Returns:** `str`

### `search_version`

Search the first or last version tag occurrence in text.

It searches for complete versions only (aka `major`, `minor` and `patch`)

```python
commitizen.commands.bump.TagRules.search_version(self, text: 'str', last: 'bool' = False) -> 'VersionTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `str` | `—` | pos/kw |
| `last` | `bool` | `False` | pos/kw |

**Returns:** `VersionTag | None`

### `commitizen.commands.bump.VersionProtocol` methods

### `bump`

Based on the given increment, generate the next bumped version according to the version scheme

Args:
    increment: The component to increase
    prerelease: The type of prerelease, if Any
    is_lo…

```python
commitizen.commands.bump.VersionProtocol.bump(self, increment: 'Increment | None', prerelease: 'Prerelease | None' = None, prerelease_offset: 'int' = 0, devrelease: 'int | None' = None, is_local_version: 'bool' = False, build_metadata: 'str | None' = None, exact_increment: 'bool' = False) -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `increment` | `Increment \| None` | `—` | pos/kw |
| `prerelease` | `Prerelease \| None` | `None` | pos/kw |
| `prerelease_offset` | `int` | `0` | pos/kw |
| `devrelease` | `int \| None` | `None` | pos/kw |
| `is_local_version` | `bool` | `False` | pos/kw |
| `build_metadata` | `str \| None` | `None` | pos/kw |
| `exact_increment` | `bool` | `False` | pos/kw |

**Returns:** `Self`

### `commitizen.commands.changelog.GitTag` methods

### `from_line`

```python
commitizen.commands.changelog.GitTag.from_line(line: 'str', inner_delimiter: 'str') -> 'GitTag'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `line` | `str` | `—` | pos/kw |
| `inner_delimiter` | `str` | `—` | pos/kw |

**Returns:** `GitTag`

### `commitizen.commands.changelog.TagRules` methods

### `extract_version`

Extract a version from the tag as defined in tag formats.

Raises `InvalidVersion` if the tag does not match any format.

```python
commitizen.commands.changelog.TagRules.extract_version(self, tag: 'GitTag') -> 'Version'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tag` | `GitTag` | `—` | pos/kw |

**Returns:** `Version`

### `find_tag_for`

Find the first matching tag for a given version.

```python
commitizen.commands.changelog.TagRules.find_tag_for(self, tags: 'Iterable[GitTag]', version: 'Version | str') -> 'GitTag | None'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tags` | `Iterable[GitTag]` | `—` | pos/kw |
| `version` | `Version \| str` | `—` | pos/kw |

**Returns:** `GitTag | None`

### `from_settings`

Extract tag rules from settings

```python
commitizen.commands.changelog.TagRules.from_settings(settings: 'Settings') -> 'Self'
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `settings` | `Settings` | `—` | pos/kw |

**Returns:** `Self`


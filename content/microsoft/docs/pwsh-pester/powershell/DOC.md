---
name: pwsh-pester
description: "Pester 5.7 testing framework — Describe, It, Mock, Should, BeforeAll, AfterAll, InModuleScope, assertions, test configuration"
metadata:
  languages: "powershell"
  versions: "7.5"
  revision: 1
  updated-on: "2026-04-07"
  source: community
  tags: "powershell,pwsh,cmdlet,Add-AssertionOperator,Add-ShouldOperator,AfterAll,AfterEach,Assert-MockCalled,Assert-VerifiableMock,BeforeAll,BeforeDiscovery,BeforeEach,Context,ConvertTo-JUnitReport,ConvertTo-NUnitReport,ConvertTo-Pester4Result,Describe,Export-JUnitReport,Export-NUnitReport,Get-AssertionOperator,Get-ShouldOperator,InModuleScope,Invoke-Pester,It,Mock,New-Fixture,New-MockObject,New-PesterConfiguration,New-PesterContainer,Set-ItResult,Should"
---

# PowerShell 7.5 — Describe

## Cmdlet Quick Reference

| Cmdlet | Synopsis |
|--------|----------|
| `Add-AssertionOperator` | Register a Should Operator with Pester |
| `Add-ShouldOperator` | Register a Should Operator with Pester |
| `AfterAll` | Defines a series of steps to perform at the end of the current container, Context or Describe block. |
| `AfterEach` | Defines a series of steps to perform at the end of every It block within the current Context or D... |
| `Assert-MockCalled` | Checks if a Mocked command has been called a certain number of times and throws an exception if i... |
| `Assert-VerifiableMock` | Checks if all verifiable Mocks has been called at least once.  THIS COMMAND IS OBSOLETE AND WILL ... |
| `BeforeAll` | Defines a series of steps to perform at the beginning of the current container, Context or Descri... |
| `BeforeDiscovery` | Runs setup code that is used during Discovery phase. |
| `BeforeEach` | Defines a series of steps to perform at the beginning of every It block within the current Contex... |
| `Context` | Provides logical grouping of It blocks within a single Describe block. |
| `ConvertTo-JUnitReport` | Converts a Pester result-object to an JUnit-compatible XML report |
| `ConvertTo-NUnitReport` | Converts a Pester result-object to an NUnit 2.5 or 3-compatible XML-report |
| `ConvertTo-Pester4Result` | Converts a Pester 5 result-object to an Pester 4-compatible object |
| `Describe` | Creates a logical group of tests. |
| `Export-JUnitReport` | Exports a Pester result-object to an JUnit-compatible XML-report |
| `Export-NUnitReport` | Exports a Pester result-object to an NUnit-compatible XML-report |
| `Get-AssertionOperator` | Display the assertion operators available for use with Should. |
| `Get-ShouldOperator` | Display the assertion operators available for use with Should. |
| `InModuleScope` | Allows you to execute parts of a test script within the scope of a PowerShell script or manifest ... |
| `Invoke-Pester` | Runs Pester tests |
| `It` | Validates the results of a test inside of a Describe block. |
| `Mock` | Mocks the behavior of an existing command with an alternate implementation. |
| `New-Fixture` | This function generates two scripts, one that defines a function and another one that contains it... |
| `New-MockObject` | This function instantiates a .NET object from a type. |
| `New-PesterConfiguration` | Creates a new PesterConfiguration object for advanced configuration of Invoke-Pester. |
| `New-PesterContainer` | Generates ContainerInfo-objects used as for Invoke-Pester -Container |
| `Set-ItResult` | Set-ItResult is used inside the It block to explicitly set the test result |
| `Should` | Should is a keyword that is used to define an assertion inside an It block. |

---

### Add-AssertionOperator

Register a Should Operator with Pester

This function allows you to create custom Should assertions.

**Returns**: `None documented`

```
Add-AssertionOperator
    -Name <String>
    -Test <ScriptBlock>
    [-Alias <String[]>]
    [-InternalName <String>]
    [-SupportsArrayInput]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | Yes | The name of the assertion. This will become a Named Parameter of Should. |
| `-Test` | `ScriptBlock` | Yes | The test function. The function must return a PSObject with a [Bool]succeeded and a [string]failureMessage property. |
| `-Alias` | `String[]` | No | A list of aliases for the Named Parameter. |
| `-InternalName` | `String` | No | If -Name is different from the actual function name, record the actual function name here. Used by Get-ShouldOperator to pull function help. |
| `-SupportsArrayInput` | `SwitchParameter` | No | Does the test function support the passing an array of values to test. |

---

### Add-ShouldOperator

Register a Should Operator with Pester

This function allows you to create custom Should assertions.

**Returns**: `None documented`

```
Add-ShouldOperator
    -Name <String>
    -Test <ScriptBlock>
    [-Alias <String[]>]
    [-InternalName <String>]
    [-SupportsArrayInput]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | Yes | The name of the assertion. This will become a Named Parameter of Should. |
| `-Test` | `ScriptBlock` | Yes | The test function. The function must return a PSObject with a [Bool]succeeded and a [string]failureMessage property. |
| `-Alias` | `String[]` | No | A list of aliases for the Named Parameter. |
| `-InternalName` | `String` | No | If -Name is different from the actual function name, record the actual function name here. Used by Get-ShouldOperator to pull function help. |
| `-SupportsArrayInput` | `SwitchParameter` | No | Does the test function support the passing an array of values to test. |

---

### AfterAll

Defines a series of steps to perform at the end of the current container,
Context or Describe block.

AfterAll is used to share teardown after all the tests in a container, Describe
or Context including all child blocks and tests. AfterAll runs during Run phase
and runs only once in the current block. It's guaranteed to run even if tests
fail.

**Returns**: `None documented`

```
AfterAll
    -Scriptblock <ScriptBlock>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Scriptblock` | `ScriptBlock` | Yes | A scriptblock with steps to be executed during teardown. |

---

### AfterEach

Defines a series of steps to perform at the end of every It block within
the current Context or Describe block.

AfterEach runs once after every test in the current or any child blocks.
Typically this is used to clean up resources created by the test or its setups.
AfterEach runs in a finally block, and is guaranteed to run even if the test
(or setup) fails.

**Returns**: `None documented`

```
AfterEach
    -Scriptblock <ScriptBlock>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Scriptblock` | `ScriptBlock` | Yes | A scriptblock with steps to be executed during teardown. |

---

### Assert-MockCalled

Checks if a Mocked command has been called a certain number of times
and throws an exception if it has not.

THIS COMMAND IS OBSOLETE AND WILL BE REMOVED SOMEWHERE DURING v5 LIFETIME,
USE Should -Invoke INSTEAD.

**Returns**: `None documented`

```
Assert-MockCalled
    -CommandName <String>
    [-Times <Int32>]
    [-ParameterFilter <ScriptBlock>]
    -ExclusiveFilter <ScriptBlock>
    [-ModuleName <String>]
    [-Scope <String>]
    [-Exactly]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CommandName` | `String` | Yes |  |
| `-Times` | `Int32` | No |  |
| `-ParameterFilter` | `ScriptBlock` | No |  |
| `-ExclusiveFilter` | `ScriptBlock` | Yes |  |
| `-ModuleName` | `String` | No |  |
| `-Scope` | `String` | No |  |
| `-Exactly` | `SwitchParameter` | No |  |

---

### Assert-VerifiableMock

Checks if all verifiable Mocks has been called at least once.

THIS COMMAND IS OBSOLETE AND WILL BE REMOVED SOMEWHERE DURING v5 LIFETIME,
USE Should -InvokeVerifiable INSTEAD.

**Returns**: `None documented`

```
Assert-VerifiableMock
```

---

### BeforeAll

Defines a series of steps to perform at the beginning of the current container,
Context or Describe block.

BeforeAll is used to share setup among all the tests in a container, Describe
or Context including all child blocks and tests. BeforeAll runs during Run phase
and runs only once in the current level.

**Returns**: `None documented`

```
BeforeAll
    -Scriptblock <ScriptBlock>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Scriptblock` | `ScriptBlock` | Yes | A scriptblock with steps to be executed during setup. |

---

### BeforeDiscovery

Runs setup code that is used during Discovery phase.

Runs your code as is, in the place where this function is defined. This is a semantic block to allow you
to be explicit about code that you need to run during Discovery, instead of just
putting code directly inside of Describe / Context.

**Returns**: `None documented`

```
BeforeDiscovery
    -ScriptBlock <ScriptBlock>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ScriptBlock` | `ScriptBlock` | Yes | The ScriptBlock to run. |

---

### BeforeEach

Defines a series of steps to perform at the beginning of every It block within
the current Context or Describe block.

BeforeEach runs once before every test in the current or any child blocks.
Typically this is used to create all the prerequisites for the current test,
such as writing content to a file.

**Returns**: `None documented`

```
BeforeEach
    -Scriptblock <ScriptBlock>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Scriptblock` | `ScriptBlock` | Yes | A scriptblock with steps to be executed during setup. |

---

### Context

Provides logical grouping of It blocks within a single Describe block.

Provides logical grouping of It blocks within a single Describe block.
Any Mocks defined inside a Context are removed at the end of the Context scope,
as are any files or folders added to the TestDrive during the Context block's
execution. Any BeforeEach or AfterEach blocks defined inside a Context also only
apply to tests within that Context .

**Returns**: `None documented`

```
Context
    -Name <String>
    [-Tag <String[]>]
    [-Fixture <ScriptBlock>]
    [-Skip]
    [-ForEach <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | Yes | The name of the Context. This is a phrase describing a set of tests within a describe. |
| `-Tag` | `String[]` | No | Optional parameter containing an array of strings. When calling Invoke-Pester, it is possible to specify a -Tag parameter which will only execute Context blocks containing the same Tag. |
| `-Fixture` | `ScriptBlock` | No | Script that is executed. This may include setup specific to the context and one or more It blocks that validate the expected outcomes. |
| `-Skip` | `SwitchParameter` | No | Use this parameter to explicitly mark the block to be skipped. This is preferable to temporarily commenting out a block, because it remains listed in the output. |
| `-ForEach` | `Object` | No | Allows data driven tests to be written. Takes an array of data and generates one block for each item in the array, and makes the item available as $_ in all child blocks. When the array is an array... |

---

### ConvertTo-JUnitReport

Converts a Pester result-object to an JUnit-compatible XML report

Pester can generate a result-object containing information about all
tests that are processed in a run. This objects can then be converted to an
NUnit-compatible XML-report using this function. The report is generated
using the JUnit 4-schema.

**Returns**: `None documented`

```
ConvertTo-JUnitReport
    -Result <Run>
    [-AsString]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Result` | `Run` | Yes | Result object from a Pester-run. This can be retrieved using Invoke-Pester -Passthru or by using the Run.PassThru configuration-option. |
| `-AsString` | `SwitchParameter` | No | Returns the XML-report as a string. |

---

### ConvertTo-NUnitReport

Converts a Pester result-object to an NUnit 2.5 or 3-compatible XML-report

Pester can generate a result-object containing information about all
tests that are processed in a run. This objects can then be converted to an
NUnit-compatible XML-report using this function. The report is generated
using either the NUnit 2.5 or 3-schema.

**Returns**: `None documented`

```
ConvertTo-NUnitReport
    -Result <Run>
    [-AsString]
    [-Format <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Result` | `Run` | Yes | Result object from a Pester-run. This can be retrieved using Invoke-Pester -Passthru or by using the Run.PassThru configuration-option. |
| `-AsString` | `SwitchParameter` | No | Returns the XML-report as a string. |
| `-Format` | `String` | No | Specifies the NUnit-schema to be used. |

---

### ConvertTo-Pester4Result

Converts a Pester 5 result-object to an Pester 4-compatible object

Pester 5 uses a new format for it's result-object compared to previous
versions of Pester. This function is provided as a way to convert the
result-object into an object using the previous format. This can be
useful as a temporary measure to easier migrate to Pester 5 without
having to redesign complex CI/CD-pipelines.

**Returns**: `None documented`

```
ConvertTo-Pester4Result
    -PesterResult <Object>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-PesterResult` | `Object` | Yes | Result object from a Pester 5-run. This can be retrieved using Invoke-Pester -Passthru or by using the Run.PassThru configuration-option. |

---

### Describe

Creates a logical group of tests.

Creates a logical group of tests. All Mocks, TestDrive and TestRegistry contents
defined within a Describe block are scoped to that Describe; they
will no longer be present when the Describe block exits.  A Describe
block may contain any number of Context and It blocks.

**Returns**: `None documented`

```
Describe
    -Name <String>
    [-Tag <String[]>]
    [-Fixture <ScriptBlock>]
    [-Skip]
    [-ForEach <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | Yes | The name of the test group. This is often an expressive phrase describing the scenario being tested. |
| `-Tag` | `String[]` | No | Optional parameter containing an array of strings. When calling Invoke-Pester, it is possible to specify a -Tag parameter which will only execute Describe blocks containing the same Tag. |
| `-Fixture` | `ScriptBlock` | No | The actual test script. If you are following the AAA pattern (Arrange-Act-Assert), this typically holds the arrange and act sections. The Asserts will also lie in this block but are typically neste... |
| `-Skip` | `SwitchParameter` | No | Use this parameter to explicitly mark the block to be skipped. This is preferable to temporarily commenting out a block, because it remains listed in the output. |
| `-ForEach` | `Object` | No | Allows data driven tests to be written. Takes an array of data and generates one block for each item in the array, and makes the item available as $_ in all child blocks. When the array is an array... |

---

### Export-JUnitReport

Exports a Pester result-object to an JUnit-compatible XML-report

Pester can generate a result-object containing information about all
tests that are processed in a run. This object can then be exported to an
JUnit-compatible XML-report using this function. The report is generated
using the JUnit 4-schema.

**Returns**: `None documented`

```
Export-JUnitReport
    -Result <Run>
    -Path <String>
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Result` | `Run` | Yes | Result object from a Pester-run. This can be retrieved using Invoke-Pester -Passthru or by using the Run.PassThru configuration-option. |
| `-Path` | `String` | Yes | The path where the XML-report should be saved. |

---

### Export-NUnitReport

Exports a Pester result-object to an NUnit-compatible XML-report

Pester can generate a result-object containing information about all
tests that are processed in a run. This object can then be exported to an
NUnit-compatible XML-report using this function. The report is generated
using the NUnit 2.5-schema (default) or NUnit3-compatible format.

**Returns**: `None documented`

```
Export-NUnitReport
    -Result <Run>
    -Path <String>
    [-Format <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Result` | `Run` | Yes | Result object from a Pester-run. This can be retrieved using Invoke-Pester -Passthru or by using the Run.PassThru configuration-option. |
| `-Path` | `String` | Yes | The path where the XML-report should be saved. |
| `-Format` | `String` | No | Specifies the NUnit-schema to be used. |

---

### Get-AssertionOperator

Display the assertion operators available for use with Should.

Get-ShouldOperator returns a list of available Should parameters,
their aliases, and examples to help you craft the tests you need.

**Returns**: `None documented`

```
Get-AssertionOperator
```

---

### Get-ShouldOperator

Display the assertion operators available for use with Should.

Get-ShouldOperator returns a list of available Should parameters,
their aliases, and examples to help you craft the tests you need.

**Returns**: `None documented`

```
Get-ShouldOperator
```

---

### InModuleScope

Allows you to execute parts of a test script within the
scope of a PowerShell script or manifest module.

By injecting some test code into the scope of a PowerShell
script or manifest module, you can use non-exported functions, aliases
and variables inside that module, to perform unit tests on
its internal implementation.

**Returns**: `None documented`

```
InModuleScope
    -ModuleName <String>
    -ScriptBlock <ScriptBlock>
    [-Parameters <Hashtable>]
    [-ArgumentList <Object[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ModuleName` | `String` | Yes | The name of the module into which the test code should be injected. This module must already be loaded into the current PowerShell session. |
| `-ScriptBlock` | `ScriptBlock` | Yes | The code to be executed within the script or manifest module. |
| `-Parameters` | `Hashtable` | No | A optional hashtable of parameters to be passed to the scriptblock. Parameters are automatically made available as variables in the scriptblock. |
| `-ArgumentList` | `Object[]` | No | A optional list of arguments to be passed to the scriptblock. |

---

### Invoke-Pester

Runs Pester tests

The Invoke-Pester function runs Pester tests, including *.Tests.ps1 files and
Pester tests in PowerShell scripts.

**Returns**: `None documented`

```
Invoke-Pester
    [-Path <String[]>]
    [-ExcludePath <String[]>]
    [-TagFilter <String[]>]
    [-ExcludeTagFilter <String[]>]
    [-FullNameFilter <String[]>]
    [-CI]
    [-Output <String>]
    [-PassThru]
    [-Container <ContainerInfo[]>]
    [-Configuration <PesterConfiguration>]
    [-EnableExit]
    [-CodeCoverage <Object[]>]
    [-CodeCoverageOutputFile <String>]
    [-CodeCoverageOutputFileEncoding <String>]
    [-CodeCoverageOutputFileFormat <String>]
    [-Strict]
    [-OutputFile <String>]
    [-OutputFormat <String>]
    [-Quiet]
    [-PesterOption <Object>]
    [-Show <OutputTypes>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Path` | `String[]` | No | Aliases Script Specifies one or more paths to files containing tests. The value is a path\file name or name pattern. Wildcards are permitted. |
| `-ExcludePath` | `String[]` | No | (Deprecated v4) Replace with ConfigurationProperty Run.ExcludePath |
| `-TagFilter` | `String[]` | No | (Deprecated v4) Aliases Tag, Tags Replace with ConfigurationProperty Filter.Tag |
| `-ExcludeTagFilter` | `String[]` | No | (Deprecated v4) Replace with ConfigurationProperty Filter.ExcludeTag |
| `-FullNameFilter` | `String[]` | No | (Deprecated v4) Replace with ConfigurationProperty Filter.FullName |
| `-CI` | `SwitchParameter` | No | (Introduced v5) Enable Test Results and Exit after Run.  Replace with ConfigurationProperty     TestResult.Enabled = $true     Run.Exit = $true  Since 5.2.0, this option no longer enables CodeCover... |
| `-Output` | `String` | No | (Deprecated v4) Replace with ConfigurationProperty Output.Verbosity Supports Diagnostic, Detailed, Normal, Minimal, None  Default value is: Normal |
| `-PassThru` | `SwitchParameter` | No | Replace with ConfigurationProperty Run.PassThru Returns a custom object (PSCustomObject) that contains the test results. By default, Invoke-Pester writes to the host program, not to the output stre... |
| `-Container` | `ContainerInfo[]` | No | Specifies one or more ContainerInfo-objects that define containers with tests. ContainerInfo-objects are generated using New-PesterContainer. Useful for scenarios where data-driven test are generat... |
| `-Configuration` | `PesterConfiguration` | No | [PesterConfiguration] object for Advanced Configuration created using `New-PesterConfiguration`. For help on each option see about_PesterConfiguration or inspect the object. |
| `-EnableExit` | `SwitchParameter` | No | (Deprecated v4) Replace with ConfigurationProperty Run.Exit Will cause Invoke-Pester to exit with a exit code equal to the number of failed tests once all tests have been run. Use this to "fail" a ... |
| `-CodeCoverage` | `Object[]` | No | (Deprecated v4) Replace with ConfigurationProperty CodeCoverage.Enabled = $true Adds a code coverage report to the Pester tests. Takes strings or hash table values. A code coverage report lists the... |
| `-CodeCoverageOutputFile` | `String` | No | (Deprecated v4) Replace with ConfigurationProperty CodeCoverage.OutputPath The path where Invoke-Pester will save formatted code coverage results file. The path must include the location and name o... |
| `-CodeCoverageOutputFileEncoding` | `String` | No | (Deprecated v4) Replace with ConfigurationProperty CodeCoverage.OutputEncoding Sets the output encoding of CodeCoverageOutputFileFormat Default is utf8 |
| `-CodeCoverageOutputFileFormat` | `String` | No | (Deprecated v4) Replace with ConfigurationProperty CodeCoverage.OutputFormat The name of a code coverage report file format. Default value is: JaCoCo. Currently supported formats are: - JaCoCo - th... |
| `-Strict` | `SwitchParameter` | No | (Deprecated v4) Makes Pending and Skipped tests to Failed tests. Useful for continuous integration where you need to make sure all tests passed. |
| `-OutputFile` | `String` | No | (Deprecated v4) Replace with ConfigurationProperty TestResult.OutputPath The path where Invoke-Pester will save formatted test results log file. The path must include the location and name of the f... |
| `-OutputFormat` | `String` | No | (Deprecated v4) Replace with ConfigurationProperty TestResult.OutputFormat The format of output. Currently NUnitXml and JUnitXml is supported. |
| `-Quiet` | `SwitchParameter` | No | (Deprecated v4) The parameter Quiet is deprecated since Pester v4.0 and will be deleted in the next major version of Pester. Please use the parameter Show with value 'None' instead. The parameter Q... |
| `-PesterOption` | `Object` | No | (Deprecated v4) This parameter is ignored in v5, and is only present for backwards compatibility when migrating from v4.  Sets advanced options for the test execution. Enter a PesterOption object, ... |
| `-Show` | `OutputTypes` | No | (Deprecated v4) Replace with ConfigurationProperty Output.Verbosity Customizes the output Pester writes to the screen. Available options are None, Default, Passed, Failed, Pending, Skipped, Inconcl... |

---

### It

Validates the results of a test inside of a Describe block.

The It command is intended to be used inside of a Describe or Context Block.
If you are familiar with the AAA pattern (Arrange-Act-Assert), the body of
the It block is the appropriate location for an assert. The convention is to
assert a single expectation for each It block. The code inside of the It block
should throw a terminating error if the expectation of the test is not met and
thus cause the test to fail. The name of the It block should expressively state
the expectation of the test.

**Returns**: `None documented`

```
It
    -Name <String>
    [-Test <ScriptBlock>]
    [-ForEach <Object[]>]
    [-Tag <String[]>]
    [-Pending]
    [-Skip]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | Yes | An expressive phrase describing the expected test outcome. |
| `-Test` | `ScriptBlock` | No | The script block that should throw an exception if the expectation of the test is not met.If you are following the AAA pattern (Arrange-Act-Assert), this typically holds the Assert. |
| `-ForEach` | `Object[]` | No | (Formerly called TestCases.) Optional array of hashtable (or any IDictionary) objects. If this parameter is used, Pester will call the test script block once for each table in the ForEach array, sp... |
| `-Tag` | `String[]` | No | Optional parameter containing an array of strings. When calling Invoke-Pester, it is possible to include or exclude tests containing the same Tag. |
| `-Pending` | `SwitchParameter` | No | Use this parameter to explicitly mark the test as work-in-progress/not implemented/pending when you need to distinguish a test that fails because it is not finished yet from a tests that fail as a ... |
| `-Skip` | `SwitchParameter` | No | Use this parameter to explicitly mark the test to be skipped. This is preferable to temporarily commenting out a test, because the test remains listed in the output. |

---

### Mock

Mocks the behavior of an existing command with an alternate
implementation.

This creates new behavior for any existing command within the scope of a
Describe or Context block. The function allows you to specify a script block
that will become the command's new behavior.

**Returns**: `None documented`

```
Mock
    [-CommandName <String>]
    [-MockWith <ScriptBlock>]
    [-Verifiable]
    [-ParameterFilter <ScriptBlock>]
    [-ModuleName <String>]
    [-RemoveParameterType <String[]>]
    [-RemoveParameterValidation <String[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-CommandName` | `String` | No | The name of the command to be mocked. |
| `-MockWith` | `ScriptBlock` | No | A ScriptBlock specifying the behavior that will be used to mock CommandName. The default is an empty ScriptBlock. NOTE: Do not specify param or dynamicparam blocks in this script block. These will ... |
| `-Verifiable` | `SwitchParameter` | No | When this is set, the mock will be checked when Should -InvokeVerifiable is called. |
| `-ParameterFilter` | `ScriptBlock` | No | An optional filter to limit mocking behavior only to usages of CommandName where the values of the parameters passed to the command pass the filter.  This ScriptBlock must return a boolean value. S... |
| `-ModuleName` | `String` | No | Optional string specifying the name of the module where this command is to be mocked.  This should be a module that _calls_ the mocked command; it doesn't necessarily have to be the same module whi... |
| `-RemoveParameterType` | `String[]` | No | Optional list of parameter names that should use Object as the parameter type instead of the parameter type defined by the function. This relaxes the type requirements and allows some strongly type... |
| `-RemoveParameterValidation` | `String[]` | No | Optional list of parameter names in the original command that should not have any validation rules applied. This relaxes the validation requirements, and allows functions that are strict about thei... |

---

### New-Fixture

This function generates two scripts, one that defines a function
and another one that contains its tests.

This function generates two scripts, one that defines a function
and another one that contains its tests. The files are by default
placed in the current directory and are called and populated as such:

**Returns**: `None documented`

```
New-Fixture
    -Name <String>
    [-Path <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Name` | `String` | Yes | Defines the name of the function and the name of the test to be created. |
| `-Path` | `String` | No | Defines path where the test and the function should be created, you can use full or relative path. If the parameter is not specified the scripts are created in the current directory. |

---

### New-MockObject

This function instantiates a .NET object from a type.

Using the New-MockObject you can mock an object based on .NET type.

**Returns**: `None documented`

```
New-MockObject
    -Type <Type>
    -InputObject <Object>
    [-Properties <Hashtable>]
    [-Methods <Hashtable>]
    [-MethodHistoryPrefix <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Type` | `Type` | Yes | The .NET type to create. This creates the object without calling any of its constructors or initializers. Use this to instantiate an object that does not have a public constructor. If your object h... |
| `-InputObject` | `Object` | Yes | An already constructed object to decorate. Use `New-Object` or `[typeName]::new()` to create it. |
| `-Properties` | `Hashtable` | No | Properties to define, specified as a hashtable, in format `@{ PropertyName = value }`. |
| `-Methods` | `Hashtable` | No | Methods to define, specified as a hashtable, in format `@{ MethodName = scriptBlock }`.  ScriptBlock can define param block, and it will receive arguments that were provided to the function call ba... |
| `-MethodHistoryPrefix` | `String` | No | Prefix for the history-property created for each mocked method. Default is '_' which would create the property '_MethodName'. |

---

### New-PesterConfiguration

Creates a new PesterConfiguration object for advanced configuration of Invoke-Pester.

The New-PesterConfiguration function creates a new PesterConfiguration-object
to enable advanced configurations for runnings tests using Invoke-Pester.

**Returns**: `None documented`

```
New-PesterConfiguration
    [-Hashtable <IDictionary>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Hashtable` | `IDictionary` | No | Override the default values for the options defined in the provided dictionary/hashtable. See about_PesterConfiguration help topic or inspect a PesterConfiguration-object to learn about the schema ... |

---

### New-PesterContainer

Generates ContainerInfo-objects used as for Invoke-Pester -Container

Pester 5 supports running tests files and scriptblocks using parameter-input.
To use this feature, Invoke-Pester expects one or more ContainerInfo-objects
created using this function, that specify test containers in the form of paths
to the test files or scriptblocks containing the tests directly.

**Returns**: `None documented`

```
New-PesterContainer
    -Path <String[]>
    -ScriptBlock <ScriptBlock[]>
    [-Data <IDictionary[]>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Path` | `String[]` | Yes | Specifies one or more paths to files containing tests. The value is a path\file name or name pattern. Wildcards are permitted. |
| `-ScriptBlock` | `ScriptBlock[]` | Yes | Specifies one or more scriptblocks containing tests. |
| `-Data` | `IDictionary[]` | No | Allows a dictionary to be provided with parameter-values that should be used during execution of the test containers defined in Path or ScriptBlock. |

---

### Set-ItResult

Set-ItResult is used inside the It block to explicitly set the test result

Sometimes a test shouldn't be executed, sometimes the condition cannot be evaluated.
By default such tests would typically fail and produce a big red message.
Using Set-ItResult it is possible to set the result from the inside of the It script
block to either inconclusive, pending or skipped.

**Returns**: `None documented`

```
Set-ItResult
    [-Inconclusive]
    [-Pending]
    [-Skipped]
    [-Because <String>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-Inconclusive` | `SwitchParameter` | No | Sets the test result to inconclusive. Cannot be used at the same time as -Pending or -Skipped |
| `-Pending` | `SwitchParameter` | No | **DEPRECATED** Sets the test result to pending. Cannot be used at the same time as -Inconclusive or -Skipped |
| `-Skipped` | `SwitchParameter` | No | Sets the test result to skipped. Cannot be used at the same time as -Inconclusive or -Pending |
| `-Because` | `String` | No | Similarly to failing tests, skipped and inconclusive tests should have reason. It allows to provide information to the user why the test is neither successful nor failed. |

---

### Should

Should is a keyword that is used to define an assertion inside an It block.

Should is a keyword that is used to define an assertion inside an It block.
Should provides assertion methods to verify assertions e.g. comparing objects.
If assertion is not met the test fails and an exception is thrown.

**Returns**: `None documented`

```
Should
    [-ActualValue <Object>]
```

| Parameter | Type | Required | Description |
|-----------|------|----------|-------------|
| `-ActualValue` | `Object` | No | The actual value that was obtained in the test which should be verified against a expected value. |

---

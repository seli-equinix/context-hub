---
name: package
description: "Pyflakes static analysis guide for checking Python code for undefined names, unused imports, and similar correctness issues"
metadata:
  languages: "python"
  versions: "3.4.0"
  updated-on: "2026-05-02"
  source: maintainer
  tags: "pyflakes,python,lint,static-analysis,cli,check,checkPath,Command-Line,greet,checkRecursive,isPythonFile,iterSourceCode,main,Annotation,redefines,AnnotationState,Argument,Assignment,Binding,Builtin,Checker,ADD,AND,ANNASSIGN,ARG,ARGUMENTS,ASSERT,ASSIGN,ASYNCFOR,ASYNCFUNCTIONDEF,ASYNCWITH,ATTRIBUTE,AUGASSIGN,AUGLOAD,AUGSTORE,AWAIT,BINOP,BITAND,BITOR,BITXOR,BOOLOP,BREAK,CALL,CLASSDEF,COMPARE,COMPREHENSION,CONSTANT,CONTINUE,DEL,DELETE,DICT,ClassDefinition,ClassScope,Definition,DetectClassScopedMagic,DoctestScope,ExportBinding,FunctionDefinition,FunctionScope,unused_annotations,unused_assignments,FutureImportation,GeneratorScope,Importation,ImportationFrom,ModuleScope,NamedExprAssignment,Scope,StarImportation,SubmoduleImportation,TypeScope,UnhandledKeyType,VariableKey,convert_to_value,getAlternatives,getNodeName,in_annotation,in_string_annotation,is_notimplemented_name_node,is_typing_overload,iter_child_nodes,parse_percent_format,AssertTuple,BreakOutsideLoop,ContinueOutsideLoop,DefaultExceptNotLast,DoctestSyntaxError,DuplicateArgument,FStringMissingPlaceholders,ForwardAnnotationSyntaxError,FutureFeatureNotDefined,IfTuple,ImportShadowedByLoopVar,ImportStarNotPermitted,ImportStarUsage,ImportStarUsed,InvalidPrintSyntax,IsLiteral,LateFutureImport,Message,MultiValueRepeatedKeyLiteral,MultiValueRepeatedKeyVariable,PercentFormatExpectedMapping,PercentFormatExpectedSequence,PercentFormatExtraNamedArguments,PercentFormatInvalidFormat,PercentFormatMissingArgument,PercentFormatMixedPositionalAndNamed,PercentFormatPositionalCountMismatch,PercentFormatStarRequiresSequence,PercentFormatUnsupportedFormatCharacter,RaiseNotImplemented,RedefinedWhileUnused,ReturnOutsideFunction,StringDotFormatExtraNamedArguments,StringDotFormatExtraPositionalArguments,StringDotFormatInvalidFormat,StringDotFormatMissingArgument,StringDotFormatMixingAutomatic,TStringMissingPlaceholders,TooManyExpressionsInStarredAssignment,TwoStarredExpressions,UndefinedExport,UndefinedLocal,UndefinedName,UnusedAnnotation,UnusedImport,UnusedIndirectAssignment,UnusedVariable,YieldOutsideFunction,Reporter,flake,syntaxError,unexpectedError,TestCase,addClassCleanup,addCleanup,addTypeEqualityFunc,assertAlmostEqual,assertCountEqual,assertDictEqual,assertEqual,assertFalse,assertGreater,assertGreaterEqual,assertIn,assertIs,assertIsInstance,assertIsNone,assertIsNot,assertIsNotNone,assertLess,assertLessEqual,assertListEqual,assertLogs,assertMultiLineEqual,assertNoLogs,assertNotAlmostEqual,assertNotEqual,assertNotIn,assertNotIsInstance,assertNotRegex,assertRaises,assertRaisesRegex,assertRegex,CheckTests,assertHasErrors"
---

# pyflakes — package

## Install

```bash
pip install pyflakes
```

## Imports

```python
import pyflakes
```

## Symbols (200)

| Symbol | Kind | Synopsis |
|--------|------|----------|
| `check` | Function | Check the Python source given by C{codeString} for flakes.  @param codeString:… |
| `checkPath` | Function | Check the given path, printing out any warnings detected.  @param reporter: A L… |
| `checkRecursive` | Function | Recursively check all source files in C{paths}.  @param paths: A list of paths… |
| `isPythonFile` | Function | Return True if filename points to a Python file. |
| `iterSourceCode` | Function | Iterate over all Python source files in C{paths}.  @param paths: A list of path… |
| `main` | Function | Entry point for the script "pyflakes". |
| `Annotation` | Class | Represents binding a name to a type without an associated value.  As long as th… |
| `redefines` | Method | An Annotation doesn't define any name, so it cannot redefine one. |
| `AnnotationState` | Class |  |
| `Argument` | Class | Represents binding a name as an argument. |
| `redefines` | Method |  |
| `Assignment` | Class | Represents binding a name with an explicit assignment.  The checker will raise… |
| `redefines` | Method |  |
| `Binding` | Class | Represents the binding of a value to a name.  The checker uses this to keep tra… |
| `redefines` | Method |  |
| `Builtin` | Class | A definition created for all Python builtins. |
| `redefines` | Method |  |
| `Checker` | Class | I check the cleanliness and sanity of Python code. |
| `ADD` | Method |  |
| `AND` | Method |  |
| `ANNASSIGN` | Method |  |
| `ARG` | Method |  |
| `ARGUMENTS` | Method |  |
| `ASSERT` | Method |  |
| `ASSIGN` | Method |  |
| `ASYNCFOR` | Method |  |
| `ASYNCFUNCTIONDEF` | Method |  |
| `ASYNCWITH` | Method |  |
| `ATTRIBUTE` | Method |  |
| `AUGASSIGN` | Method |  |
| `AUGLOAD` | Method |  |
| `AUGSTORE` | Method |  |
| `AWAIT` | Method |  |
| `BINOP` | Method |  |
| `BITAND` | Method |  |
| `BITOR` | Method |  |
| `BITXOR` | Method |  |
| `BOOLOP` | Method |  |
| `BREAK` | Method |  |
| `CALL` | Method |  |
| `CLASSDEF` | Method | Check names used in a class definition, including its decorators, base classes,… |
| `COMPARE` | Method |  |
| `COMPREHENSION` | Method |  |
| `CONSTANT` | Method |  |
| `CONTINUE` | Method |  |
| `DEL` | Method |  |
| `DELETE` | Method |  |
| `DICT` | Method |  |
| `ClassDefinition` | Class | A binding that defines a function or a class. |
| `redefines` | Method |  |
| `ClassScope` | Class | dict() -> new empty dictionary dict(mapping) -> new dictionary initialized from… |
| `Definition` | Class | A binding that defines a function or a class. |
| `redefines` | Method |  |
| `DetectClassScopedMagic` | Class |  |
| `DoctestScope` | Class | Scope for a doctest. |
| `ExportBinding` | Class | A binding created by an C{__all__} assignment.  If the names in the list can be… |
| `redefines` | Method |  |
| `FunctionDefinition` | Class | A binding that defines a function or a class. |
| `redefines` | Method |  |
| `FunctionScope` | Class | I represent a name scope for a function.  @ivar globals: Names declared 'global… |
| `unused_annotations` | Method | Return a generator for the annotations which have not been used. |
| `unused_assignments` | Method | Return a generator for the assignments which have not been used. |
| `FutureImportation` | Class | A binding created by a from `__future__` import statement.  `__future__` import… |
| `redefines` | Method |  |
| `GeneratorScope` | Class | dict() -> new empty dictionary dict(mapping) -> new dictionary initialized from… |
| `Importation` | Class | A binding created by an import statement.  @ivar fullName: The complete name gi… |
| `redefines` | Method |  |
| `ImportationFrom` | Class | A binding created by an import statement.  @ivar fullName: The complete name gi… |
| `redefines` | Method |  |
| `ModuleScope` | Class | Scope for a module. |
| `NamedExprAssignment` | Class | Represents binding a name with an assignment expression. |
| `redefines` | Method |  |
| `Scope` | Class | dict() -> new empty dictionary dict(mapping) -> new dictionary initialized from… |
| `StarImportation` | Class | A binding created by a 'from x import *' statement. |
| `redefines` | Method |  |
| `SubmoduleImportation` | Class | A binding created by a submodule import statement.  A submodule import is a spe… |
| `redefines` | Method |  |
| `TypeScope` | Class | dict() -> new empty dictionary dict(mapping) -> new dictionary initialized from… |
| `UnhandledKeyType` | Class | A dictionary key of a type that we cannot or do not check for duplicates. |
| `VariableKey` | Class | A dictionary key which is a variable.  @ivar item: The variable AST object. |
| `convert_to_value` | Function |  |
| `getAlternatives` | Function |  |
| `getNodeName` | Function |  |
| `in_annotation` | Function |  |
| `in_string_annotation` | Function |  |
| `is_notimplemented_name_node` | Function |  |
| `is_typing_overload` | Function |  |
| `iter_child_nodes` | Function | Yield all direct child nodes of *node*, that is, all fields that are nodes and… |
| `parse_percent_format` | Function | Parses the string component of a `'...' % ...` format call  Copied from https:/… |
| `AssertTuple` | Class | Assertion test is a non-empty tuple literal, which are always True. |
| `BreakOutsideLoop` | Class | Indicates a break statement outside of a while or for loop. |
| `ContinueOutsideLoop` | Class | Indicates a continue statement outside of a while or for loop. |
| `DefaultExceptNotLast` | Class | Indicates an except: block as not the last exception handler. |
| `DoctestSyntaxError` | Class |  |
| `DuplicateArgument` | Class |  |
| `FStringMissingPlaceholders` | Class |  |
| `ForwardAnnotationSyntaxError` | Class |  |
| `FutureFeatureNotDefined` | Class | An undefined __future__ feature name was imported. |
| `IfTuple` | Class | Conditional test is a non-empty tuple literal, which are always True. |
| `ImportShadowedByLoopVar` | Class |  |
| `ImportStarNotPermitted` | Class |  |
| `ImportStarUsage` | Class |  |
| `ImportStarUsed` | Class |  |
| `InvalidPrintSyntax` | Class |  |
| `IsLiteral` | Class |  |
| `LateFutureImport` | Class |  |
| `Message` | Class |  |
| `MultiValueRepeatedKeyLiteral` | Class |  |
| `MultiValueRepeatedKeyVariable` | Class |  |
| `PercentFormatExpectedMapping` | Class |  |
| `PercentFormatExpectedSequence` | Class |  |
| `PercentFormatExtraNamedArguments` | Class |  |
| `PercentFormatInvalidFormat` | Class |  |
| `PercentFormatMissingArgument` | Class |  |
| `PercentFormatMixedPositionalAndNamed` | Class |  |
| `PercentFormatPositionalCountMismatch` | Class |  |
| `PercentFormatStarRequiresSequence` | Class |  |
| `PercentFormatUnsupportedFormatCharacter` | Class |  |
| `RaiseNotImplemented` | Class |  |
| `RedefinedWhileUnused` | Class |  |
| `ReturnOutsideFunction` | Class | Indicates a return statement outside of a function/method. |
| `StringDotFormatExtraNamedArguments` | Class |  |
| `StringDotFormatExtraPositionalArguments` | Class |  |
| `StringDotFormatInvalidFormat` | Class |  |
| `StringDotFormatMissingArgument` | Class |  |
| `StringDotFormatMixingAutomatic` | Class |  |
| `TStringMissingPlaceholders` | Class |  |
| `TooManyExpressionsInStarredAssignment` | Class | Too many expressions in an assignment with star-unpacking |
| `TwoStarredExpressions` | Class | Two or more starred expressions in an assignment (a, *b, *c = d). |
| `UndefinedExport` | Class |  |
| `UndefinedLocal` | Class |  |
| `UndefinedName` | Class |  |
| `UnusedAnnotation` | Class | Indicates that a variable has been explicitly annotated to but not actually use… |
| `UnusedImport` | Class |  |
| `UnusedIndirectAssignment` | Class | A `global` or `nonlocal` statement where the name is never reassigned |
| `UnusedVariable` | Class | Indicates that a variable has been explicitly assigned to but not actually used. |
| `YieldOutsideFunction` | Class | Indicates a yield or yield from statement outside of a function/method. |
| `Reporter` | Class | Formats the results of pyflakes checks to users. |
| `flake` | Method | pyflakes found something wrong with the code.  @param: A L{pyflakes.messages.Me… |
| `syntaxError` | Method | There was a syntax error in C{filename}.  @param filename: The path to the file… |
| `unexpectedError` | Method | An unexpected error occurred trying to process C{filename}.  @param filename: T… |
| `check` | Function | Check the Python source given by C{codeString} for flakes.  @param codeString:… |
| `checkPath` | Function | Check the given path, printing out any warnings detected.  @param reporter: A L… |
| `checkRecursive` | Function | Recursively check all source files in C{paths}.  @param paths: A list of paths… |
| `iterSourceCode` | Function | Iterate over all Python source files in C{paths}.  @param paths: A list of path… |
| `main` | Function | Entry point for the script "pyflakes". |
| `TestCase` | Class | A class whose instances are single test cases.  By default, the test code itsel… |
| `addClassCleanup` | Method | Same as addCleanup, except the cleanup items are called even if setUpClass fail… |
| `addCleanup` | Method | Add a function, with arguments, to be called when the test is completed. Functi… |
| `addTypeEqualityFunc` | Method | Add a type specific assertEqual style function to compare a type.  This method… |
| `assertAlmostEqual` | Method | Fail if the two objects are unequal as determined by their difference rounded t… |
| `assertCountEqual` | Method | Asserts that two iterables have the same elements, the same number of times, wi… |
| `assertDictEqual` | Method |  |
| `assertEqual` | Method | Fail if the two objects are unequal as determined by the '==' operator. |
| `assertFalse` | Method | Check that the expression is false. |
| `assertGreater` | Method | Just like self.assertTrue(a > b), but with a nicer default message. |
| `assertGreaterEqual` | Method | Just like self.assertTrue(a >= b), but with a nicer default message. |
| `assertIn` | Method | Just like self.assertTrue(a in b), but with a nicer default message. |
| `assertIs` | Method | Just like self.assertTrue(a is b), but with a nicer default message. |
| `assertIsInstance` | Method | Same as self.assertTrue(isinstance(obj, cls)), with a nicer default message. |
| `assertIsNone` | Method | Same as self.assertTrue(obj is None), with a nicer default message. |
| `assertIsNot` | Method | Just like self.assertTrue(a is not b), but with a nicer default message. |
| `assertIsNotNone` | Method | Included for symmetry with assertIsNone. |
| `assertLess` | Method | Just like self.assertTrue(a < b), but with a nicer default message. |
| `assertLessEqual` | Method | Just like self.assertTrue(a <= b), but with a nicer default message. |
| `assertListEqual` | Method | A list-specific equality assertion.  Args:     list1: The first list to compare… |
| `assertLogs` | Method | Fail unless a log message of level *level* or higher is emitted on *logger_name… |
| `assertMultiLineEqual` | Method | Assert that two multi-line strings are equal. |
| `assertNoLogs` | Method | Fail unless no log messages of level *level* or higher are emitted on *logger_n… |
| `assertNotAlmostEqual` | Method | Fail if the two objects are equal as determined by their difference rounded to… |
| `assertNotEqual` | Method | Fail if the two objects are equal as determined by the '!=' operator. |
| `assertNotIn` | Method | Just like self.assertTrue(a not in b), but with a nicer default message. |
| `assertNotIsInstance` | Method | Included for symmetry with assertIsInstance. |
| `assertNotRegex` | Method | Fail the test if the text matches the regular expression. |
| `assertRaises` | Method | Fail unless an exception of class expected_exception is raised by the callable… |
| `assertRaisesRegex` | Method | Asserts that the message in a raised exception matches a regex.  Args:     expe… |
| `assertRegex` | Method | Fail the test unless the text matches the regular expression. |
| `CheckTests` | Class | Tests for L{check} and L{checkPath} which check a file for flakes. |
| `addClassCleanup` | Method | Same as addCleanup, except the cleanup items are called even if setUpClass fail… |
| `addCleanup` | Method | Add a function, with arguments, to be called when the test is completed. Functi… |
| `addTypeEqualityFunc` | Method | Add a type specific assertEqual style function to compare a type.  This method… |
| `assertAlmostEqual` | Method | Fail if the two objects are unequal as determined by their difference rounded t… |
| `assertCountEqual` | Method | Asserts that two iterables have the same elements, the same number of times, wi… |
| `assertDictEqual` | Method |  |
| `assertEqual` | Method | Fail if the two objects are unequal as determined by the '==' operator. |
| `assertFalse` | Method | Check that the expression is false. |
| `assertGreater` | Method | Just like self.assertTrue(a > b), but with a nicer default message. |
| `assertGreaterEqual` | Method | Just like self.assertTrue(a >= b), but with a nicer default message. |
| `assertHasErrors` | Method | Assert that C{path} causes errors.  @param path: A path to a file to check. @pa… |
| `assertIn` | Method | Just like self.assertTrue(a in b), but with a nicer default message. |
| `assertIs` | Method | Just like self.assertTrue(a is b), but with a nicer default message. |
| `assertIsInstance` | Method | Same as self.assertTrue(isinstance(obj, cls)), with a nicer default message. |
| `assertIsNone` | Method | Same as self.assertTrue(obj is None), with a nicer default message. |
| `assertIsNot` | Method | Just like self.assertTrue(a is not b), but with a nicer default message. |
| `assertIsNotNone` | Method | Included for symmetry with assertIsNone. |
| `assertLess` | Method | Just like self.assertTrue(a < b), but with a nicer default message. |
| `assertLessEqual` | Method | Just like self.assertTrue(a <= b), but with a nicer default message. |
| `assertListEqual` | Method | A list-specific equality assertion.  Args:     list1: The first list to compare… |
| `assertLogs` | Method | Fail unless a log message of level *level* or higher is emitted on *logger_name… |
| `assertMultiLineEqual` | Method | Assert that two multi-line strings are equal. |

## Classes

### `Annotation`

Represents binding a name to a type without an associated value.

As long as this name is not assigned a value in another binding, it is considered
undefined for most purposes. One notable exception…

```python
pyflakes.checker.Annotation(self, name, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `AnnotationState`

```python
pyflakes.checker.AnnotationState(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Argument`

Represents binding a name as an argument.

```python
pyflakes.checker.Argument(self, name, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `Assignment`

Represents binding a name with an explicit assignment.

The checker will raise warnings for any Assignment that isn't used. Also,
the checker does not consider assignments in tuple/list unpacking to…

```python
pyflakes.checker.Assignment(self, name, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `Binding`

Represents the binding of a value to a name.

The checker uses this to keep track of which names have been bound and
which names have not. See L{Assignment} for a special type of binding that
is chec…

```python
pyflakes.checker.Binding(self, name, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `Builtin`

A definition created for all Python builtins.

```python
pyflakes.checker.Builtin(self, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |

### `Checker`

I check the cleanliness and sanity of Python code.

```python
pyflakes.checker.Checker(self, tree, filename='(none)', builtins=None, withDoctest=False, file_tokens=())
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `tree` | `—` | `—` | pos/kw |
| `filename` | `—` | `'(none)'` | pos/kw |
| `builtins` | `—` | `None` | pos/kw |
| `withDoctest` | `—` | `False` | pos/kw |
| `file_tokens` | `—` | `()` | pos/kw |

### `ClassDefinition`

A binding that defines a function or a class.

```python
pyflakes.checker.ClassDefinition(self, name, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `ClassScope`

dict() -> new empty dictionary
dict(mapping) -> new dictionary initialized from a mapping object's
    (key, value) pairs
dict(iterable) -> new dictionary initialized as if via:
    d = {}
    for k,…

```python
pyflakes.checker.ClassScope(self)
```

### `Definition`

A binding that defines a function or a class.

```python
pyflakes.checker.Definition(self, name, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `DetectClassScopedMagic`

```python
pyflakes.checker.DetectClassScopedMagic(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `DoctestScope`

Scope for a doctest.

```python
pyflakes.checker.DoctestScope(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `ExportBinding`

A binding created by an C{__all__} assignment.  If the names in the list
can be determined statically, they will be treated as names for export and
additional checking applied to them.

The only reco…

```python
pyflakes.checker.ExportBinding(self, name, source, scope)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |
| `scope` | `—` | `—` | pos/kw |

### `FunctionDefinition`

A binding that defines a function or a class.

```python
pyflakes.checker.FunctionDefinition(self, name, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `FunctionScope`

I represent a name scope for a function.

@ivar globals: Names declared 'global' in this function.

```python
pyflakes.checker.FunctionScope(self)
```

### `FutureImportation`

A binding created by a from `__future__` import statement.

`__future__` imports are implicitly used.

```python
pyflakes.checker.FutureImportation(self, name, source, scope)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |
| `scope` | `—` | `—` | pos/kw |

### `GeneratorScope`

dict() -> new empty dictionary
dict(mapping) -> new dictionary initialized from a mapping object's
    (key, value) pairs
dict(iterable) -> new dictionary initialized as if via:
    d = {}
    for k,…

```python
pyflakes.checker.GeneratorScope(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `Importation`

A binding created by an import statement.

@ivar fullName: The complete name given to the import statement,
    possibly including multiple dotted components.
@type fullName: C{str}

```python
pyflakes.checker.Importation(self, name, source, full_name=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |
| `full_name` | `—` | `None` | pos/kw |

### `ImportationFrom`

A binding created by an import statement.

@ivar fullName: The complete name given to the import statement,
    possibly including multiple dotted components.
@type fullName: C{str}

```python
pyflakes.checker.ImportationFrom(self, name, source, module, real_name=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |
| `module` | `—` | `—` | pos/kw |
| `real_name` | `—` | `None` | pos/kw |

### `ModuleScope`

Scope for a module.

```python
pyflakes.checker.ModuleScope(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `NamedExprAssignment`

Represents binding a name with an assignment expression.

```python
pyflakes.checker.NamedExprAssignment(self, name, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `Scope`

dict() -> new empty dictionary
dict(mapping) -> new dictionary initialized from a mapping object's
    (key, value) pairs
dict(iterable) -> new dictionary initialized as if via:
    d = {}
    for k,…

```python
pyflakes.checker.Scope(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `StarImportation`

A binding created by a 'from x import *' statement.

```python
pyflakes.checker.StarImportation(self, name, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `SubmoduleImportation`

A binding created by a submodule import statement.

A submodule import is a special case where the root module is implicitly
imported, without an 'as' clause, and the submodule is also imported.
Pyth…

```python
pyflakes.checker.SubmoduleImportation(self, name, source)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `name` | `—` | `—` | pos/kw |
| `source` | `—` | `—` | pos/kw |

### `TypeScope`

dict() -> new empty dictionary
dict(mapping) -> new dictionary initialized from a mapping object's
    (key, value) pairs
dict(iterable) -> new dictionary initialized as if via:
    d = {}
    for k,…

```python
pyflakes.checker.TypeScope(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `UnhandledKeyType`

A dictionary key of a type that we cannot or do not check for duplicates.

```python
pyflakes.checker.UnhandledKeyType(self, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `VariableKey`

A dictionary key which is a variable.

@ivar item: The variable AST object.

```python
pyflakes.checker.VariableKey(self, item)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `item` | `—` | `—` | pos/kw |

### `AssertTuple`

Assertion test is a non-empty tuple literal, which are always True.

```python
pyflakes.messages.AssertTuple(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `BreakOutsideLoop`

Indicates a break statement outside of a while or for loop.

```python
pyflakes.messages.BreakOutsideLoop(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `ContinueOutsideLoop`

Indicates a continue statement outside of a while or for loop.

```python
pyflakes.messages.ContinueOutsideLoop(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `DefaultExceptNotLast`

Indicates an except: block as not the last exception handler.

```python
pyflakes.messages.DefaultExceptNotLast(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `DoctestSyntaxError`

```python
pyflakes.messages.DoctestSyntaxError(self, filename, loc, position=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `position` | `—` | `None` | pos/kw |

### `DuplicateArgument`

```python
pyflakes.messages.DuplicateArgument(self, filename, loc, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `FStringMissingPlaceholders`

```python
pyflakes.messages.FStringMissingPlaceholders(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `ForwardAnnotationSyntaxError`

```python
pyflakes.messages.ForwardAnnotationSyntaxError(self, filename, loc, annotation)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `annotation` | `—` | `—` | pos/kw |

### `FutureFeatureNotDefined`

An undefined __future__ feature name was imported.

```python
pyflakes.messages.FutureFeatureNotDefined(self, filename, loc, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `IfTuple`

Conditional test is a non-empty tuple literal, which are always True.

```python
pyflakes.messages.IfTuple(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `ImportShadowedByLoopVar`

```python
pyflakes.messages.ImportShadowedByLoopVar(self, filename, loc, name, orig_loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `orig_loc` | `—` | `—` | pos/kw |

### `ImportStarNotPermitted`

```python
pyflakes.messages.ImportStarNotPermitted(self, filename, loc, modname)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `modname` | `—` | `—` | pos/kw |

### `ImportStarUsage`

```python
pyflakes.messages.ImportStarUsage(self, filename, loc, name, from_list)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `from_list` | `—` | `—` | pos/kw |

### `ImportStarUsed`

```python
pyflakes.messages.ImportStarUsed(self, filename, loc, modname)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `modname` | `—` | `—` | pos/kw |

### `InvalidPrintSyntax`

```python
pyflakes.messages.InvalidPrintSyntax(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `IsLiteral`

```python
pyflakes.messages.IsLiteral(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `LateFutureImport`

```python
pyflakes.messages.LateFutureImport(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `Message`

```python
pyflakes.messages.Message(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `MultiValueRepeatedKeyLiteral`

```python
pyflakes.messages.MultiValueRepeatedKeyLiteral(self, filename, loc, key)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |

### `MultiValueRepeatedKeyVariable`

```python
pyflakes.messages.MultiValueRepeatedKeyVariable(self, filename, loc, key)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `key` | `—` | `—` | pos/kw |

### `PercentFormatExpectedMapping`

```python
pyflakes.messages.PercentFormatExpectedMapping(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `PercentFormatExpectedSequence`

```python
pyflakes.messages.PercentFormatExpectedSequence(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `PercentFormatExtraNamedArguments`

```python
pyflakes.messages.PercentFormatExtraNamedArguments(self, filename, loc, extra_keywords)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `extra_keywords` | `—` | `—` | pos/kw |

### `PercentFormatInvalidFormat`

```python
pyflakes.messages.PercentFormatInvalidFormat(self, filename, loc, error)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `error` | `—` | `—` | pos/kw |

### `PercentFormatMissingArgument`

```python
pyflakes.messages.PercentFormatMissingArgument(self, filename, loc, missing_arguments)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `missing_arguments` | `—` | `—` | pos/kw |

### `PercentFormatMixedPositionalAndNamed`

```python
pyflakes.messages.PercentFormatMixedPositionalAndNamed(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `PercentFormatPositionalCountMismatch`

```python
pyflakes.messages.PercentFormatPositionalCountMismatch(self, filename, loc, n_placeholders, n_substitutions)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `n_placeholders` | `—` | `—` | pos/kw |
| `n_substitutions` | `—` | `—` | pos/kw |

### `PercentFormatStarRequiresSequence`

```python
pyflakes.messages.PercentFormatStarRequiresSequence(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `PercentFormatUnsupportedFormatCharacter`

```python
pyflakes.messages.PercentFormatUnsupportedFormatCharacter(self, filename, loc, c)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `c` | `—` | `—` | pos/kw |

### `RaiseNotImplemented`

```python
pyflakes.messages.RaiseNotImplemented(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `RedefinedWhileUnused`

```python
pyflakes.messages.RedefinedWhileUnused(self, filename, loc, name, orig_loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `orig_loc` | `—` | `—` | pos/kw |

### `ReturnOutsideFunction`

Indicates a return statement outside of a function/method.

```python
pyflakes.messages.ReturnOutsideFunction(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `StringDotFormatExtraNamedArguments`

```python
pyflakes.messages.StringDotFormatExtraNamedArguments(self, filename, loc, extra_keywords)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `extra_keywords` | `—` | `—` | pos/kw |

### `StringDotFormatExtraPositionalArguments`

```python
pyflakes.messages.StringDotFormatExtraPositionalArguments(self, filename, loc, extra_positions)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `extra_positions` | `—` | `—` | pos/kw |

### `StringDotFormatInvalidFormat`

```python
pyflakes.messages.StringDotFormatInvalidFormat(self, filename, loc, error)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `error` | `—` | `—` | pos/kw |

### `StringDotFormatMissingArgument`

```python
pyflakes.messages.StringDotFormatMissingArgument(self, filename, loc, missing_arguments)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `missing_arguments` | `—` | `—` | pos/kw |

### `StringDotFormatMixingAutomatic`

```python
pyflakes.messages.StringDotFormatMixingAutomatic(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `TStringMissingPlaceholders`

```python
pyflakes.messages.TStringMissingPlaceholders(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `TooManyExpressionsInStarredAssignment`

Too many expressions in an assignment with star-unpacking

```python
pyflakes.messages.TooManyExpressionsInStarredAssignment(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `TwoStarredExpressions`

Two or more starred expressions in an assignment (a, *b, *c = d).

```python
pyflakes.messages.TwoStarredExpressions(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `UndefinedExport`

```python
pyflakes.messages.UndefinedExport(self, filename, loc, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `UndefinedLocal`

```python
pyflakes.messages.UndefinedLocal(self, filename, loc, name, orig_loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |
| `orig_loc` | `—` | `—` | pos/kw |

### `UndefinedName`

```python
pyflakes.messages.UndefinedName(self, filename, loc, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `UnusedAnnotation`

Indicates that a variable has been explicitly annotated to but not actually
used.

```python
pyflakes.messages.UnusedAnnotation(self, filename, loc, names)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `names` | `—` | `—` | pos/kw |

### `UnusedImport`

```python
pyflakes.messages.UnusedImport(self, filename, loc, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `UnusedIndirectAssignment`

A `global` or `nonlocal` statement where the name is never reassigned

```python
pyflakes.messages.UnusedIndirectAssignment(self, filename, loc, name)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `name` | `—` | `—` | pos/kw |

### `UnusedVariable`

Indicates that a variable has been explicitly assigned to but not actually
used.

```python
pyflakes.messages.UnusedVariable(self, filename, loc, names)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |
| `names` | `—` | `—` | pos/kw |

### `YieldOutsideFunction`

Indicates a yield or yield from statement outside of a function/method.

```python
pyflakes.messages.YieldOutsideFunction(self, filename, loc)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `loc` | `—` | `—` | pos/kw |

### `Reporter`

Formats the results of pyflakes checks to users.

```python
pyflakes.reporter.Reporter(self, warningStream, errorStream)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `warningStream` | `—` | `—` | pos/kw |
| `errorStream` | `—` | `—` | pos/kw |

### `TestCase`

A class whose instances are single test cases.

By default, the test code itself should be placed in a method named
'runTest'.

If the fixture may be used for many test cases, create as
many test met…

```python
pyflakes.test.harness.TestCase(self, methodName='runTest')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `methodName` | `—` | `'runTest'` | pos/kw |

### `CheckTests`

Tests for L{check} and L{checkPath} which check a file for flakes.

```python
pyflakes.test.test_api.CheckTests(self, methodName='runTest')
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `methodName` | `—` | `'runTest'` | pos/kw |

## Functions

### `check`

Check the Python source given by C{codeString} for flakes.

@param codeString: The Python source to check.
@type codeString: C{str}

@param filename: The name of the file the source came from, used t…

```python
pyflakes.api.check(codeString, filename, reporter=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `codeString` | `—` | `—` | pos/kw |
| `filename` | `—` | `—` | pos/kw |
| `reporter` | `—` | `None` | pos/kw |

### `checkPath`

Check the given path, printing out any warnings detected.

@param reporter: A L{Reporter} instance, where errors and warnings will be
    reported.

@return: the number of warnings printed

```python
pyflakes.api.checkPath(filename, reporter=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `reporter` | `—` | `None` | pos/kw |

### `checkRecursive`

Recursively check all source files in C{paths}.

@param paths: A list of paths to Python source files and directories
    containing Python source files.
@param reporter: A L{Reporter} where all of t…

```python
pyflakes.api.checkRecursive(paths, reporter)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `paths` | `—` | `—` | pos/kw |
| `reporter` | `—` | `—` | pos/kw |

### `isPythonFile`

Return True if filename points to a Python file.

```python
pyflakes.api.isPythonFile(filename)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |

### `iterSourceCode`

Iterate over all Python source files in C{paths}.

@param paths: A list of paths.  Directories will be recursed into and
    any .py files found will be yielded.  Any non-directories will be
    yiel…

```python
pyflakes.api.iterSourceCode(paths)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `paths` | `—` | `—` | pos/kw |

### `main`

Entry point for the script "pyflakes".

```python
pyflakes.api.main(prog=None, args=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `prog` | `—` | `None` | pos/kw |
| `args` | `—` | `None` | pos/kw |

### `convert_to_value`

```python
pyflakes.checker.convert_to_value(item)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `item` | `—` | `—` | pos/kw |

### `getAlternatives`

```python
pyflakes.checker.getAlternatives(n)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `n` | `—` | `—` | pos/kw |

### `getNodeName`

```python
pyflakes.checker.getNodeName(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `in_annotation`

```python
pyflakes.checker.in_annotation(func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `—` | `—` | pos/kw |

### `in_string_annotation`

```python
pyflakes.checker.in_string_annotation(func)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `func` | `—` | `—` | pos/kw |

### `is_notimplemented_name_node`

```python
pyflakes.checker.is_notimplemented_name_node(node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |

### `is_typing_overload`

```python
pyflakes.checker.is_typing_overload(value, scope_stack)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `value` | `—` | `—` | pos/kw |
| `scope_stack` | `—` | `—` | pos/kw |

### `iter_child_nodes`

Yield all direct child nodes of *node*, that is, all fields that
are nodes and all items of fields that are lists of nodes.

:param node:          AST node to be iterated upon
:param omit:          S…

```python
pyflakes.checker.iter_child_nodes(node, omit=None, _fields_order={})
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `node` | `—` | `—` | pos/kw |
| `omit` | `—` | `None` | pos/kw |
| `_fields_order` | `—` | `{}` | pos/kw |

### `parse_percent_format`

Parses the string component of a `'...' % ...` format call

Copied from https://github.com/asottile/pyupgrade at v1.20.1

```python
pyflakes.checker.parse_percent_format(s)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `s` | `—` | `—` | pos/kw |

### `check`

Check the Python source given by C{codeString} for flakes.

@param codeString: The Python source to check.
@type codeString: C{str}

@param filename: The name of the file the source came from, used t…

```python
pyflakes.scripts.pyflakes.check(codeString, filename, reporter=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `codeString` | `—` | `—` | pos/kw |
| `filename` | `—` | `—` | pos/kw |
| `reporter` | `—` | `None` | pos/kw |

### `checkPath`

Check the given path, printing out any warnings detected.

@param reporter: A L{Reporter} instance, where errors and warnings will be
    reported.

@return: the number of warnings printed

```python
pyflakes.scripts.pyflakes.checkPath(filename, reporter=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `filename` | `—` | `—` | pos/kw |
| `reporter` | `—` | `None` | pos/kw |

### `checkRecursive`

Recursively check all source files in C{paths}.

@param paths: A list of paths to Python source files and directories
    containing Python source files.
@param reporter: A L{Reporter} where all of t…

```python
pyflakes.scripts.pyflakes.checkRecursive(paths, reporter)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `paths` | `—` | `—` | pos/kw |
| `reporter` | `—` | `—` | pos/kw |

### `iterSourceCode`

Iterate over all Python source files in C{paths}.

@param paths: A list of paths.  Directories will be recursed into and
    any .py files found will be yielded.  Any non-directories will be
    yiel…

```python
pyflakes.scripts.pyflakes.iterSourceCode(paths)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `paths` | `—` | `—` | pos/kw |

### `main`

Entry point for the script "pyflakes".

```python
pyflakes.scripts.pyflakes.main(prog=None, args=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `prog` | `—` | `None` | pos/kw |
| `args` | `—` | `None` | pos/kw |

## Methods

### `pyflakes.checker.Annotation` methods

### `redefines`

An Annotation doesn't define any name, so it cannot redefine one.

```python
pyflakes.checker.Annotation.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.Argument` methods

### `redefines`

```python
pyflakes.checker.Argument.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.Assignment` methods

### `redefines`

```python
pyflakes.checker.Assignment.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.Binding` methods

### `redefines`

```python
pyflakes.checker.Binding.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.Builtin` methods

### `redefines`

```python
pyflakes.checker.Builtin.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.Checker` methods

### `ADD`

```python
pyflakes.checker.Checker.ADD(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `AND`

```python
pyflakes.checker.Checker.AND(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `ANNASSIGN`

```python
pyflakes.checker.Checker.ANNASSIGN(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `ARG`

```python
pyflakes.checker.Checker.ARG(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `ARGUMENTS`

```python
pyflakes.checker.Checker.ARGUMENTS(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `ASSERT`

```python
pyflakes.checker.Checker.ASSERT(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `ASSIGN`

```python
pyflakes.checker.Checker.ASSIGN(self, tree, omit=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tree` | `—` | `—` | pos/kw |
| `omit` | `—` | `None` | pos/kw |

### `ASYNCFOR`

```python
pyflakes.checker.Checker.ASYNCFOR(self, tree, omit=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tree` | `—` | `—` | pos/kw |
| `omit` | `—` | `None` | pos/kw |

### `ASYNCFUNCTIONDEF`

```python
pyflakes.checker.Checker.ASYNCFUNCTIONDEF(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `ASYNCWITH`

```python
pyflakes.checker.Checker.ASYNCWITH(self, tree, omit=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tree` | `—` | `—` | pos/kw |
| `omit` | `—` | `None` | pos/kw |

### `ATTRIBUTE`

```python
pyflakes.checker.Checker.ATTRIBUTE(self, tree, omit=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tree` | `—` | `—` | pos/kw |
| `omit` | `—` | `None` | pos/kw |

### `AUGASSIGN`

```python
pyflakes.checker.Checker.AUGASSIGN(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `AUGLOAD`

```python
pyflakes.checker.Checker.AUGLOAD(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `AUGSTORE`

```python
pyflakes.checker.Checker.AUGSTORE(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `AWAIT`

```python
pyflakes.checker.Checker.AWAIT(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `BINOP`

```python
pyflakes.checker.Checker.BINOP(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `BITAND`

```python
pyflakes.checker.Checker.BITAND(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `BITOR`

```python
pyflakes.checker.Checker.BITOR(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `BITXOR`

```python
pyflakes.checker.Checker.BITXOR(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `BOOLOP`

```python
pyflakes.checker.Checker.BOOLOP(self, tree, omit=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tree` | `—` | `—` | pos/kw |
| `omit` | `—` | `None` | pos/kw |

### `BREAK`

```python
pyflakes.checker.Checker.BREAK(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `CALL`

```python
pyflakes.checker.Checker.CALL(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `CLASSDEF`

Check names used in a class definition, including its decorators, base
classes, and the body of its definition.  Additionally, add its name to
the current scope.

```python
pyflakes.checker.Checker.CLASSDEF(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `COMPARE`

```python
pyflakes.checker.Checker.COMPARE(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `COMPREHENSION`

```python
pyflakes.checker.Checker.COMPREHENSION(self, tree, omit=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tree` | `—` | `—` | pos/kw |
| `omit` | `—` | `None` | pos/kw |

### `CONSTANT`

```python
pyflakes.checker.Checker.CONSTANT(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `CONTINUE`

```python
pyflakes.checker.Checker.CONTINUE(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `DEL`

```python
pyflakes.checker.Checker.DEL(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `DELETE`

```python
pyflakes.checker.Checker.DELETE(self, tree, omit=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `tree` | `—` | `—` | pos/kw |
| `omit` | `—` | `None` | pos/kw |

### `DICT`

```python
pyflakes.checker.Checker.DICT(self, node)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `node` | `—` | `—` | pos/kw |

### `pyflakes.checker.ClassDefinition` methods

### `redefines`

```python
pyflakes.checker.ClassDefinition.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.Definition` methods

### `redefines`

```python
pyflakes.checker.Definition.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.ExportBinding` methods

### `redefines`

```python
pyflakes.checker.ExportBinding.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.FunctionDefinition` methods

### `redefines`

```python
pyflakes.checker.FunctionDefinition.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.FunctionScope` methods

### `unused_annotations`

Return a generator for the annotations which have not been used.

```python
pyflakes.checker.FunctionScope.unused_annotations(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `unused_assignments`

Return a generator for the assignments which have not been used.

```python
pyflakes.checker.FunctionScope.unused_assignments(self)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |

### `pyflakes.checker.FutureImportation` methods

### `redefines`

```python
pyflakes.checker.FutureImportation.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.Importation` methods

### `redefines`

```python
pyflakes.checker.Importation.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.ImportationFrom` methods

### `redefines`

```python
pyflakes.checker.ImportationFrom.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.NamedExprAssignment` methods

### `redefines`

```python
pyflakes.checker.NamedExprAssignment.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.StarImportation` methods

### `redefines`

```python
pyflakes.checker.StarImportation.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.checker.SubmoduleImportation` methods

### `redefines`

```python
pyflakes.checker.SubmoduleImportation.redefines(self, other)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `other` | `—` | `—` | pos/kw |

### `pyflakes.reporter.Reporter` methods

### `flake`

pyflakes found something wrong with the code.

@param: A L{pyflakes.messages.Message}.

```python
pyflakes.reporter.Reporter.flake(self, message)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `message` | `—` | `—` | pos/kw |

### `syntaxError`

There was a syntax error in C{filename}.

@param filename: The path to the file with the syntax error.
@ptype filename: C{unicode}
@param msg: An explanation of the syntax error.
@ptype msg: C{unicod…

```python
pyflakes.reporter.Reporter.syntaxError(self, filename, msg, lineno, offset, text)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filename` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |
| `lineno` | `—` | `—` | pos/kw |
| `offset` | `—` | `—` | pos/kw |
| `text` | `—` | `—` | pos/kw |

### `unexpectedError`

An unexpected error occurred trying to process C{filename}.

@param filename: The path to a file that we could not process.
@ptype filename: C{unicode}
@param msg: A message explaining the problem.
@…

```python
pyflakes.reporter.Reporter.unexpectedError(self, filename, msg)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `filename` | `—` | `—` | pos/kw |
| `msg` | `—` | `—` | pos/kw |

### `pyflakes.test.harness.TestCase` methods

### `addClassCleanup`

Same as addCleanup, except the cleanup items are called even if
setUpClass fails (unlike tearDownClass).

```python
pyflakes.test.harness.TestCase.addClassCleanup(function, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `function` | `—` | `—` | pos |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `addCleanup`

Add a function, with arguments, to be called when the test is
completed. Functions added are called on a LIFO basis and are
called after tearDown on test failure or success.

Cleanup items are called…

```python
pyflakes.test.harness.TestCase.addCleanup(self, function, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `function` | `—` | `—` | pos |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `addTypeEqualityFunc`

Add a type specific assertEqual style function to compare a type.

This method is for use by TestCase subclasses that need to register
their own type equality functions to provide nicer error message…

```python
pyflakes.test.harness.TestCase.addTypeEqualityFunc(self, typeobj, function)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `typeobj` | `—` | `—` | pos/kw |
| `function` | `—` | `—` | pos/kw |

### `assertAlmostEqual`

Fail if the two objects are unequal as determined by their
difference rounded to the given number of decimal places
(default 7) and comparing to zero, or by comparing that the
difference between the…

```python
pyflakes.test.harness.TestCase.assertAlmostEqual(self, first, second, places=None, msg=None, delta=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |
| `second` | `—` | `—` | pos/kw |
| `places` | `—` | `None` | pos/kw |
| `msg` | `—` | `None` | pos/kw |
| `delta` | `—` | `None` | pos/kw |

### `assertCountEqual`

Asserts that two iterables have the same elements, the same number of
times, without regard to order.

    self.assertEqual(Counter(list(first)),
                     Counter(list(second)))

 Example…

```python
pyflakes.test.harness.TestCase.assertCountEqual(self, first, second, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |
| `second` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertDictEqual`

```python
pyflakes.test.harness.TestCase.assertDictEqual(self, d1, d2, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `d1` | `—` | `—` | pos/kw |
| `d2` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertEqual`

Fail if the two objects are unequal as determined by the '=='
operator.

```python
pyflakes.test.harness.TestCase.assertEqual(self, first, second, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |
| `second` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertFalse`

Check that the expression is false.

```python
pyflakes.test.harness.TestCase.assertFalse(self, expr, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `expr` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertGreater`

Just like self.assertTrue(a > b), but with a nicer default message.

```python
pyflakes.test.harness.TestCase.assertGreater(self, a, b, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertGreaterEqual`

Just like self.assertTrue(a >= b), but with a nicer default message.

```python
pyflakes.test.harness.TestCase.assertGreaterEqual(self, a, b, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIn`

Just like self.assertTrue(a in b), but with a nicer default message.

```python
pyflakes.test.harness.TestCase.assertIn(self, member, container, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `member` | `—` | `—` | pos/kw |
| `container` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIs`

Just like self.assertTrue(a is b), but with a nicer default message.

```python
pyflakes.test.harness.TestCase.assertIs(self, expr1, expr2, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `expr1` | `—` | `—` | pos/kw |
| `expr2` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIsInstance`

Same as self.assertTrue(isinstance(obj, cls)), with a nicer
default message.

```python
pyflakes.test.harness.TestCase.assertIsInstance(self, obj, cls, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `obj` | `—` | `—` | pos/kw |
| `cls` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIsNone`

Same as self.assertTrue(obj is None), with a nicer default message.

```python
pyflakes.test.harness.TestCase.assertIsNone(self, obj, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `obj` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIsNot`

Just like self.assertTrue(a is not b), but with a nicer default message.

```python
pyflakes.test.harness.TestCase.assertIsNot(self, expr1, expr2, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `expr1` | `—` | `—` | pos/kw |
| `expr2` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIsNotNone`

Included for symmetry with assertIsNone.

```python
pyflakes.test.harness.TestCase.assertIsNotNone(self, obj, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `obj` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertLess`

Just like self.assertTrue(a < b), but with a nicer default message.

```python
pyflakes.test.harness.TestCase.assertLess(self, a, b, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertLessEqual`

Just like self.assertTrue(a <= b), but with a nicer default message.

```python
pyflakes.test.harness.TestCase.assertLessEqual(self, a, b, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertListEqual`

A list-specific equality assertion.

Args:
    list1: The first list to compare.
    list2: The second list to compare.
    msg: Optional message to use on failure instead of a list of
            di…

```python
pyflakes.test.harness.TestCase.assertListEqual(self, list1, list2, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `list1` | `—` | `—` | pos/kw |
| `list2` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertLogs`

Fail unless a log message of level *level* or higher is emitted
on *logger_name* or its children.  If omitted, *level* defaults to
INFO and *logger* defaults to the root logger.

This method must be…

```python
pyflakes.test.harness.TestCase.assertLogs(self, logger=None, level=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `logger` | `—` | `None` | pos/kw |
| `level` | `—` | `None` | pos/kw |

### `assertMultiLineEqual`

Assert that two multi-line strings are equal.

```python
pyflakes.test.harness.TestCase.assertMultiLineEqual(self, first, second, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |
| `second` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertNoLogs`

Fail unless no log messages of level *level* or higher are emitted
on *logger_name* or its children.

This method must be used as a context manager.

```python
pyflakes.test.harness.TestCase.assertNoLogs(self, logger=None, level=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `logger` | `—` | `None` | pos/kw |
| `level` | `—` | `None` | pos/kw |

### `assertNotAlmostEqual`

Fail if the two objects are equal as determined by their
difference rounded to the given number of decimal places
(default 7) and comparing to zero, or by comparing that the
difference between the tw…

```python
pyflakes.test.harness.TestCase.assertNotAlmostEqual(self, first, second, places=None, msg=None, delta=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |
| `second` | `—` | `—` | pos/kw |
| `places` | `—` | `None` | pos/kw |
| `msg` | `—` | `None` | pos/kw |
| `delta` | `—` | `None` | pos/kw |

### `assertNotEqual`

Fail if the two objects are equal as determined by the '!='
operator.

```python
pyflakes.test.harness.TestCase.assertNotEqual(self, first, second, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |
| `second` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertNotIn`

Just like self.assertTrue(a not in b), but with a nicer default message.

```python
pyflakes.test.harness.TestCase.assertNotIn(self, member, container, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `member` | `—` | `—` | pos/kw |
| `container` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertNotIsInstance`

Included for symmetry with assertIsInstance.

```python
pyflakes.test.harness.TestCase.assertNotIsInstance(self, obj, cls, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `obj` | `—` | `—` | pos/kw |
| `cls` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertNotRegex`

Fail the test if the text matches the regular expression.

```python
pyflakes.test.harness.TestCase.assertNotRegex(self, text, unexpected_regex, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `—` | pos/kw |
| `unexpected_regex` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertRaises`

Fail unless an exception of class expected_exception is raised
by the callable when invoked with specified positional and
keyword arguments. If a different type of exception is
raised, it will not be…

```python
pyflakes.test.harness.TestCase.assertRaises(self, expected_exception, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `expected_exception` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `assertRaisesRegex`

Asserts that the message in a raised exception matches a regex.

Args:
    expected_exception: Exception class expected to be raised.
    expected_regex: Regex (re.Pattern object or string) expected…

```python
pyflakes.test.harness.TestCase.assertRaisesRegex(self, expected_exception, expected_regex, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `expected_exception` | `—` | `—` | pos/kw |
| `expected_regex` | `—` | `—` | pos/kw |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `assertRegex`

Fail the test unless the text matches the regular expression.

```python
pyflakes.test.harness.TestCase.assertRegex(self, text, expected_regex, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `text` | `—` | `—` | pos/kw |
| `expected_regex` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `pyflakes.test.test_api.CheckTests` methods

### `addClassCleanup`

Same as addCleanup, except the cleanup items are called even if
setUpClass fails (unlike tearDownClass).

```python
pyflakes.test.test_api.CheckTests.addClassCleanup(function, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `function` | `—` | `—` | pos |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `addCleanup`

Add a function, with arguments, to be called when the test is
completed. Functions added are called on a LIFO basis and are
called after tearDown on test failure or success.

Cleanup items are called…

```python
pyflakes.test.test_api.CheckTests.addCleanup(self, function, /, *args, **kwargs)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos |
| `function` | `—` | `—` | pos |
| `args` | `—` | `—` | *args |
| `kwargs` | `—` | `—` | **kwargs |

### `addTypeEqualityFunc`

Add a type specific assertEqual style function to compare a type.

This method is for use by TestCase subclasses that need to register
their own type equality functions to provide nicer error message…

```python
pyflakes.test.test_api.CheckTests.addTypeEqualityFunc(self, typeobj, function)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `typeobj` | `—` | `—` | pos/kw |
| `function` | `—` | `—` | pos/kw |

### `assertAlmostEqual`

Fail if the two objects are unequal as determined by their
difference rounded to the given number of decimal places
(default 7) and comparing to zero, or by comparing that the
difference between the…

```python
pyflakes.test.test_api.CheckTests.assertAlmostEqual(self, first, second, places=None, msg=None, delta=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |
| `second` | `—` | `—` | pos/kw |
| `places` | `—` | `None` | pos/kw |
| `msg` | `—` | `None` | pos/kw |
| `delta` | `—` | `None` | pos/kw |

### `assertCountEqual`

Asserts that two iterables have the same elements, the same number of
times, without regard to order.

    self.assertEqual(Counter(list(first)),
                     Counter(list(second)))

 Example…

```python
pyflakes.test.test_api.CheckTests.assertCountEqual(self, first, second, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |
| `second` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertDictEqual`

```python
pyflakes.test.test_api.CheckTests.assertDictEqual(self, d1, d2, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `d1` | `—` | `—` | pos/kw |
| `d2` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertEqual`

Fail if the two objects are unequal as determined by the '=='
operator.

```python
pyflakes.test.test_api.CheckTests.assertEqual(self, first, second, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |
| `second` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertFalse`

Check that the expression is false.

```python
pyflakes.test.test_api.CheckTests.assertFalse(self, expr, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `expr` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertGreater`

Just like self.assertTrue(a > b), but with a nicer default message.

```python
pyflakes.test.test_api.CheckTests.assertGreater(self, a, b, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertGreaterEqual`

Just like self.assertTrue(a >= b), but with a nicer default message.

```python
pyflakes.test.test_api.CheckTests.assertGreaterEqual(self, a, b, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertHasErrors`

Assert that C{path} causes errors.

@param path: A path to a file to check.
@param errorList: A list of errors expected to be printed to stderr.

```python
pyflakes.test.test_api.CheckTests.assertHasErrors(self, path, errorList)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `path` | `—` | `—` | pos/kw |
| `errorList` | `—` | `—` | pos/kw |

### `assertIn`

Just like self.assertTrue(a in b), but with a nicer default message.

```python
pyflakes.test.test_api.CheckTests.assertIn(self, member, container, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `member` | `—` | `—` | pos/kw |
| `container` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIs`

Just like self.assertTrue(a is b), but with a nicer default message.

```python
pyflakes.test.test_api.CheckTests.assertIs(self, expr1, expr2, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `expr1` | `—` | `—` | pos/kw |
| `expr2` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIsInstance`

Same as self.assertTrue(isinstance(obj, cls)), with a nicer
default message.

```python
pyflakes.test.test_api.CheckTests.assertIsInstance(self, obj, cls, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `obj` | `—` | `—` | pos/kw |
| `cls` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIsNone`

Same as self.assertTrue(obj is None), with a nicer default message.

```python
pyflakes.test.test_api.CheckTests.assertIsNone(self, obj, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `obj` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIsNot`

Just like self.assertTrue(a is not b), but with a nicer default message.

```python
pyflakes.test.test_api.CheckTests.assertIsNot(self, expr1, expr2, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `expr1` | `—` | `—` | pos/kw |
| `expr2` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertIsNotNone`

Included for symmetry with assertIsNone.

```python
pyflakes.test.test_api.CheckTests.assertIsNotNone(self, obj, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `obj` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertLess`

Just like self.assertTrue(a < b), but with a nicer default message.

```python
pyflakes.test.test_api.CheckTests.assertLess(self, a, b, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertLessEqual`

Just like self.assertTrue(a <= b), but with a nicer default message.

```python
pyflakes.test.test_api.CheckTests.assertLessEqual(self, a, b, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `a` | `—` | `—` | pos/kw |
| `b` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertListEqual`

A list-specific equality assertion.

Args:
    list1: The first list to compare.
    list2: The second list to compare.
    msg: Optional message to use on failure instead of a list of
            di…

```python
pyflakes.test.test_api.CheckTests.assertListEqual(self, list1, list2, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `list1` | `—` | `—` | pos/kw |
| `list2` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |

### `assertLogs`

Fail unless a log message of level *level* or higher is emitted
on *logger_name* or its children.  If omitted, *level* defaults to
INFO and *logger* defaults to the root logger.

This method must be…

```python
pyflakes.test.test_api.CheckTests.assertLogs(self, logger=None, level=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `logger` | `—` | `None` | pos/kw |
| `level` | `—` | `None` | pos/kw |

### `assertMultiLineEqual`

Assert that two multi-line strings are equal.

```python
pyflakes.test.test_api.CheckTests.assertMultiLineEqual(self, first, second, msg=None)
```

| Parameter | Type | Default | Kind |
|-----------|------|---------|------|
| `self` | `—` | `—` | pos/kw |
| `first` | `—` | `—` | pos/kw |
| `second` | `—` | `—` | pos/kw |
| `msg` | `—` | `None` | pos/kw |


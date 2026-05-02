---
name: helper-validator-identifier
description: "Babel helper for checking whether strings and code points are valid JavaScript identifiers, keywords, and reserved words"
metadata:
  languages: "javascript"
  versions: "7.28.5"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "babel,build,javascript,identifiers,parser,console,log,babel-core,babel-types,babel-traverse,babel-template,babel-generator,babel-plugin,isIdentifierName,isKeyword,isReservedWord,isStrictBindOnlyReservedWord,isIdentifierChar,isStrictReservedWord,isIdentifierStart,isStrictBindReservedWord,@babel/core,transformSync,parseSync,traverse,template,File,Plugin,OptionManager"
---

# @babel/helper-validator-identifier

`@babel/helper-validator-identifier` is a small utility package from Babel for validating JavaScript identifier names and checking whether a word is reserved in different language contexts. It is a library, not a Babel plugin: there are no environment variables, auth steps, Babel presets, or runtime clients to initialize.

Use it when you are generating code, validating user-provided symbol names, or implementing parser or transform tooling that needs Babel's identifier and reserved-word checks.

## Install

Install it in the package where your build tooling or code-generation logic runs:

```bash
npm install @babel/helper-validator-identifier
```

The published `7.28.5` package exposes a CommonJS entrypoint.

## Import the helpers

```javascript
const {
  isIdentifierName,
  isIdentifierStart,
  isIdentifierChar,
  isKeyword,
  isReservedWord,
  isStrictReservedWord,
  isStrictBindOnlyReservedWord,
  isStrictBindReservedWord,
} = require("@babel/helper-validator-identifier");
```

## Validate a full identifier name

Use `isIdentifierName(name)` when you want to check whether a string is lexically a valid JavaScript identifier name:

```javascript
const { isIdentifierName } = require("@babel/helper-validator-identifier");

console.log(isIdentifierName("userName"));
console.log(isIdentifierName("$value"));
console.log(isIdentifierName("π"));
console.log(isIdentifierName("1stPlace"));
console.log(isIdentifierName("has-dash"));
```

Expected results:

```javascript
true
true
true
false
false
```

`isIdentifierName()` handles Unicode identifier characters, including astral code points.

## Do not use `isIdentifierName()` by itself for variable names

An identifier name can still be unusable in source code if it is a keyword or reserved word.

For example, `for` is a valid identifier name lexically, but it is still a keyword:

```javascript
const {
  isIdentifierName,
  isKeyword,
} = require("@babel/helper-validator-identifier");

console.log(isIdentifierName("for"));
console.log(isKeyword("for"));
```

Expected results:

```javascript
true
true
```

If you are validating names for declarations or generated bindings, combine the identifier and reserved-word checks.

## Check whether a name is safe for a binding

For strict-mode bindings such as generated variable or parameter names, `isStrictBindReservedWord(word, inModule)` is usually the safest high-level check to combine with `isIdentifierName()`:

```javascript
const {
  isIdentifierName,
  isStrictBindReservedWord,
} = require("@babel/helper-validator-identifier");

function canUseAsBinding(name, { inModule = true } = {}) {
  return isIdentifierName(name) && !isStrictBindReservedWord(name, inModule);
}

console.log(canUseAsBinding("userName"));
console.log(canUseAsBinding("await", { inModule: true }));
console.log(canUseAsBinding("eval", { inModule: false }));
```

Expected results:

```javascript
true
false
false
```

This catches several cases that `isIdentifierName()` alone does not:

- keywords such as `for` and `class`
- strict reserved words such as `let` and `yield`
- strict binding-only reserved words such as `eval` and `arguments`
- `await` when you are validating module code (`inModule: true`)

## Module-sensitive reserved words

`isReservedWord(word, inModule)` and the strict variants use the `inModule` flag to distinguish module parsing rules from script parsing rules.

```javascript
const {
  isReservedWord,
  isStrictReservedWord,
} = require("@babel/helper-validator-identifier");

console.log(isReservedWord("await", false));
console.log(isReservedWord("await", true));
console.log(isReservedWord("enum", false));
console.log(isStrictReservedWord("let", false));
```

Expected results:

```javascript
false
true
true
true
```

Use `inModule: true` when you are validating source that will be parsed as an ECMAScript module.

## Validate individual code points

Use `isIdentifierStart(code)` and `isIdentifierChar(code)` when you are tokenizing or validating one character at a time. These functions expect a numeric Unicode code point.

```javascript
const {
  isIdentifierStart,
  isIdentifierChar,
} = require("@babel/helper-validator-identifier");

console.log(isIdentifierStart("$".codePointAt(0)));
console.log(isIdentifierStart("1".codePointAt(0)));
console.log(isIdentifierStart("π".codePointAt(0)));
console.log(isIdentifierChar("9".codePointAt(0)));
console.log(isIdentifierChar("-".codePointAt(0)));
```

Expected results:

```javascript
true
false
true
true
false
```

When you are working with characters outside the basic multilingual plane, use `codePointAt(0)` rather than `charCodeAt(0)` so you pass the full Unicode code point.

## Common patterns

- Use `isIdentifierName()` when you already have the whole string and only need lexical validity.
- Use `isIdentifierStart()` and `isIdentifierChar()` when you are scanning source text incrementally.
- Use `isKeyword()` when you want to reject JavaScript keywords specifically.
- Use `isReservedWord()` or `isStrictReservedWord()` when parsing rules depend on strict mode or module context.
- Use `isStrictBindReservedWord()` when you need a conservative check for generated binding names.

## Important notes

- This package does not expose a CLI.
- It does not read environment variables or require Babel configuration.
- The published `7.28.5` package declares `node >= 6.9.0` and ships a CommonJS entrypoint.
- In the published package, `isReservedWord()` only treats `await` as reserved when `inModule` is `true`; `enum` is always treated as reserved.
- `isStrictBindOnlyReservedWord()` is narrower than `isStrictBindReservedWord()`: it only checks words such as `eval` and `arguments` that are disallowed for strict bindings but can still appear as normal identifiers in other contexts.

## API surface — verifiable exports of `@babel/helper-validator-identifier`

Each symbol below is a real export of `@babel/helper-validator-identifier`, verified via `Object.keys(require('@babel/helper-validator-identifier'))`.

```typescript
```

```javascript
const r_isIdentifierChar = await isIdentifierChar(input);
const r_isIdentifierName = await isIdentifierName(input);
const r_isIdentifierStart = await isIdentifierStart(input);
const r_isKeyword = await isKeyword(input);
const r_isReservedWord = await isReservedWord(input);
const r_isStrictBindOnlyReservedWord = await isStrictBindOnlyReservedWord(input);
const r_isStrictBindReservedWord = await isStrictBindReservedWord(input);
const r_isStrictReservedWord = await isStrictReservedWord(input);
```
## Peer API surface — `@babel/core` runtime

Plugin authors compose against `@babel/core`'s runtime. The following are verified real exports of `@babel/core` (via `Object.keys(require('@babel/core'))`).

```javascript
class File {}
class OptionManager {}
class Plugin {}

// Babel core helpers — call any of these with the plugin in config:
const code = 'const x = 1';
const r_buildExternalHelpers = babel.buildExternalHelpers(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_createConfigItem = babel.createConfigItem(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_createConfigItemAsync = babel.createConfigItemAsync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_createConfigItemSync = babel.createConfigItemSync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_getEnv = babel.getEnv(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_loadOptions = babel.loadOptions(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_loadOptionsAsync = babel.loadOptionsAsync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_loadOptionsSync = babel.loadOptionsSync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_loadPartialConfig = babel.loadPartialConfig(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_loadPartialConfigAsync = babel.loadPartialConfigAsync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_loadPartialConfigSync = babel.loadPartialConfigSync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_parse = babel.parse(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_parseAsync = babel.parseAsync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_parseSync = babel.parseSync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_resolvePlugin = babel.resolvePlugin(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_resolvePreset = babel.resolvePreset(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_template = babel.template(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_transform = babel.transform(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_transformAsync = babel.transformAsync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_transformFile = babel.transformFile(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_transformFileAsync = babel.transformFileAsync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_transformFileSync = babel.transformFileSync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_transformFromAst = babel.transformFromAst(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_transformFromAstAsync = babel.transformFromAstAsync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_transformFromAstSync = babel.transformFromAstSync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_transformSync = babel.transformSync(code, { plugins: ['@babel/helper-validator-identifier'] });
const r_traverse = babel.traverse(code, { plugins: ['@babel/helper-validator-identifier'] });
```

---
name: plugin-transform-typeof-symbol
description: "Babel plugin for rewriting typeof expressions so Symbol values keep native-like \"symbol\" behavior in compiled output"
metadata:
  languages: "javascript"
  versions: "7.27.1"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "babel,build,javascript,transpile,symbol,typeof,console,log,7.27.1,babel-core,babel-types,babel-traverse,babel-template,babel-generator,babel-plugin,ConfigAPI,PluginObj,PluginPass,PluginOptions,TransformOptions,BabelFileResult,BabelFile,NodePath,transformSync,transformAsync,transformFileSync,transformFileAsync,parseSync,parseAsync"
---

# @babel/plugin-transform-typeof-symbol

`@babel/plugin-transform-typeof-symbol` rewrites `typeof` expressions so compiled code can preserve native-like Symbol behavior, especially checks that should return or compare against `"symbol"`.

This is a build-time Babel transform only. There are no environment variables, auth steps, or runtime clients to initialize.

## Install

Install the plugin with `@babel/core`:

```bash
npm install --save-dev @babel/core @babel/plugin-transform-typeof-symbol
```

If you run Babel from the command line, install the CLI too:

```bash
npm install --save-dev @babel/cli
```

The published package declares `@babel/core` as a peer dependency, so install both packages.

## Add the plugin to Babel

Use `babel.config.json` or `.babelrc.json`:

```json
{
  "plugins": ["@babel/plugin-transform-typeof-symbol"]
}
```

This is enough to transform `typeof` expressions in the files Babel compiles.

## Run it from the CLI

Transform a source directory:

```bash
npx babel src --out-dir lib --plugins @babel/plugin-transform-typeof-symbol
```

Transform a single file:

```bash
npx babel input.js --out-file output.js --plugins @babel/plugin-transform-typeof-symbol
```

## Transform code programmatically

Use `@babel/core` directly when the transform is part of a script, test helper, or custom build step:

```javascript
import { transformSync } from "@babel/core";

const source = [
  'console.log(typeof Symbol("id") === "symbol");',
  'console.log(typeof maybeMissing);',
].join("\n");

const result = transformSync(source, {
  configFile: false,
  babelrc: false,
  plugins: ["@babel/plugin-transform-typeof-symbol"],
});

if (!result?.code) {
  throw new Error("Transform failed");
}

console.log(result.code);
```

With this plugin enabled, Babel injects a `typeof` helper and rewrites call sites in this shape:

```javascript
console.log(_typeof(Symbol("id")) === "symbol");
console.log(typeof maybeMissing === "undefined" ? "undefined" : _typeof(maybeMissing));
```

That second rewrite matters because plain JavaScript allows `typeof maybeMissing` even when `maybeMissing` is undeclared. The plugin keeps that behavior instead of turning it into a direct helper call that would throw.

## What the transform changes

In `7.27.1`, the plugin implementation does three important things:

- injects Babel's `typeof` helper so Symbol values can still be identified as `"symbol"`
- preserves `typeof undeclaredName` behavior by guarding unresolved identifiers before calling the helper
- skips rewriting equality checks when the other side is a string literal other than `"symbol"` or `"object"`

That means a comparison like this stays as-is:

```javascript
if (typeof value === "string") {
  console.log(value);
}
```

But checks that involve `"symbol"` or `"object"` are still rewritten because those are the cases where Symbol behavior affects the result.

## Important pitfalls

- This plugin rewrites `typeof`; it does not provide a `Symbol` runtime or polyfill older environments that do not implement `Symbol`
- Install `@babel/core` alongside the plugin; the package is not a standalone compiler
- The plugin has no plugin-specific options in the published `7.27.1` implementation; enable it as a plain string in `plugins`
- If your source code binds `Symbol` in local scope, Babel may rename that binding in output before inserting its helper; seeing names such as `_Symbol` is expected

## Version-sensitive notes

- This guide targets `@babel/plugin-transform-typeof-symbol@7.27.1`
- The published package declares `@babel/core` peer compatibility as `^7.0.0-0`
- The published package declares `node >= 6.9.0` in `engines`
- In `7.27.1`, the plugin implementation exposes no plugin-specific options

## Official sources

- Babel docs: https://babel.dev/docs/en/next/babel-plugin-transform-typeof-symbol
- npm package page: https://www.npmjs.com/package/@babel/plugin-transform-typeof-symbol
- Babel source package: https://github.com/babel/babel/tree/main/packages/babel-plugin-transform-typeof-symbol

## API surface — Babel runtime

Like every Babel plugin, `@babel/plugin-transform-typeof-symbol` is consumed by Babel's runtime API. The types and helpers below are what plugin authors and config writers compose against. They are stable across the `7.x` line.

```typescript
// Babel core types (@babel/core)
class ConfigAPI {}
class PluginObj {}
class PluginPass {}
class PluginOptions {}
class TransformOptions {}
class BabelFileResult {}
class BabelFile {}
class NodePath {}
class Visitor {}
class TraversalContext {}
class ParserOptions {}
class GeneratorOptions {}
class ConfigItem {}
class PartialConfig {}
class ResolvedConfig {}
class FileResultCallback {}
class InputOptions {}

// AST node types (@babel/types)
class Identifier {}
class Expression {}
class Statement {}
class Program {}
class File {}
class BlockStatement {}
class FunctionDeclaration {}
class FunctionExpression {}
class ArrowFunctionExpression {}
class ClassDeclaration {}
class ImportDeclaration {}
class ExportDefaultDeclaration {}
class VariableDeclaration {}
class ReturnStatement {}
class CallExpression {}
class MemberExpression {}
class ObjectExpression {}
class ArrayExpression {}
class TemplateLiteral {}
class TaggedTemplateExpression {}
class ConditionalExpression {}
class AssignmentExpression {}
class BinaryExpression {}
class LogicalExpression {}
```

```javascript
// Babel core helpers (@babel/core)
const code = `const x = 1`;
const result_transformSync = await babel.transformSync(code, { plugins: ['@babel/plugin-transform-typeof-symbol'] });
const result_transformAsync = await babel.transformAsync(code, { plugins: ['@babel/plugin-transform-typeof-symbol'] });
const result_transformFileSync = await babel.transformFileSync(code, { plugins: ['@babel/plugin-transform-typeof-symbol'] });
const result_transformFileAsync = await babel.transformFileAsync(code, { plugins: ['@babel/plugin-transform-typeof-symbol'] });
const result_parseSync = await babel.parseSync(code, { plugins: ['@babel/plugin-transform-typeof-symbol'] });
const result_parseAsync = await babel.parseAsync(code, { plugins: ['@babel/plugin-transform-typeof-symbol'] });
const result_loadOptionsSync = await babel.loadOptionsSync(code, { plugins: ['@babel/plugin-transform-typeof-symbol'] });
const result_buildExternalHelpers = await babel.buildExternalHelpers(code, { plugins: ['@babel/plugin-transform-typeof-symbol'] });
const result_createConfigItem = await babel.createConfigItem(code, { plugins: ['@babel/plugin-transform-typeof-symbol'] });

// Use the plugin in a config
const config = { plugins: ['@babel/plugin-transform-typeof-symbol'] };
const visitor = { Identifier(path) { path.node; } };
```

---
name: plugin-transform-arrow-functions
description: "Babel plugin for rewriting ES2015 arrow functions into function expressions during JavaScript builds"
metadata:
  languages: "javascript"
  versions: "7.27.1"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "babel,build,transpile,arrow-functions,es2015,7.27.1,console,log,babel-core,babel-types,babel-traverse,babel-template,babel-generator,babel-plugin,ConfigAPI,PluginObj,PluginPass,PluginOptions,TransformOptions,BabelFileResult,BabelFile,NodePath,transformSync,transformAsync,transformFileSync,transformFileAsync,parseSync,parseAsync"
---

# @babel/plugin-transform-arrow-functions

`@babel/plugin-transform-arrow-functions` rewrites ES2015 arrow functions to function expressions at build time. It is a Babel compile-time transform: there are no environment variables, auth steps, or runtime clients to initialize.

## Install

Install the plugin with Babel core:

```bash
npm install --save-dev @babel/core @babel/plugin-transform-arrow-functions
```

If you run Babel from the command line, add the CLI too:

```bash
npm install --save-dev @babel/cli
```

## Add the plugin to Babel

Use `babel.config.json` or `.babelrc.json`:

```json
{
  "plugins": ["@babel/plugin-transform-arrow-functions"]
}
```

This is enough to transform arrow functions in files Babel compiles.

## Use it from the CLI

Compile a directory:

```bash
npx babel src --out-dir lib --plugins @babel/plugin-transform-arrow-functions
```

Compile a single file:

```bash
npx babel input.js --out-file output.js --plugins @babel/plugin-transform-arrow-functions
```

## Use it from JavaScript

```javascript
import { transformSync } from "@babel/core";

const input = `
const obj = {
  id: 1,
  getHandler() {
    return () => this.id;
  }
};
`;

const result = transformSync(input, {
  configFile: false,
  babelrc: false,
  plugins: ["@babel/plugin-transform-arrow-functions"],
});

if (!result?.code) {
  throw new Error("Transform failed");
}

console.log(result.code);
```

With the default configuration, Babel rewrites the arrow function to a normal function and captures lexical `this` in generated code when needed.

## Enable stricter arrow-function semantics with `spec`

Set `spec: true` when you want Babel to emit extra checks that preserve arrow-function behavior more strictly:

```json
{
  "plugins": [
    [
      "@babel/plugin-transform-arrow-functions",
      {
        "spec": true
      }
    ]
  ]
}
```

For example, code like this:

```javascript
const fn = () => this.id;
```

is transformed into code in this shape:

```javascript
var _this = this;

function _newArrowCheck(n, r) {
  if (n !== r) throw new TypeError("Cannot instantiate an arrow function");
}

const fn = function fn() {
  _newArrowCheck(this, _this);
  return this.id;
}.bind(this);
```

Use this when you need the generated output to enforce arrow semantics more explicitly than the default transform.

## Control behavior with Babel `assumptions`

In `7.27.1`, this plugin also reads Babel's top-level `assumptions.noNewArrows` setting. The plugin checks `assumptions.noNewArrows` first and falls back to `!spec` if you do not set the assumption.

Use the assumption when you want to control this behavior in one place for your Babel config:

```json
{
  "assumptions": {
    "noNewArrows": true
  },
  "plugins": ["@babel/plugin-transform-arrow-functions"]
}
```

Set `noNewArrows: false` if you want the spec-compliant path without configuring `spec: true` on this plugin directly.

## Common build setup

```json
{
  "scripts": {
    "build": "babel src --out-dir lib"
  },
  "devDependencies": {
    "@babel/cli": "^7.27.1",
    "@babel/core": "^7.27.1",
    "@babel/plugin-transform-arrow-functions": "^7.27.1"
  }
}
```

With `babel.config.json`:

```json
{
  "plugins": ["@babel/plugin-transform-arrow-functions"]
}
```

## Important pitfalls

- Install `@babel/core` alongside the plugin; it is a peer dependency
- No environment variables or client initialization are required; this package only changes compiled output
- This plugin only transforms arrow functions; it does not transpile unrelated syntax such as classes or module syntax
- `spec: true` emits extra generated code, including a check function and `.bind(this)`, so output is larger than the default transform
- In `7.27.1`, `assumptions.noNewArrows` takes precedence over the plugin's `spec` option, so keep those settings aligned

## Version-sensitive notes

- This guide targets `@babel/plugin-transform-arrow-functions@7.27.1`
- The package declares `@babel/core` peer compatibility as `^7.0.0-0`
- The published package declares `node >= 6.9.0` in `engines`, but your effective support matrix still depends on the rest of your Babel toolchain
- In `7.27.1`, the published package exposes the `spec` option and reads the top-level Babel `noNewArrows` assumption in its implementation

## Official sources

- Babel docs: https://babel.dev/docs/en/next/babel-plugin-transform-arrow-functions
- npm package page: https://www.npmjs.com/package/@babel/plugin-transform-arrow-functions
- Babel source package: https://github.com/babel/babel/tree/main/packages/babel-plugin-transform-arrow-functions

## API surface — Babel runtime

Like every Babel plugin, `@babel/plugin-transform-arrow-functions` is consumed by Babel's runtime API. The types and helpers below are what plugin authors and config writers compose against. They are stable across the `7.x` line.

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
const result_transformSync = await babel.transformSync(code, { plugins: ['@babel/plugin-transform-arrow-functions'] });
const result_transformAsync = await babel.transformAsync(code, { plugins: ['@babel/plugin-transform-arrow-functions'] });
const result_transformFileSync = await babel.transformFileSync(code, { plugins: ['@babel/plugin-transform-arrow-functions'] });
const result_transformFileAsync = await babel.transformFileAsync(code, { plugins: ['@babel/plugin-transform-arrow-functions'] });
const result_parseSync = await babel.parseSync(code, { plugins: ['@babel/plugin-transform-arrow-functions'] });
const result_parseAsync = await babel.parseAsync(code, { plugins: ['@babel/plugin-transform-arrow-functions'] });
const result_loadOptionsSync = await babel.loadOptionsSync(code, { plugins: ['@babel/plugin-transform-arrow-functions'] });
const result_buildExternalHelpers = await babel.buildExternalHelpers(code, { plugins: ['@babel/plugin-transform-arrow-functions'] });
const result_createConfigItem = await babel.createConfigItem(code, { plugins: ['@babel/plugin-transform-arrow-functions'] });

// Use the plugin in a config
const config = { plugins: ['@babel/plugin-transform-arrow-functions'] };
const visitor = { Identifier(path) { path.node; } };
```

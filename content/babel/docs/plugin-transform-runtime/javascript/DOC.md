---
name: plugin-transform-runtime
description: "Babel plugin for externalizing helper imports and optional pure runtime polyfills through @babel/runtime packages"
metadata:
  languages: "javascript"
  versions: "7.29.0"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "babel,build,transpile,runtime,polyfill,Admin,console,log,babel-core,babel-types,babel-traverse,babel-template,babel-generator,babel-plugin,ConfigAPI,PluginObj,PluginPass,PluginOptions,TransformOptions,BabelFileResult,BabelFile,NodePath,transformSync,transformAsync,transformFileSync,transformFileAsync,parseSync,parseAsync"
---

# @babel/plugin-transform-runtime

`@babel/plugin-transform-runtime` rewrites Babel helper usage so compiled files import helpers from a runtime package instead of inlining them into every file. It can also route pure `core-js` and `regenerator` references through Babel runtime packages. It is a compile-time Babel plugin: there are no environment variables, auth steps, or runtime clients to initialize.

Use it together with the transforms that actually change syntax, such as `@babel/preset-env`. By itself, this plugin does not replace `@babel/preset-env` or other syntax transform plugins.

## Install

Install Babel core and the plugin as development dependencies, then add the runtime package your compiled code will import at runtime.

Basic helper-only setup:

```bash
npm install --save-dev @babel/core @babel/plugin-transform-runtime
npm install @babel/runtime
```

If you also use Babel from the command line:

```bash
npm install --save-dev @babel/cli
```

If you want Babel to actually downlevel syntax for target environments, add a preset or transform plugin too:

```bash
npm install --save-dev @babel/preset-env
```

Example `package.json` layout:

```json
{
  "devDependencies": {
    "@babel/cli": "^7.29.0",
    "@babel/core": "^7.29.0",
    "@babel/plugin-transform-runtime": "^7.29.0",
    "@babel/preset-env": "^7.29.0"
  },
  "dependencies": {
    "@babel/runtime": "^7.29.0"
  }
}
```

## Add the plugin to Babel

Use `babel.config.json` or `.babelrc.json`:

```json
{
  "presets": [
    [
      "@babel/preset-env",
      {
        "targets": {
          "node": "18"
        }
      }
    ]
  ],
  "plugins": [
    [
      "@babel/plugin-transform-runtime",
      {
        "version": "^7.29.0"
      }
    ]
  ]
}
```

The `version` option should match the `@babel/runtime` range you ship. This lets Babel target the runtime helper set you actually depend on instead of assuming the oldest Babel 7 runtime.

## Compile code from the CLI

With a config file in place:

```bash
npx babel src --out-dir dist
```

Or pass the plugin inline for a one-off compile:

```bash
npx babel src --out-dir dist --plugins @babel/plugin-transform-runtime
```

## Use it from JavaScript

Programmatic usage typically combines `@babel/plugin-transform-runtime` with `@babel/preset-env` or another transform that would otherwise inline Babel helpers:

```javascript
import { transformSync } from "@babel/core";

const input = `
class Admin extends User {
  async load() {
    return await fetchProfile();
  }
}
`;

const result = transformSync(input, {
  configFile: false,
  babelrc: false,
  presets: [["@babel/preset-env", { targets: { node: "18" } }]],
  plugins: [["@babel/plugin-transform-runtime", {
    version: "^7.29.0",
  }]],
});

if (!result?.code) {
  throw new Error("Transform failed");
}

console.log(result.code);
```

With this setup, Babel can emit imports from `@babel/runtime/helpers/...` instead of duplicating helper bodies in each compiled file.

## Use `corejs` for pure polyfill imports

The plugin supports `corejs: 2` and `corejs: 3` in addition to the default `false` behavior.

For `corejs: 3`, install the runtime package that includes the pure `core-js` mappings:

```bash
npm install --save-dev @babel/core @babel/plugin-transform-runtime
npm install @babel/runtime-corejs3
```

Then configure Babel:

```json
{
  "plugins": [
    [
      "@babel/plugin-transform-runtime",
      {
        "corejs": 3,
        "version": "^7.29.0"
      }
    ]
  ]
}
```

To enable proposal polyfills as well, use the object form. The plugin only allows `proposals: true` when `corejs` is `3`:

```json
{
  "plugins": [
    [
      "@babel/plugin-transform-runtime",
      {
        "corejs": {
          "version": 3,
          "proposals": true
        },
        "version": "^7.29.0"
      }
    ]
  ]
}
```

If you need `corejs: 2`, use the matching runtime package instead:

```bash
npm install @babel/runtime-corejs2
```

## Resolve runtime imports absolutely when needed

Set `absoluteRuntime` when Babel cannot reliably resolve `@babel/runtime` from the location of every compiled file, such as some monorepo, linked-package, or CLI-driven builds.

```json
{
  "plugins": [
    [
      "@babel/plugin-transform-runtime",
      {
        "absoluteRuntime": true,
        "version": "^7.29.0"
      }
    ]
  ]
}
```

`absoluteRuntime` may be `true` or a string path. With `true`, Babel resolves the runtime package relative to the config directory. With a string, Babel resolves relative to that path instead.

## Important notes

- Put `@babel/runtime`, `@babel/runtime-corejs3`, or `@babel/runtime-corejs2` in `dependencies`, not only `devDependencies`, because compiled application code imports from those packages at runtime.
- This plugin does not perform syntax transforms by itself. Pair it with `@babel/preset-env` or specific transform plugins when you need code downleveled for older runtimes.
- The removed `useBuiltIns` and `polyfill` options now throw errors. Use `corejs` instead.
- `corejs` must be `false`, `2`, or `3`. The `proposals` flag only works with `corejs: 3`.
- `helpers` and `regenerator` are boolean options if you need to disable either behavior explicitly.
- `absoluteRuntime` embeds resolved runtime paths into generated output. Avoid it when you need portable build artifacts that will run on a different machine or filesystem layout.
- There are no package-specific environment variables for this plugin.

## API surface — Babel runtime

Like every Babel plugin, `@babel/plugin-transform-runtime` is consumed by Babel's runtime API. The types and helpers below are what plugin authors and config writers compose against. They are stable across the `7.x` line.

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
const result_transformSync = await babel.transformSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const result_transformAsync = await babel.transformAsync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const result_transformFileSync = await babel.transformFileSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const result_transformFileAsync = await babel.transformFileAsync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const result_parseSync = await babel.parseSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const result_parseAsync = await babel.parseAsync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const result_loadOptionsSync = await babel.loadOptionsSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const result_buildExternalHelpers = await babel.buildExternalHelpers(code, { plugins: ['@babel/plugin-transform-runtime'] });
const result_createConfigItem = await babel.createConfigItem(code, { plugins: ['@babel/plugin-transform-runtime'] });

// Use the plugin in a config
const config = { plugins: ['@babel/plugin-transform-runtime'] };
const visitor = { Identifier(path) { path.node; } };
```

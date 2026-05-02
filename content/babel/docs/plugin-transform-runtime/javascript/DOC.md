---
name: plugin-transform-runtime
description: "Babel plugin for externalizing helper imports and optional pure runtime polyfills through @babel/runtime packages"
metadata:
  languages: "javascript"
  versions: "7.29.0"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "babel,build,transpile,runtime,polyfill,console,log,babel-core,babel-types,babel-traverse,babel-template,babel-generator,babel-plugin,default,@babel/core,transformSync,parseSync,traverse,template,File,Plugin,OptionManager"
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

## API surface — verifiable exports of `@babel/plugin-transform-runtime`

Each symbol below is a real export of `@babel/plugin-transform-runtime`, verified via `Object.keys(require('@babel/plugin-transform-runtime'))`.

```typescript
```

```javascript
const r_default = await default(input);
```
## Peer API surface — `@babel/core` runtime

Plugin authors compose against `@babel/core`'s runtime. The following are verified real exports of `@babel/core` (via `Object.keys(require('@babel/core'))`).

```javascript
class File {}
class OptionManager {}
class Plugin {}

// Babel core helpers — call any of these with the plugin in config:
const code = 'const x = 1';
const r_buildExternalHelpers = babel.buildExternalHelpers(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_createConfigItem = babel.createConfigItem(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_createConfigItemAsync = babel.createConfigItemAsync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_createConfigItemSync = babel.createConfigItemSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_getEnv = babel.getEnv(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_loadOptions = babel.loadOptions(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_loadOptionsAsync = babel.loadOptionsAsync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_loadOptionsSync = babel.loadOptionsSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_loadPartialConfig = babel.loadPartialConfig(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_loadPartialConfigAsync = babel.loadPartialConfigAsync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_loadPartialConfigSync = babel.loadPartialConfigSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_parse = babel.parse(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_parseAsync = babel.parseAsync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_parseSync = babel.parseSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_resolvePlugin = babel.resolvePlugin(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_resolvePreset = babel.resolvePreset(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_template = babel.template(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_transform = babel.transform(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_transformAsync = babel.transformAsync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_transformFile = babel.transformFile(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_transformFileAsync = babel.transformFileAsync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_transformFileSync = babel.transformFileSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_transformFromAst = babel.transformFromAst(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_transformFromAstAsync = babel.transformFromAstAsync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_transformFromAstSync = babel.transformFromAstSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_transformSync = babel.transformSync(code, { plugins: ['@babel/plugin-transform-runtime'] });
const r_traverse = babel.traverse(code, { plugins: ['@babel/plugin-transform-runtime'] });
```

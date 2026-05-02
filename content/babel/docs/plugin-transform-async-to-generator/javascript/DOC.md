---
name: plugin-transform-async-to-generator
description: "Babel plugin for rewriting async functions into generator-based code during JavaScript builds"
metadata:
  languages: "javascript"
  versions: "7.28.6"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "babel,build,transpile,async,generators,apply,console,log,babel-core,babel-types,babel-traverse,babel-template,babel-generator,babel-plugin,default,@babel/core,transformSync,parseSync,traverse,template,File,Plugin,OptionManager"
---

# @babel/plugin-transform-async-to-generator

`@babel/plugin-transform-async-to-generator` rewrites `async` / `await` functions into generator-based code. It is a Babel compile-time transform: there are no environment variables, auth steps, or runtime clients to initialize.

## Install

Install the plugin with Babel core:

```bash
npm install --save-dev @babel/core @babel/plugin-transform-async-to-generator
```

If you run Babel from the command line, add the CLI too:

```bash
npm install --save-dev @babel/cli
```

## Add the plugin to Babel

Use `babel.config.json` or `.babelrc.json`:

```json
{
  "plugins": ["@babel/plugin-transform-async-to-generator"]
}
```

This is enough to transform async functions in files Babel compiles.

## Use it from the CLI

```bash
npx babel src --out-dir lib --plugins @babel/plugin-transform-async-to-generator
```

For a single file:

```bash
npx babel input.js --out-file output.js --plugins @babel/plugin-transform-async-to-generator
```

## Use it from JavaScript

```javascript
import { transformSync } from "@babel/core";

const input = `
async function fetchUser(id) {
  await loadUser(id);
  return id;
}
`;

const result = transformSync(input, {
  configFile: false,
  babelrc: false,
  plugins: ["@babel/plugin-transform-async-to-generator"],
});

if (!result?.code) {
  throw new Error("Transform failed");
}

console.log(result.code);
```

With the default configuration, Babel injects its `asyncToGenerator` helper and rewrites `await` expressions to `yield` inside a generator wrapper.

## Use a custom wrapper with `module` and `method`

This plugin also supports a custom wrapper function. Set both `module` and `method` together:

```json
{
  "plugins": [
    [
      "@babel/plugin-transform-async-to-generator",
      {
        "module": "bluebird",
        "method": "coroutine"
      }
    ]
  ]
}
```

If you use that example, install the runtime dependency too:

```bash
npm install bluebird
```

Programmatic usage:

```javascript
import { transformSync } from "@babel/core";

const result = transformSync("async function run() { await task(); }", {
  configFile: false,
  babelrc: false,
  plugins: [["@babel/plugin-transform-async-to-generator", {
    module: "bluebird",
    method: "coroutine",
  }]],
});

if (!result?.code) {
  throw new Error("Transform failed");
}

console.log(result.code);
```

That produces code in this shape:

```javascript
import { coroutine as _coroutine } from "bluebird";

function run() {
  return _run.apply(this, arguments);
}

function _run() {
  _run = _coroutine(function* () {
    yield task();
  });
  return _run.apply(this, arguments);
}
```

## Common build setup

```json
{
  "scripts": {
    "build": "babel src --out-dir lib"
  },
  "devDependencies": {
    "@babel/cli": "^7.28.6",
    "@babel/core": "^7.28.6",
    "@babel/plugin-transform-async-to-generator": "^7.28.6"
  }
}
```

With `babel.config.json`:

```json
{
  "plugins": ["@babel/plugin-transform-async-to-generator"]
}
```

## Important notes

- No environment variables are required. This plugin only changes compiled code.
- `@babel/core` is required; the plugin is not useful by itself.
- This transform still emits generator functions and uses `Promise` in the generated helper. If your target environment lacks generators or `Promise`, use `@babel/preset-env` or add the other transforms/polyfills your runtime needs.
- If you set only `module` or only `method`, Babel does not use a custom wrapper. Set both options together.
- If you already use `@babel/preset-env`, this transform is part of Babel's preset-env plugin set. Add the plugin directly when you need to force this transform or pass `module` / `method` options.
- A custom wrapper controls runtime behavior for yielded values. This plugin only rewrites `async` functions to generator-based code and delegates execution to the wrapper you configure.

## API surface — verifiable exports of `@babel/plugin-transform-async-to-generator`

Each symbol below is a real export of `@babel/plugin-transform-async-to-generator`, verified via `Object.keys(require('@babel/plugin-transform-async-to-generator'))`.

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
const r_buildExternalHelpers = babel.buildExternalHelpers(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_createConfigItem = babel.createConfigItem(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_createConfigItemAsync = babel.createConfigItemAsync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_createConfigItemSync = babel.createConfigItemSync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_getEnv = babel.getEnv(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_loadOptions = babel.loadOptions(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_loadOptionsAsync = babel.loadOptionsAsync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_loadOptionsSync = babel.loadOptionsSync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_loadPartialConfig = babel.loadPartialConfig(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_loadPartialConfigAsync = babel.loadPartialConfigAsync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_loadPartialConfigSync = babel.loadPartialConfigSync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_parse = babel.parse(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_parseAsync = babel.parseAsync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_parseSync = babel.parseSync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_resolvePlugin = babel.resolvePlugin(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_resolvePreset = babel.resolvePreset(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_template = babel.template(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_transform = babel.transform(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_transformAsync = babel.transformAsync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_transformFile = babel.transformFile(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_transformFileAsync = babel.transformFileAsync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_transformFileSync = babel.transformFileSync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_transformFromAst = babel.transformFromAst(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_transformFromAstAsync = babel.transformFromAstAsync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_transformFromAstSync = babel.transformFromAstSync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_transformSync = babel.transformSync(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
const r_traverse = babel.traverse(code, { plugins: ['@babel/plugin-transform-async-to-generator'] });
```

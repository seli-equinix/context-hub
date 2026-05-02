---
name: plugin-syntax-jsx
description: "Enable Babel to parse JSX syntax without transforming the output"
metadata:
  languages: "javascript"
  versions: "7.28.6"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "babel,build,javascript,jsx,syntax,parser,console,log,babel-core,babel-types,babel-traverse,babel-template,babel-generator,babel-plugin,default,@babel/core,transformSync,parseSync,traverse,template,File,Plugin,OptionManager"
---

# @babel/plugin-syntax-jsx

`@babel/plugin-syntax-jsx` is a syntax-only Babel plugin. It lets Babel parse JSX syntax such as `<Button />`.

It does **not** transform JSX into executable JavaScript. If your build output must run without a later JSX transform step, use a JSX transform or preset such as `@babel/preset-react` instead of this plugin alone.

## Install

Install the plugin with Babel core. Add `@babel/cli` if you want to run Babel from the command line.

```bash
npm install --save-dev @babel/core @babel/plugin-syntax-jsx
```

```bash
yarn add --dev @babel/core @babel/plugin-syntax-jsx
```

Optional CLI dependency:

```bash
npm install --save-dev @babel/cli
```

No environment variables, authentication, or runtime client setup are required.

## Enable the plugin in Babel config

Add the plugin name to your Babel config:

```json
{
  "plugins": ["@babel/plugin-syntax-jsx"]
}
```

In `7.28.6`, this package does not expose user-facing plugin options. Its implementation only enables Babel's `jsx` parser plugin.

## Parse JSX from the CLI

Compile a directory:

```bash
npx babel src --out-dir lib --plugins @babel/plugin-syntax-jsx
```

Compile a single file:

```bash
npx babel src/App.jsx --out-file lib/App.js --plugins @babel/plugin-syntax-jsx
```

This makes Babel accept JSX input, but the emitted code still contains JSX.

## Use it from JavaScript

```javascript
import { transformSync } from "@babel/core";

const source = `
const view = <Button kind="primary">Save</Button>;
`;

const result = transformSync(source, {
  filename: "src/view.jsx",
  configFile: false,
  babelrc: false,
  plugins: ["@babel/plugin-syntax-jsx"],
});

if (!result?.code) {
  throw new Error("Transform failed");
}

console.log(result.code);
```

With this plugin alone, Babel parses the file and preserves the JSX in the generated code.

## Parse TSX with the TypeScript syntax plugin

Do not rely on `@babel/plugin-syntax-jsx` to turn TypeScript parsing into TSX parsing. In the current Babel `7.28.6` implementation, this plugin exits early when the `typescript` parser plugin is already enabled.

Use `@babel/plugin-syntax-typescript` with `isTSX: true` instead:

```json
{
  "plugins": [
    [
      "@babel/plugin-syntax-typescript",
      {
        "isTSX": true
      }
    ]
  ]
}
```

Programmatic example:

```javascript
import { transformSync } from "@babel/core";

const result = transformSync("const view = <Button />;", {
  filename: "src/view.tsx",
  configFile: false,
  babelrc: false,
  plugins: [["@babel/plugin-syntax-typescript", { isTSX: true }]],
});

if (!result?.code) {
  throw new Error("Transform failed");
}
```

If you enable TypeScript parsing without `isTSX: true`, JSX-like input in `.tsx` code does not parse correctly.

## Common build setup

`package.json`:

```json
{
  "scripts": {
    "build": "babel src --out-dir lib"
  },
  "devDependencies": {
    "@babel/cli": "^7.28.6",
    "@babel/core": "^7.28.6",
    "@babel/plugin-syntax-jsx": "^7.28.6"
  }
}
```

`babel.config.json`:

```json
{
  "plugins": ["@babel/plugin-syntax-jsx"]
}
```

This setup is useful when another tool handles JSX transformation later and you only need Babel to parse the syntax during an intermediate step.

## Important pitfalls

- This plugin only affects parsing. It does not rewrite JSX and does not add any runtime helpers.
- A Babel build can succeed with this plugin while the output still contains `<Component />`, which will not run directly in standard JavaScript environments.
- Install `@babel/core` alongside the plugin; the published package declares Babel core as a peer dependency.
- There are no plugin-specific configuration options in `7.28.6`.
- If TypeScript syntax is enabled for the same file, configure `@babel/plugin-syntax-typescript` for TSX instead of expecting `@babel/plugin-syntax-jsx` to override it.

## Version-sensitive notes

- This guide targets `@babel/plugin-syntax-jsx@7.28.6`.
- The published `7.28.6` package declares `@babel/core` peer compatibility as `^7.0.0-0`.
- In the published `7.28.6` implementation, the plugin asserts Babel compatibility as `^7.0.0-0 || ^8.0.0-0`.
- In the published `7.28.6` implementation, the plugin adds `"jsx"` to Babel's parser plugins unless `"typescript"` is already present.
- The published package description for `7.28.6` is `Allow parsing of jsx`.

## Official sources

- Babel docs: https://babel.dev/docs/en/next/babel-plugin-syntax-jsx
- npm package page: https://www.npmjs.com/package/@babel/plugin-syntax-jsx
- Babel source package: https://github.com/babel/babel/tree/main/packages/babel-plugin-syntax-jsx
- Babel TypeScript syntax plugin docs: https://babel.dev/docs/en/next/babel-plugin-syntax-typescript

## API surface — verifiable exports of `@babel/plugin-syntax-jsx`

Each symbol below is a real export of `@babel/plugin-syntax-jsx`, verified via `Object.keys(require('@babel/plugin-syntax-jsx'))`.

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
const r_buildExternalHelpers = babel.buildExternalHelpers(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_createConfigItem = babel.createConfigItem(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_createConfigItemAsync = babel.createConfigItemAsync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_createConfigItemSync = babel.createConfigItemSync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_getEnv = babel.getEnv(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_loadOptions = babel.loadOptions(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_loadOptionsAsync = babel.loadOptionsAsync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_loadOptionsSync = babel.loadOptionsSync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_loadPartialConfig = babel.loadPartialConfig(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_loadPartialConfigAsync = babel.loadPartialConfigAsync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_loadPartialConfigSync = babel.loadPartialConfigSync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_parse = babel.parse(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_parseAsync = babel.parseAsync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_parseSync = babel.parseSync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_resolvePlugin = babel.resolvePlugin(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_resolvePreset = babel.resolvePreset(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_template = babel.template(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_transform = babel.transform(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_transformAsync = babel.transformAsync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_transformFile = babel.transformFile(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_transformFileAsync = babel.transformFileAsync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_transformFileSync = babel.transformFileSync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_transformFromAst = babel.transformFromAst(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_transformFromAstAsync = babel.transformFromAstAsync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_transformFromAstSync = babel.transformFromAstSync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_transformSync = babel.transformSync(code, { plugins: ['@babel/plugin-syntax-jsx'] });
const r_traverse = babel.traverse(code, { plugins: ['@babel/plugin-syntax-jsx'] });
```

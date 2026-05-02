---
name: webpack-merge
description: "Utility for composing webpack configuration objects with deep merges, rule-aware overrides, and custom array merge strategies"
metadata:
  languages: "javascript"
  versions: "6.0.1"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "webpack,webpack-merge,build,bundler,javascript,path,HotModuleReplacementPlugin,resolve,build-tool,Configuration,Compiler,Compilation,Stats,Module,Chunk,ChunkGroup,Asset,watch,run,close"
---

# webpack-merge for JavaScript

`webpack-merge` helps you split webpack config into small files and combine them into one final config object. Use it for the common pattern of a shared base config plus development- or production-specific overrides.

There is no authentication, client setup, or required environment variable. Import the merge helper and use it inside your webpack config files.

## Install

Install `webpack-merge` in the same project as webpack:

```bash
npm install --save-dev webpack-merge
```

Common import patterns:

```js
const { merge, mergeWithRules } = require("webpack-merge");

// or
import { merge, mergeWithRules } from "webpack-merge";
```

## Split a base config from environment-specific configs

Keep the shared config in one file and merge in the pieces that change by environment.

`webpack.common.js`:

```js
const path = require("node:path");

module.exports = {
  entry: "./src/index.js",
  output: {
    path: path.resolve(__dirname, "dist"),
    filename: "[name].js",
    clean: true,
  },
  module: {
    rules: [
      {
        test: /\.css$/i,
        use: ["style-loader", "css-loader"],
      },
    ],
  },
};
```

`webpack.dev.js`:

```js
const { merge } = require("webpack-merge");
const common = require("./webpack.common.js");

module.exports = merge(common, {
  mode: "development",
  devtool: "inline-source-map",
});
```

`webpack.prod.js`:

```js
const { merge } = require("webpack-merge");
const common = require("./webpack.common.js");

module.exports = merge(common, {
  mode: "production",
  devtool: "source-map",
  output: {
    filename: "[name].[contenthash].js",
  },
});
```

Run the matching config with webpack-cli:

```bash
npx webpack --config webpack.dev.js
npx webpack --config webpack.prod.js
```

By default, `merge()` deep-merges objects and concatenates arrays. That default works well for many top-level webpack settings.

## Replace parts of matching loader rules with `mergeWithRules`

`module.rules` often needs more control than the default merge because loader arrays are normally appended. Use `mergeWithRules()` when you need to match a specific rule and replace only selected fields.

```js
const { mergeWithRules } = require("webpack-merge");

const mergeCssRules = mergeWithRules({
  module: {
    rules: {
      test: "match",
      use: {
        loader: "match",
        options: "replace",
      },
    },
  },
});

module.exports = mergeCssRules(
  {
    module: {
      rules: [
        {
          test: /\.css$/i,
          use: [
            { loader: "style-loader" },
            { loader: "css-loader", options: { modules: false } },
          ],
        },
      ],
    },
  },
  {
    module: {
      rules: [
        {
          test: /\.css$/i,
          use: [{ loader: "css-loader", options: { modules: true } }],
        },
      ],
    },
  },
);
```

This pattern keeps the existing CSS rule, matches the `css-loader` entry by `loader`, and replaces only its `options`.

## Prepend or replace selected arrays with `mergeWithCustomize`

When the default array concatenation is not what you want, use `mergeWithCustomize()` with the package helpers.

```js
const {
  mergeWithCustomize,
  customizeArray,
} = require("webpack-merge");

const mergeEntries = mergeWithCustomize({
  customizeArray: customizeArray({
    "entry.*": "prepend",
  }),
});

module.exports = mergeEntries(
  {
    entry: {
      app: ["./src/index.js"],
    },
  },
  {
    entry: {
      app: ["./src/polyfills.js"],
    },
  },
);
```

Use this kind of customization when a later config should prepend, append, or replace a specific array instead of taking the default behavior everywhere.

## Deduplicate plugin arrays

If both configs add the same plugin class, the default merge produces two plugin instances. Use the `unique()` helper when only one copy should remain.

```js
const webpack = require("webpack");
const {
  mergeWithCustomize,
  unique,
} = require("webpack-merge");

const mergePlugins = mergeWithCustomize({
  customizeArray: unique(
    "plugins",
    ["HotModuleReplacementPlugin"],
    (plugin) => plugin.constructor && plugin.constructor.name,
  ),
});

module.exports = mergePlugins(
  {
    plugins: [new webpack.HotModuleReplacementPlugin()],
  },
  {
    plugins: [new webpack.HotModuleReplacementPlugin()],
  },
);
```

## Practical notes

- `webpack-merge` only builds config objects. It does not run webpack by itself.
- No environment variables are required by the package. If your webpack config reads `process.env`, that is project-specific rather than a `webpack-merge` requirement.
- Arrays concatenate by default. This is the main reason duplicated loaders or plugins appear after a merge.
- Use `merge()` for broad config composition and `mergeWithRules()` for `module.rules` where matching and replacement matter.
- Keep shared settings such as `entry`, `output.path`, and common loader definitions in one base config so later overrides stay small.

## API surface — webpack runtime

`webpack-merge` is consumed by webpack's runtime as a plugin, loader, or config helper. The types below are webpack's stable plugin/loader API.

```typescript
// webpack public types
class Configuration {}
class Compiler {}
class Compilation {}
class Stats {}
class Module {}
class Chunk {}
class ChunkGroup {}
class Asset {}
class Dependency {}
class ResolverFactory {}
class WebpackPluginInstance {}
class RuleSetRule {}
class ModuleOptions {}
class OutputOptions {}
class EntryOptions {}
class ResolveOptions {}
class DevServerConfiguration {}
class PerformanceOptions {}
class OptimizationOptions {}
class ExternalsConfiguration {}
class ResolvePluginInstance {}
class LoaderContext {}
class LoaderDefinitionFunction {}
class WebpackError {}
class WebpackOptionsNormalized {}
```

```javascript
const compiler = webpack(config);
compiler.webpack(arg);
compiler.watch(arg);
compiler.run(arg);
compiler.close(arg);
compiler.getInfrastructureLogger(arg);
compiler.purgeInputFileSystem(arg);
compiler.hooks.run.tap('plugin', (compiler) => {});
compiler.hooks.compilation.tap('plugin', (compilation) => {});
compiler.hooks.emit.tapAsync('plugin', (compilation, callback) => {});
compilation.hooks.optimize.tap('plugin', () => {});
```

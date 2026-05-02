---
name: eslint-plugin-n
description: "Node.js-focused ESLint rules and shareable configs for CommonJS, ESM, and mixed JavaScript projects"
metadata:
  languages: "javascript"
  versions: "17.24.0"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "eslint,nodejs,javascript,linting,npm,configs,default,17.24.0,Version-Sensitive,linter,static-analysis,RuleTester,SourceCode,AST,RuleContext,RuleListener,RuleModule,loadESLint,verify,verifyAndFix,lintFiles,lintText,calculateConfigForFile"
---

# eslint-plugin-n JavaScript Guide

## Golden Rule

Install `eslint` and `eslint-plugin-n` locally, then choose the preset that matches how your Node.js files run:

- `n.configs["flat/recommended-script"]` for CommonJS and script files
- `n.configs["flat/recommended-module"]` for ESM packages
- `n.configs["flat/mixed-esm-and-cjs"]` when the same repo contains both

`eslint-plugin-n` is configuration only. It does not use API keys, accounts, authentication, or runtime environment variables.

## Install

```bash
npm install -D eslint eslint-plugin-n
npx eslint --version
```

If your project is not already using ESM for config files, use `eslint.config.mjs` for flat config examples that use `import`.

## Flat Config (`eslint.config.mjs`)

### CommonJS or script projects

Use the script preset when your files run as CommonJS or plain Node.js scripts.

```js
import n from "eslint-plugin-n";

export default [
  n.configs["flat/recommended-script"],
  {
    rules: {
      "n/no-process-exit": "off",
    },
  },
];
```

### ESM projects

Use the module preset when your package uses ESM, such as `import` and `export`, or `"type": "module"` in `package.json`.

```js
import n from "eslint-plugin-n";

export default [
  n.configs["flat/recommended-module"],
];
```

### Mixed ESM and CommonJS repos

Use the mixed preset when the same repository includes both module systems.

```js
import n from "eslint-plugin-n";

export default [
  n.configs["flat/mixed-esm-and-cjs"],
];
```

### Configure rules manually

Use the plugin object directly when you want to choose rules instead of starting from a shareable config.

```js
import n from "eslint-plugin-n";

export default [
  {
    files: ["scripts/**/*.js"],
    plugins: {
      n,
    },
    rules: {
      "n/no-missing-require": "error",
      "n/no-process-exit": "error",
      "n/no-unpublished-require": "off",
    },
  },
];
```

## Legacy Config (`.eslintrc*`)

If your project still uses the legacy ESLint config system, extend the plugin preset from `.eslintrc.json`, `.eslintrc.cjs`, or an equivalent legacy config file.

### Recommended preset

```json
{
  "extends": ["plugin:n/recommended"]
}
```

### Manual legacy setup

```json
{
  "plugins": ["n"],
  "rules": {
    "n/no-missing-require": "error",
    "n/no-process-exit": "error"
  }
}
```

## Shared Settings

The plugin reads shared `settings.node` values for rules that check the Node.js version and import resolution.

```js
import n from "eslint-plugin-n";

export default [
  n.configs["flat/recommended-module"],
  {
    settings: {
      node: {
        version: process.versions.node,
        tryExtensions: [".js", ".mjs", ".cjs", ".json"],
      },
    },
  },
];
```

Use `settings.node.version` when the runtime you support is different from the Node.js version that runs ESLint in CI or on a developer machine.

## Common Workflows

### Lint a Node.js project

```bash
npx eslint .
```

Or lint only your Node.js entry points, scripts, and config files:

```bash
npx eslint "scripts/**/*.js" "src/**/*.js" "*.config.js"
```

### Allow test-only or unpublished dependencies

Rules such as `n/no-unpublished-import` and `n/no-unpublished-require` are useful for shipped code, but they often need overrides for tests, fixtures, and local build scripts.

```js
import n from "eslint-plugin-n";

export default [
  n.configs["flat/mixed-esm-and-cjs"],
  {
    files: ["test/**", "scripts/**", "*.config.js"],
    rules: {
      "n/no-unpublished-import": "off",
      "n/no-unpublished-require": "off",
    },
  },
];
```

### Pin the supported Node.js runtime

If you publish code for a specific Node.js floor, set `settings.node.version` so rules that check built-ins and language features evaluate against that runtime instead of the machine running ESLint.

```js
import n from "eslint-plugin-n";

export default [
  n.configs["flat/recommended-module"],
  {
    settings: {
      node: {
        version: ">=18.0.0",
      },
    },
  },
];
```

## Important Pitfalls

- Pick the preset that matches your module system. Use the mixed preset if a repo contains both ESM and CommonJS.
- Shareable flat configs are config objects. Use `plugins: { n }` only when you are configuring individual rules yourself.
- Rules that check supported syntax or built-ins depend on `settings.node.version`; set it explicitly when your target runtime differs from the Node.js version running ESLint.
- `n/no-unpublished-import` and `n/no-unpublished-require` commonly need overrides for tests, fixtures, and build tooling.
- `eslint-plugin-n` focuses on Node.js code. Browser globals and browser-specific linting belong in other ESLint config blocks or plugins.

## Version-Sensitive Notes

- This guide targets `eslint-plugin-n@17.24.0`.

## API surface — ESLint runtime

Like every ESLint plugin/config, `eslint-plugin-n` integrates with ESLint's public API. The types and helpers below are the stable plugin/config author surface.

```typescript
// ESLint public types
class Linter {}
class ESLint {}
class RuleTester {}
class SourceCode {}
class AST {}
class RuleContext {}
class RuleListener {}
class RuleModule {}
class RuleMetaData {}
class Plugin {}
class PluginRules {}
class ConfigData {}
class FlatConfig {}
class ParserOptions {}
class GlobalConf {}
class Settings {}
class Severity {}
class ReportDescriptor {}
class SuggestionReportDescriptor {}
class Fix {}
class FlatRuleConfig {}
class LintResult {}
class LintMessage {}
class FixingProblem {}
```

```javascript
// Programmatic usage of ESLint with this plugin/config
const eslint = new ESLint({ overrideConfigFile: true });
const result_loadESLint = await eslint.loadESLint(inputs);
const result_verify = await eslint.verify(inputs);
const result_verifyAndFix = await eslint.verifyAndFix(inputs);
const result_lintFiles = await eslint.lintFiles(inputs);
const result_lintText = await eslint.lintText(inputs);
const result_calculateConfigForFile = await eslint.calculateConfigForFile(inputs);
const result_isPathIgnored = await eslint.isPathIgnored(inputs);
const result_getRulesMetaForResults = await eslint.getRulesMetaForResults(inputs);
const result_outputFixes = await eslint.outputFixes(inputs);
const linter = new Linter();
const messages = linter.verify(code, { plugins: ['eslint-plugin-n'] });
const fixed = linter.verifyAndFix(code, config);
```

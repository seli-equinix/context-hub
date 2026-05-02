---
name: eslint-plugin-simple-import-sort
description: "ESLint plugin for autofixing import and export ordering with configurable import groups."
metadata:
  languages: "javascript"
  versions: "12.1.1"
  revision: 1
  updated-on: "2026-03-13"
  source: maintainer
  tags: "eslint,imports,sorting,javascript,linting,npm,groups,default,12.1.1,linter,static-analysis,RuleTester,SourceCode,AST,RuleContext,RuleListener,RuleModule,loadESLint,verify,verifyAndFix,lintFiles,lintText,calculateConfigForFile"
---

# eslint-plugin-simple-import-sort

`eslint-plugin-simple-import-sort` adds ESLint autofix rules for sorting `import` and `export` statements. It has no runtime client, no authentication step, and no environment variables. You install it as a dev dependency, register it in ESLint, and run ESLint with `--fix` when you want files rewritten.

## Install

Install ESLint and the plugin as development dependencies:

```bash
npm install --save-dev eslint eslint-plugin-simple-import-sort
```

## Flat config (`eslint.config.js`)

Use this with modern ESLint setups:

```js
import simpleImportSort from "eslint-plugin-simple-import-sort";

export default [
  {
    files: ["**/*.{js,mjs,cjs,jsx}"],
    languageOptions: {
      ecmaVersion: "latest",
      sourceType: "module",
    },
    plugins: {
      "simple-import-sort": simpleImportSort,
    },
    rules: {
      "simple-import-sort/imports": "error",
      "simple-import-sort/exports": "error",
    },
  },
];
```

The `imports` rule sorts `import` declarations. The `exports` rule sorts `export` declarations.

## Legacy config (`.eslintrc.json`)

If your project still uses legacy ESLint config files, enable the same two rules there:

```json
{
  "plugins": ["simple-import-sort"],
  "rules": {
    "simple-import-sort/imports": "error",
    "simple-import-sort/exports": "error"
  }
}
```

## Common workflows

### Sort imports and exports with ESLint autofix

Run ESLint with `--fix` to apply the plugin's reordering:

```bash
npx eslint . --fix
```

Without `--fix`, ESLint reports ordering errors but does not rewrite the file.

### Add package scripts

```json
{
  "scripts": {
    "lint": "eslint .",
    "lint:fix": "eslint . --fix"
  }
}
```

### Customize import groups

The `imports` rule accepts a `groups` option. Each inner array is one group, and ESLint inserts a blank line between groups after autofix.

```js
import simpleImportSort from "eslint-plugin-simple-import-sort";

export default [
  {
    plugins: {
      "simple-import-sort": simpleImportSort,
    },
    rules: {
      "simple-import-sort/imports": [
        "error",
        {
          groups: [
            ["^\\u0000"],
            ["^node:"],
            ["^react$", "^@?\\w"],
            ["^@/"],
            ["^\\."],
          ],
        },
      ],
      "simple-import-sort/exports": "error",
    },
  },
];
```

In this example:

- `^\u0000` keeps side-effect imports together.
- `^node:` groups Node.js built-in modules imported with the `node:` prefix.
- `^react$` and `^@?\w` keep package imports together, with `react` first.
- `^@/` matches a common project alias.
- `^\.` keeps relative imports in their own group.

## Important pitfalls

- Do not enable other rules that reorder entire `import` declarations at the same time unless you have intentionally limited them to non-overlapping behavior. In particular, watch for conflicts with ESLint's core `sort-imports` rule or `import/order` from `eslint-plugin-import`.
- The plugin only sorts `import` and `export` syntax. It does not resolve modules, remove unused imports, or enforce dependency boundaries.
- When you provide a custom `groups` array, you replace the default grouping logic for the `imports` rule. Keep explicit patterns for side-effect imports and built-ins if you still want them separated.
- CommonJS `require()` calls are outside these two rules. If you need ordering checks for `require`, use other ESLint rules for that code path.

## Minimal commands

```bash
# install
npm install --save-dev eslint eslint-plugin-simple-import-sort

# report ordering issues
npx eslint .

# rewrite files with sorted imports/exports
npx eslint . --fix
```

## Version-sensitive notes

- This guide targets `eslint-plugin-simple-import-sort@12.1.1`.
- Use the flat-config example when your repo has `eslint.config.js`. Use the legacy example only for projects that still rely on `.eslintrc*` files.

## API surface — ESLint runtime

Like every ESLint plugin/config, `eslint-plugin-simple-import-sort` integrates with ESLint's public API. The types and helpers below are the stable plugin/config author surface.

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
const messages = linter.verify(code, { plugins: ['eslint-plugin-simple-import-sort'] });
const fixed = linter.verifyAndFix(code, config);
```

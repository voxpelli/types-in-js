![](https://repository-images.githubusercontent.com/319930104/97292a80-409e-11eb-80f1-577cf14431cb)

# Types in JavaScript

If you love types but not transpiling, then using TypeScript itself won't be your cup of tea, but there are other approaches you can take to get pretty close.

## Participate

### Join our [GitHub discussions](https://github.com/voxpelli/types-in-js/discussions)!

This repo exists mainly to promote a discussion around this topic – exchange experiences, share best practices and tips and ask for help on tricky parts. The discussions is found in the [GitHub discussions](https://github.com/voxpelli/types-in-js/discussions) of this repo

### Is there a readme badge?

Yes! If you use types in plain JS in your project, you can include thise badge in your readme to let people know that your code is typed without relying on TypeScript syntax.

[![Types in JS](https://img.shields.io/badge/types_in_js-yes-brightgreen)](https://github.com/voxpelli/types-in-js)

```md
[![Types in JS](https://img.shields.io/badge/types_in_js-yes-brightgreen)](https://github.com/voxpelli/types-in-js)
```

## How to use types in JavaScript

[TypeScript supports JavaScript](https://www.typescriptlang.org/docs/handbook/intro-to-js-ts.html) and it supports quite a few [JSDoc annotations](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html) to help you type your JS code (some, like `@deprecated`, is even used in TS-code).

Since TypeScript is what drives the JavaScript tools in Visual Studio Code and [its intellisense](https://code.visualstudio.com/docs/nodejs/working-with-javascript#_intellisense) the implementation is actually used more than one would initially guess.

### Getting started

1. Add a [`tsconfig.json`](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) with eg. [`allowJs: true`](https://www.typescriptlang.org/tsconfig#allowJs) or add a [`jsconfig.json`](https://code.visualstudio.com/docs/languages/jsconfig) instead, which implies `allowJs: true` (Update 2024-02-29: It appears like `jsconfig.json` now implies [much more](https://github.com/eslint/eslint/issues/18100#issuecomment-1971500684)).

2. Then point it to your javascript files by using [`files`](https://www.typescriptlang.org/tsconfig#files) and/or [`include`](https://www.typescriptlang.org/tsconfig#include) properties.

3. Lastly either set [`checkJs: true`](https://www.typescriptlang.org/tsconfig#checkJs) in it, to have all of those files checked, or selectively add `// @ts-check` to the top of the files you want to check.

4. (optional) Add some other useful / needed configurations, see [TSConfig / JSConfig tips](#tsconfig--jsconfig-tips).

4. (optional) Install [`typescript`](https://www.npmjs.com/package/typescript) locally in your project (`npm install typescript`), then validate your project using `npx tsc` ([`tsc`](https://www.typescriptlang.org/docs/handbook/compiler-options.html) is the name of the CLI supplied by `typescript`). `tsc` can preferably be run as a part of your test scripts, locally and on CI. See [CI / linting tips](#ci--linting--additional-tools)

## Articles around using types with JavaScript

* [TypeScript without TypeScript -- JSDoc superpowers](https://fettblog.eu/typescript-jsdoc-superpowers/) by [@ddprrt](https://github.com/ddprrt)

## TSConfig / JSConfig tips

See [open discussion](https://github.com/voxpelli/types-in-js/discussions/2) as well as [base configs](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html#tsconfig-bases) to extend from.

## CI / linting / additional tools

See [open discussion](https://github.com/voxpelli/types-in-js/discussions/3)

## JSDoc syntax tips

There's a [cheatsheet available](https://devhints.io/jsdoc)

## Managing third party dependencies

See [open discussion](https://github.com/voxpelli/types-in-js/discussions/7)

## Other good resources

* [DavidWells/types-with-jsdocs](https://github.com/DavidWells/types-with-jsdocs)
* [TypeScript JSDoc Reference](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html)

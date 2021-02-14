![](https://repository-images.githubusercontent.com/319930104/97292a80-409e-11eb-80f1-577cf14431cb)

# Types in JavaScript

If you love types but not transpiling, then using TypeScript itself won't be your cup of tea, but there are other approaches you can take to get pretty close.

## How

Something that might have passed you by: [TypeScript supports JavaScript](https://www.typescriptlang.org/docs/handbook/intro-to-js-ts.html) and it support a couple of [JSDoc annonations](https://www.typescriptlang.org/docs/handbook/jsdoc-supported-types.html) that helps you annotate your JavaScript in such a way that it can properly validate it for you.

In fact, TypeScript is what drives the JavaScript tools in Visual Studio Code and what is responsible for [its intellisense](https://code.visualstudio.com/docs/nodejs/working-with-javascript#_intellisense).

### Some quick steps

1. Add a [`tsconfig.json`](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html) with eg. [`allowJs: true`](https://www.typescriptlang.org/tsconfig#allowJs) or add a [`jsconfig.json`](https://code.visualstudio.com/docs/languages/jsconfig) instead, which implies `allowJs: true`.

2. Then point it to your javascript files by using [`files`](https://www.typescriptlang.org/tsconfig#files) and/or [`include`](https://www.typescriptlang.org/tsconfig#include) properties.

3. Lastly either set [`checkJs: true`](https://www.typescriptlang.org/tsconfig#checkJs) in it, to have all of those files checked, or selectively add `// @ts-check` to the top of the files you want to check.

4. (optional) Add some other useful / needed configurations, see [TSConfig / JSConfig tips](#tsconfig--jsconfig-tips).

4. (optional) Install [`typescript`](https://www.npmjs.com/package/typescript) locally in your project (`npm install typescript`), then validate your project using `npx tsc` ([`tsc`](https://www.typescriptlang.org/docs/handbook/compiler-options.html) is the name of the CLI supplied by `typescript`). `tsc` can preferably be run as a part of your test scripts, locally and on CI. See [CI / linting tips](#ci--linting--additional-tools)

## Discussions, questions and best practices

Can be found in the [GitHub discussions](https://github.com/voxpelli/types-in-js/discussions) of this repo

## TSConfig / JSConfig tips

See [open discussion](https://github.com/voxpelli/types-in-js/discussions/2) as well as [base configs](https://www.typescriptlang.org/docs/handbook/tsconfig-json.html#tsconfig-bases) to extend from.

## CI / linting / additional tools

See [open discussion](https://github.com/voxpelli/types-in-js/discussions/3)

## JSDoc syntax tips

There's a [cheatsheet available](https://devhints.io/jsdoc)

...

## Managing third party dependencies

See [open discussion](https://github.com/voxpelli/types-in-js/discussions/7)

## 🚧 Under construction

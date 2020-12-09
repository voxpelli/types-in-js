# Types in JavaScript

If you love types but not transpiling, then using TypeScript itself won't be your cup of tea, but there are other approaches you can take to get pretty close.

## JSDoc validated and parsed by TypeScript

Something that might have passed you by: TypeScript supports JavaScript. (In fact, TypeScript is what drives the JavaScript tools like Intellisense in VS Code)

Set `allowJs: true` and optionally `checkJs: true` in your `tsconfig.json` (or add a [`jsconfig`](https://code.visualstudio.com/docs/languages/jsconfig)) and you're up and running.

# FAQ

Some common questions about JSDoc features in TypeScript.

## Can I use an `@typedef` from another file ?

It's possible to share definitions between multiple files, for example you might have

```js
// file-saver.js
/**
 * @typedef {{
 *    fileName: string,
 *    contents: object
 * }} SaveOptions
 */
```

As long as this is defined as a top level comment in the file ( Not part of a class/method )
then it can be imported in other files

```js
// app.js
/** @typedef {import('./file-saver.js').SaveOptions} SaveOptions */
```

If you want to share a definition, you can import it and give it a local name, you can also
use it directly in a method if that's preferred.

```js
// app.js

class App {
  /**
   * @param {import('./file-saver.js').SaveOptions} options
   */
  saveFile (options) {

  }
}
```

## I want to share some helper interfaces or aliases globally in my JSDoc project.

Turns out that you can share interfaces / type aliases globally in a project without copy pasting
or adding lots of `@typedef {import(...)} ...` statements.

The most important thing to do is to `declare`. 

```ts
// typedefs.d.ts
declare type Result<T> = {
  err: Error,
  data?: undefined
} | {
  err?: undefined,
  data: T
}
```

Then in any javscript file you can use `Result<null>` or `Result<string[]>` etc.

Do make sure that this file is included in your `jsconfig.json`

```json
{
  "compilerOptions": { ... },
  "include": [
    "src/**/*.js",
    "src/**/*.d.ts"
  ]
}
```

I've set up my project to just include all `.d.ts`

### Can I use `import` with this `typedefs.d.ts`

Yes you can, however adding [`import` or `export` turns it into a module](https://stackoverflow.com/a/57040462/419970) and its no longer global.

You will have to write `declare global { ... }` to be able to declare global interfaces/type aliases from a module.

```
// typedefs.d.ts
import * as events from 'events'

declare global {
  type Result<T> = {
    err: Error,
    data?: undefined
  } | {
    err?: undefined,
    data: T
  }
}
```

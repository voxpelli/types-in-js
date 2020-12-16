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

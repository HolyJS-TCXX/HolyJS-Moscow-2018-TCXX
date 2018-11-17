# ECMAScript proposal: Add 🐈(cat) prefix to functions
- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Functions or methods, marked with 🐈 do not throw exceptions. In in case of error - 🐈 will be throw.
```js
function 🐈myFunction() {
}
```
## High-level API

```js
function 🐈myFunction() {
  throw new Error('bad request');
}
try {
  myFunction();
} catch (err) {
  console.error(err); // 🐈
}

```
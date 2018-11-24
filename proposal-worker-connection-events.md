# ECMAScript proposal: Add special event listeners to the workers
- [Motivation](#motivation)
- [High-level API](#high-level-api)

## Motivation

As you might already knew, workers cannot acces DOM, but there're a one interesting and useful thing - an event listeners.
Of course, most of them are tightly connected with DOM, `onclick`, for example, but there are a few events that are not related to the DOM -
`online` or `offline`:

## High-level API

```js
// example.js
new Worker('script.js');

// script.js
self.addEventListener('offline', function (e) {
  // Do something, when client gone offline
});

self.addEventListener('online', function (e) {
  // Do something, when client got back online
});
```

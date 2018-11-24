# ECMAScript proposal: Add special event listeners to the workers related to the internet connection
- [Motivation](#motivation)
- [High-level API](#high-level-api)

## Motivation

We all love event listeners, but there are no way to use them inside of a worker.
Of course, most of event listeners are tightly connected with DOM, `onclick`, for example, but there are a few events that are not related to the DOM -
`online` or `offline`. It would be better to add them to be able to be used inside of the worker, because at most we are using workers to deal with requests and calculations. 

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

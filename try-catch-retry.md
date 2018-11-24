# ECMAScript proposal: Retry statement for Try block
- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

I am working at backend team and use nodejs, and I think will be awesome to add `retry` 

Why this should be done on language and not userland?

1. Standart solution and approach
2. Optimizations by CFG

## High-level API

Variant A (automaticaly try catch, any exception):

```js
try {
   await anotherServiceApi.logAudit();
} retry (e, amount) {
   console.log(`Trying to attemnt ${amount}, after error: ${e.message}`);
}
```

Variant B (manually with fire as callback, any exception):

```js
try {
   await anotherServiceApi.logAudit();
} retry (e, amount, fire) {
   console.log(`Trying to attemnt ${amount}, after error: ${e.message}`);

   fire();
}
```


With my propolsal at HolyJS Piter 2018 (automaticaly try catch, specified exception):

```js
try {
   await anotherServiceApi.logAudit();
} retry (e: InternalComunicationError, amount) {
   console.log(`Trying to attemnt ${amount}, after error: ${e.message}`);
}
```

Another idea with instanceof (automaticaly try catch, specified exception):

```js
try {
   await anotherServiceApi.logAudit();
} retry (e instaceof InternalComunicationError, amount) {
   console.log(`Trying to attemnt ${amount}, after error: ${e.message}`);
}
```

### FAQ
#### Question

Answer

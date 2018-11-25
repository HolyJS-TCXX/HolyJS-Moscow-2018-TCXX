# ECMAScript proposal: Stack context
- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

JS is foundation for microservice architecture (even in frontend, as HolyJS talks declare). 
Microservices require transactional approach, which require some request-level context;
In order to make js friendly to database transactions, 2- and 3-phase commits and other microservice technologies, 
context pass through all the APIs should be simplified. We cannot rely on globals for it, as long as node.js can handle multiple requests in a same time, so we need some specific async stack point-level variables.

## High-level API

```js
const context = createContext()
const test = () => assert.equal(obj, context.consumer())
context.provider(obj), () => {
    setTimeout(() =>
    test()) 
}) 


```

### FAQ
#### Why it copy react api? 
it is simple and familiar to a lot of developers, and do same functionality for React stack

# ECMAScript proposal: Class Spread Operator
- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

In JavaScript we could extend class only by another one, but sometimes we need to merge functionality from multiple classes with any colission rule.
```js
class A {}

class B extends A {}
```
With `Class Spread Operator` we could extend class from multiple classes and objects.
```js
import lodash from 'lodash'

class LabmdaLodash {
 // Some functions
}

export default class BetterLodash {
  ...lodash;
  ...LabmdaLodash;
}

```

## High-level API

Merge classes
```js
class A {}
class B {}
class C {
  ...A;
  ...B;
}
```

Merge objects
```js
const apiService = new API();

class ComponentWithApiMethods {
  ...apiService
}
```

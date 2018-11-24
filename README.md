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
So it solve problem when you have a same part of few classes, but you don't make relations between them.
```js
const methodsMixin = {
  firstFn() {},
  secondFn() {}
}

class A {
  ...methodsMixin;
  thirdFn() {}
}

class B {
  ...methodsMixin;
  forthFn() {}
}
```

## High-level API

Merge classes
```js
class A {
  a = 2;
}
class B {
  a = 3;
  b() {}
}
class C {
  ...A;
  ...B;
}
// C { a = 3; b() {} }
```

Merge objects
```js
const apiService = {
  fetchUser() {},
  fetchMessages() {},
};

class ComponentWithApiMethods {
  ...apiService;
  async componentDidMount() {
    this.users = await this.fetchUser();
  }
}
```

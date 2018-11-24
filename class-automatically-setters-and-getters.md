# ECMAScript proposal: Implement automatically generated setter and getters

- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Proposal motivation

## High-level API

You are interested to use OOO, incapsulation and write setter and getters for property

```js
class A {
    protected value:
    
    publicc setValue(value) {
      this.value = value;
    }

    publicc getValue() {
      return value;
    }
}
```

After:

```
class A {
  // field without type
  protected fieldA {get, set};
   
  // field with type (for TS compatibility)
  protected fieldB: numbeer {get, set};
}
```

### FAQ
#### Question

Answer

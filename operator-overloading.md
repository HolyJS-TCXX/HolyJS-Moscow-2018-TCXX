# ECMAScript proposal: Operator overloading
- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Proposal motivation

## High-level API

### How to define operator

Variant A: (`this` is allowed and `operator` is a method)

```js
class Account {
    protected amount;

    operator < (right) {
        return this.amount < right;
    }
}
```

Variant B: (static method)

```js
class Account {
    protected amount;

    operator < (left, right) {
        // this is not allowed, because it's static fn
        return leftt < right;
    }
}
```

### Examples

Example with console.log

```js
interface Console {
    operator << (...args) {
        this.log(...args);
    }
}

console << "Welcome to Holly";
```

Example with sort & reduce:

```js
class Account {
    protected amount;
    
    public __constructor(amount) {
        this.amount = amount;
    }

    operator > (right) {
        return this.amount > right;
    }

    operator < (right) {
        return this.amount < right;
    }
    
    operator + (right) {
        return this.amount + right;
    }
}

const accounts = [new Account(1111), new Account(222222)];

// asc
const sortedAccounts = accounts.sort((a, b) => a > b);

// desc
const sortedAccounts = accounts.sort((a, b) => a < b);

// calculate total summ of account's amounts
const totalAmount = accounts.reduce((a, b) => a + b);

// Btw this PR can be worked with my additional RFC at https://github.com/HolyJS-TCXX/HolyJS-Moscow-2018-TCXX/pull/8

// asc
const sortedAccounts = accounts.sort('>');

// desc
const sortedAccounts = accounts.sort('<');

// calculate total summ of account's amounts
const totalAmount = accounts.reduce('+');
```

### Another languages

### FAQ
#### Question

Answer

# ECMAScript proposal: BigDecinimal/BigNumber: Arbitrary precision numbers

- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Currently `number` type support `1.7976931348623157 × 10^308`, it's 99.9% enought for any applications but sometimes....

Motivation:

Make language more seriously

There are a lot of libraries that implement this:

- https://github.com/justmoon/node-bignum
- https://github.com/MikeMcl/big.js/
- https://github.com/royNiladri/js-big-decimal

But we can do more:

- Complex
- Performance
- Ovveride operator for `BigDecinimal` object
- Ovveride standart `Math` functions to work with it

## High-level API

### How Does It Work?

A `BigDecinimal` is created by appending `d` to the end of the number or by calling the constructor.

```js

const theBiggestDecinimal = 900719925474099100000000000000d;

const theBiggestDecinimalSecondWay = BigDecinimal(9007199254740991);
// ↪ 9007199254740991n

const theBiggestDecinimalThirdWayFromString = BigDecinimal('9007199254740991');
// ↪ 9007199254740991n
```

### Operators

You can use `+`, `*`, `-`, `**` and `%` with `BigInt`s, just like with `Number`s.

```
const result = 900719925474099100000000000000d + 110000000000000000d;
const result = 900719925474099100000000000000d * 110000000000000000d;
const result = 900719925474099100000000000000d - 110000000000000000d;
const result = 900719925474099100000000000000d ** 2;
```

### FAQ
#### Question

Answer

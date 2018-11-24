# ECMAScript proposal: Support more Math functions

- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

JS is a serius language))) WE NEED IT!!!111

A lot of functions can be find in http://www.cplusplus.com/reference/cmath/

## High-level API

```
// Generate value from significand and exponent (function) - http://www.cplusplus.com/reference/cmath/ldexp/
ldexp(value: number, exp: number): number;

// Get significand and exponent - http://www.cplusplus.com/reference/cmath/frexp/
frexp(value: number, exp: number): number;

// Break into fractional and integral parts - http://www.cplusplus.com/reference/cmath/modf/
modf(value: number): {fracrtional: number; integral: number};
```

### FAQ
#### Question

Answer

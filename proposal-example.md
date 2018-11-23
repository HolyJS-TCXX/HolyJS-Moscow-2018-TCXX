# ECMAScript proposal: Determine type of variable
- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Need a simple and reliable way to determine the type of variable, that returns the expected result.

## High-level API

```js
Object.typeOf = (a) => {
    const type = toString.call(a).slice(8, -1);
    if (type === 'Number') {
        if (isNaN(a)) return 'NaN';
        if (!isFinite(a)) return 'Infinity';
        if (a % 1 !== 0) return 'Float';
    }
    return type;
};

const inputs = [
    () => {}, // => 'Function' 
    {}, // => 'Object'
    [], // => 'Array'
    false, // => 'Boolean'
    NaN, // => 'NaN'
    new Date(), // => 'Date'
    '', // => 'String'
    0, // => 'Number'
    3.14, // => 'Float'
    null, // => 'Null'
    undefined, // => 'Undefined'
    Infinity, // => 'Infinity'
    new WeakMap([]), // => 'WeakMap'
    new Boolean(true), // => 'Boolean'
    new Number(1), // => 'Number'
    /regexp/, // => 'RegExp'
    class MyClass {}, // => 'Function'
];

```

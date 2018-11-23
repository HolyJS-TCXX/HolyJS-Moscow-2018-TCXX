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

Object.typeOf(() => {}); // => 'Function' 
Object.typeOf({}); // => 'Object'
Object.typeOf([]); // => 'Array'
Object.typeOf(false); // => 'Boolean'
Object.typeOf(NaN); // => 'NaN'
Object.typeOf(new Date()); // => 'Date'
Object.typeOf(''); // => 'String'
Object.typeOf(0); // => 'Number'
Object.typeOf(3.14); // => 'Float'
Object.typeOf(null); // => 'Null'
Object.typeOf(undefined); // => 'Undefined'
Object.typeOf(Infinity); // => 'Infinity'
Object.typeOf(new WeakMap([])); // => 'WeakMap'
Object.typeOf(new Boolean(true)); // => 'Boolean'
Object.typeOf(new Number(1)); // => 'Number'
Object.typeOf(/regexp/); // => 'RegExp'
Object.typeOf(class MyClass {}); // => 'Function'


```

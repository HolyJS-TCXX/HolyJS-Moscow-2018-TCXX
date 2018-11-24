# ECMAScript proposal: Operator functions

- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Proposal motivation

I am not interested to write simple functions I am interested to write 3 chars.

## High-level API

Reduce usage:

```js
// total summ of array of number
const summ = [1,2,3,4,5].reduce('+', 0);

// multiple all number, I defined initialValue as 1 because 0 will not work
const summ = [1,2,3,4,5].reduce('*', 1);
```

Sort:

```js
const asc = [1,2,3,4,5].sort('<');

const desc = [1,2,3,4,5].sort('>');

// On HolyJS i submited an RFC for SPACE SHIP OPERATORS
const sorted = [1,2,3,4,5].sort('<=>');
```

Operators list:

- `+`
- `-`
- `/`
- `*`
- `**`
- `%`

and etc, around 10-15

### FAQ
#### Question

Answer

# ECMAScript proposal: @Name
- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Sometimes you want to rerun to prev step in a loop

## High-level API

```js
let res = false;
for (let i = 0; i < 5; i++) {
    // some code
    console.log(i);
    if (i === 3 && !res) {
        res = true;
        back;
    }
}
```

The code will log:
```
0 
1
2
3
2
3
4
```
### FAQ
#### Question

Answer

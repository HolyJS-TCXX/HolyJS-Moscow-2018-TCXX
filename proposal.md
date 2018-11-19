# ECMAScript proposal: Add unique function to Array class
- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Currently, there is no easy way to remove duplicates from Arrays and Collections. This function adds this ability.

## High-level API

```js
Array.prototype.uniq=function(attr){
	return this.filter((item, pos, arr)=>item && (typeof item === "object" && attr ? arr.indexOf(arr.find(elem=>item[attr]===elem[attr])) === pos : arr.indexOf(item) === pos));
}

[{aa:33, bb:111222}, {aa:34, bb:111222}, {aa:33, bb:111222}].uniq('aa');

// [{aa:33, bb:111222}, {aa:34, bb:111222}]

[{aa:33, bb:111222}, {aa:34, bb:111222}, {aa:33, bb:111222}].uniq('bb');

// [{aa:33, bb:111222}]

[{aa:33, bb:111222}, {aa:34, bb:111222}, {aa:33, bb:111222}].uniq();

// [{aa:33, bb:111222}, {aa:34, bb:111222}, {aa:33, bb:111222}]

[11, 22, 33, 11].uniq()

// [11, 22, 33]

```
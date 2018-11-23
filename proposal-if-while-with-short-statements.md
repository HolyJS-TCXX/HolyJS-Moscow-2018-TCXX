# ECMAScript proposal: Add if and while statements with a short statement to execute before the condition
- [Motivation](#motivation)
- [Syntax](#syntax)
- [High-level API](#high-level-api)
- [Prior Art](#prior-art)
- [FAQ](#faq)

## Motivation

Like for, `if` and `while` statements can start with a short statement to execute before the condition.
Using the `if` and `while` statements with declaration doesn't pollute the upper scope with unnecessary variables and makes the code cleaner.

## Syntax

### `if` statement

```js
if ([Statement;] Expression) Statement
if ([Statement;] Expression) Statement else Statement
```

### `while` statements

```js
while ([Statement;] Expression) Statement
do Statement while ([Statement;] Expression)
```

## High-level API

### Before

```js
const foo = bar();

if (foo != 'fizzbuzz') {
	return foo;
} else {
	console.log(foo);
}

const foo2 = getSomething(); // can't use foo here
```

```js
let num;
let isPositive = false;

while (!isPositive) {
	num = foo.bar(1337);
	isPositive = num >= 0;
}

foo.fizzBuzz(num);

const isPositive2 = foo.bar(1) >= 0; // can't use isPositive here
```

### After

```js
if (const foo = bar(); foo != 'fizzbuzz') {
	return foo;
} else {
	console.log(foo);
}

const foo = getSomething(); // can use foo here
```

```js
let num;

while (let isPositive = false; !isPositive) {
	num = foo.bar(1337);
	isPositive = num >= 0;
}

foo.fizzBuzz(num);

const isPositive = foo.bar(1) >= 0; // can use isPositive here
```

## Prior Art

+ [C++](https://en.cppreference.com/w/cpp/language/if)
+ [Go](https://tour.golang.org/flowcontrol/6)

## FAQ

#### What's the advantage of "`if` and `while` with a short statement"?
It's shorter, that's about it. Also, since `if` and `while` accept an initialization statement, it's common to see one used to set up a local variable.

#### OK, but are there any pitfalls?
As you can imagine, this can lead to shadowing: 
```js
function doSomething() {
	const x = 1;
	
	if (const x = bar(); x != 1337) {
		// x from if's short statement shadows x from outer scope
		console.log(x);
	}
}
```

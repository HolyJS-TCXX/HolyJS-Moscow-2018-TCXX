# ECMAScript proposal: Final modifier for Class or Method

- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Разместив перед объявлениями методов класса, можно предотвратить их переопределение в дочерних классах. 
Если же сам класс определяется с этим ключевым словом, то он не сможет быть унаследован.

Classes and methods that are declared with `final` are not allowed to be inherited or being overridden.

Proposal motivation

Даст пространство для оптимизаций и поможет разработчику более лучше разбираться в коде.

## High-level API

For class:

```js
final class A {
}

// JS engine will show that you are wrong, it's final class
class B extends A {
}
```

Disallow to add methods to prototype?

```
final class A {
}

// JS engine will say: Sorry Bro :(
A.prototype.unknownShitThatComesFromCode = () => null;;
```

For methods:

```js
class A {
    final method doWork() {}
}

class B extends A {
    // JS engine will show that you are wrong, it's final class
    method doWork() {}
}
```

### FAQ

#### Question

Answer

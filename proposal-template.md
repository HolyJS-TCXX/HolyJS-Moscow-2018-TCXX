# ECMAScript proposal: StaticObject to optimize

- [Motivation](#motivation)
- [High-level API](#high-level-api)
- [FAQ](#faq)

## Motivation

Обьект в JS настолько динамичен по своей природе что заставляет разработчиков браузеров делать всякие
hidden классесс и тд, но что если мы разрешим использовать динамический обьект так же по умолчаннию, но сделаем возможность
крутой оптимизации, но как?

```js
class UserService extends StaticObject {
     public a;
}
```

И когда кто-то попробует сделать:

```js
const service = new UserService();

// JS скажет нет / спс
service.awesmefield = 5;
```

Пока я тут веселюсь с написание компилируемого TS (https://github.com/ovr/StaticScript), я понимаю что если компилировать JS
можно было бы точно круто оптимизировать, что в EXE/ELF/MACH-O, что в webassembly

Мотивация:

- Оптимизация
- Запрещение расширение объекта

## High-level API

```js
// example code
```

### FAQ
#### Question

Answer

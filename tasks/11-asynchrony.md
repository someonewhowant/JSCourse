# Функция задержки (delay)
Language: javascript
Reward: 50

Напишите функцию `delay(ms)`, которая возвращает промис. Этот промис должен переходить в состояние "выполнено" (resolve) через `ms` миллисекунд.

Затем используйте эту функцию внутри асинхронной функции `sayHello()`, чтобы она:
1. Ждала 500 миллисекунд.
2. Возвращала строку `"Hello after delay!"`.

## Starter Code
```javascript
function delay(ms) {
    // ваш код (используйте setTimeout и Promise)
}

async function sayHello() {
    // ваш код
}
```

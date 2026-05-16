# Fetch API в JavaScript: Полное руководство

**Fetch API** — это современный интерфейс для выполнения сетевых запросов. Он пришел на смену старому `XMLHttpRequest` и основан на промисах, что делает работу с сетью гораздо проще и чище.

---

## 1. Базовый GET-запрос

Самый простой запрос — это получение данных.

```javascript
fetch('https://api.example.com/data')
  .then(response => {
    // response - это объект ответа
    return response.json(); // преобразуем ответ в JSON
  })
  .then(data => {
    console.log(data); // здесь мы получаем наши данные
  });
```

---

## 2. Обработка ошибок

**Важно:** `fetch` не выдает ошибку в `.catch()`, если сервер вернул ошибку 404 или 500. Промис отклонится только если запрос вообще не смог завершиться (например, пропал интернет).
Чтобы проверить, был ли запрос успешным, используйте свойство `response.ok`.

```javascript
fetch('https://api.example.com/data')
  .then(response => {
    if (!response.ok) {
      throw new Error('Произошла ошибка: ' + response.status);
    }
    return response.json();
  })
  .then(data => console.log(data))
  .catch(error => console.error('Ошибка:', error));
```

---

## 3. Fetch с Async / Await

Это самый популярный способ написания сетевых запросов в современном JavaScript.

```javascript
async function getData() {
  try {
    const response = await fetch('https://api.example.com/data');
    
    if (!response.ok) {
      throw new Error(`Ошибка статус: ${response.status}`);
    }
    
    const data = await response.json();
    console.log(data);
  } catch (error) {
    console.error('Ошибка при получении данных:', error);
  }
}
```

---

## 4. Отправка данных (POST-запрос)

Для отправки данных нужно передать второй аргумент — объект настроек.

```javascript
const user = { name: "Ivan", age: 25 };

fetch('https://api.example.com/users', {
  method: 'POST', // Метод запроса
  headers: {
    'Content-Type': 'application/json;charset=utf-8' // Сообщаем серверу, что шлем JSON
  },
  body: JSON.stringify(user) // Превращаем объект в строку
})
.then(response => response.json())
.then(result => console.log('Ответ сервера:', result));
```

---

## 5. Основные свойства объекта `Response`

- `response.status` — HTTP-код ответа (200, 404, 500 и т.д.).
- `response.ok` — `true`, если статус от 200 до 299.
- `response.headers` — объект с заголовками ответа.
- `response.json()` — метод для чтения тела ответа как JSON.
- `response.text()` — метод для чтения тела ответа как обычный текст.

---

## Лучшие практики

1. **Всегда проверяйте `response.ok`**. Это единственный способ узнать, что сервер действительно вернул данные, а не ошибку.
2. **Используйте `async/await`**. Код становится плоским и его легче читать и отлаживать.
3. **Не забывайте про заголовки**. При отправке JSON заголовок `Content-Type` обязателен для большинства серверов.
4. **Используйте глобальный `try...catch`**. Сетевые ошибки могут возникнуть в любой момент (пропал Wi-Fi, упал сервер), и ваше приложение не должно от этого ломаться.

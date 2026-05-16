# Работа с DOM в JavaScript: Полное руководство

**DOM (Document Object Model)** — это объектная модель документа, которая представляет HTML-страницу в виде дерева объектов. С помощью JavaScript мы можем изменять структуру, стили и содержание страницы в реальном времени.

---

## 1. Дерево DOM

Каждый тег в HTML становится объектом (узлом) в дереве DOM.
- `document` — главная "входная точка" в DOM.
- `document.documentElement` — соответствует тегу `<html>`.
- `document.body` — соответствует тегу `<body>`.

---

## 2. Поиск элементов

Чтобы что-то изменить на странице, нужно сначала это найти.

### Современные методы (рекомендуются)
- **querySelector(cssSelector)** — возвращает **первый** найденный элемент по CSS-селектору.
- **querySelectorAll(cssSelector)** — возвращает **все** найденные элементы в виде коллекции (NodeList).

```javascript
const title = document.querySelector('.main-title');
const buttons = document.querySelectorAll('button');
```

### Старые методы (все еще встречаются)
- `getElementById(id)` — поиск по ID.
- `getElementsByClassName(className)` — поиск по классу.

---

## 3. Изменение содержимого и свойств

### Текст и HTML
- **textContent** — возвращает или меняет текстовое содержимое (безопасно).
- **innerHTML** — возвращает или меняет HTML-код внутри элемента (нужно быть осторожным с безопасностью).

```javascript
title.textContent = "Новый заголовок";
```

### Атрибуты
- `element.getAttribute(name)` — получить значение.
- `element.setAttribute(name, value)` — установить значение.
- `element.hasAttribute(name)` — проверить наличие.

---

## 4. Управление стилями и классами

### Стили
Свойства пишутся в формате camelCase.
```javascript
title.style.backgroundColor = "blue";
title.style.marginTop = "20px";
```

### Классы (classList) — лучший способ
- `classList.add("name")` — добавить класс.
- `classList.remove("name")` — удалить класс.
- `classList.toggle("name")` — переключить класс.
- `classList.contains("name")` — проверить наличие.

---

## 5. Создание и удаление элементов

```javascript
// 1. Создание
const newDiv = document.createElement('div');
newDiv.textContent = "Я новый блок!";

// 2. Добавление на страницу
document.body.append(newDiv); // в конец body
// Другие варианты: prepend (в начало), before, after.

// 3. Удаление
newDiv.remove();
```

---

## 6. Навигация по DOM

Если у вас уже есть элемент, вы можете найти его "родственников":
- `parentNode` — родитель.
- `children` — дочерние элементы.
- `nextElementSibling` / `previousElementSibling` — соседние элементы.

---

## Лучшие практики

1. **Минимизируйте обращения к DOM**. Каждое изменение заставляет браузер пересчитывать страницу. Лучше сначала собрать изменения в памяти, а потом применить их за один раз.
2. **Используйте `classList` вместо `style`**. Лучше менять состояние через классы, описанные в CSS, чем прописывать стили в JavaScript.
3. **Предпочитайте `querySelector`**. Это универсальный и мощный способ поиска.
4. **Помните про скрипты**. Если ваш `<script>` находится в `<head>`, он может не найти элементы, которые еще не загрузились. Используйте атрибут `defer` или событие `DOMContentLoaded`.

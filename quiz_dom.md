# Квиз: Работа с DOM в JavaScript

Проверьте свои знания о том, как управлять HTML-страницей с помощью JavaScript. Ответы в конце.

---

### Вопрос 1
Какой объект является главной входной точкой в DOM и представляет всю веб-страницу?

A) `window`  
B) `document`  
C) `html`  
D) `body`  

---

### Вопрос 2
Какой метод вернет **все** элементы на странице, которые имеют класс `active`?

A) `document.querySelector(".active")`  
B) `document.getElementById("active")`  
C) `document.querySelectorAll(".active")`  
D) `document.find(".active")`  

---

### Вопрос 3
Как правильно добавить CSS-класс `highlight` к элементу `myElem`, не затирая старые классы?

A) `myElem.class = "highlight"`  
B) `myElem.classList.add("highlight")`  
C) `myElem.setAttribute("class", "highlight")`  
D) `myElem.style.class = "highlight"`  

---

### Вопрос 4
В чем основное отличие `textContent` от `innerHTML`?

A) Разницы нет  
B) `textContent` работает только с заголовками  
C) `innerHTML` интерпретирует строку как HTML-код, а `textContent` — как обычный текст  
D) `textContent` работает быстрее, но только в браузере Chrome  

---

### Вопрос 5
Какой метод используется для удаления элемента из дерева DOM?

A) `delete()`  
B) `remove()`  
C) `clear()`  
D) `destroy()`  

---

## Ответы

<details>
<summary>Нажмите, чтобы увидеть ответы</summary>

1. **B) document** (Хотя `window` — это глобальный объект браузера, именно `document` отвечает за DOM).
2. **C) document.querySelectorAll(".active")** (Возвращает коллекцию всех совпадений).
3. **B) myElem.classList.add("highlight")** (Свойство `classList` — самый удобный способ работы с классами).
4. **C) innerHTML интерпретирует строку как HTML-код...** (Поэтому `innerHTML` менее безопасен, так как через него можно провести XSS-атаку).
5. **B) remove()** (Современный и простой метод для удаления узла).

</details>

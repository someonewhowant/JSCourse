# Квиз: Хранение данных в браузере

Проверьте свои знания о LocalStorage и SessionStorage. Ответы в конце.

---

### Вопрос 1
В чем основное отличие `localStorage` от `sessionStorage`?

A) `localStorage` работает быстрее  
B) `sessionStorage` удаляется при закрытии вкладки, а `localStorage` — нет  
C) `localStorage` может хранить объекты, а `sessionStorage` — нет  
D) `sessionStorage` доступен только в Node.js  

---

### Вопрос 2
Что вернет метод `getItem()`, если запрашиваемого ключа не существует в хранилище?

A) `undefined`  
B) `""` (пустая строка)  
C) `null`  
D) Вызовет ошибку  

---

### Вопрос 3
Как правильно сохранить объект `user = {id: 1}` в LocalStorage?

A) `localStorage.setItem("user", user)`  
B) `localStorage.save(user)`  
C) `localStorage.setItem("user", JSON.stringify(user))`  
D) `localStorage.user = user`  

---

### Вопрос 4
Какой объем данных (примерно) можно хранить в LocalStorage?

A) 1 ГБ  
B) 100 КБ  
C) 5-10 МБ  
D) Неограниченно  

---

### Вопрос 5
Как полностью удалить ВСЕ данные из LocalStorage?

A) `localStorage.delete()`  
B) `localStorage.removeItem("*")`  
C) `localStorage.clear()`  
D) `localStorage.reset()`  

---

## Ответы

<details>
<summary>Нажмите, чтобы увидеть ответы</summary>

1. **B) sessionStorage удаляется при закрытии вкладки, а localStorage — нет** (Это ключевое различие в жизненном цикле данных).
2. **C) null** (Поэтому всегда полезно проверять результат на существование).
3. **C) localStorage.setItem("user", JSON.stringify(user))** (Поскольку хранилище понимает только строки).
4. **C) 5-10 МБ** (Этого достаточно для настроек и простых данных, но мало для видео или тяжелых фото).
5. **C) localStorage.clear()** (Очищает всё хранилище для текущего домена).

</details>

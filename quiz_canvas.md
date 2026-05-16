# Квиз: Canvas API в JavaScript

Проверьте свои знания о рисовании на холсте. Ответы в конце.

---

### Вопрос 1
Какой метод используется для получения контекста рисования 2D-графики?

A) `canvas.getContext("2d")`  
B) `canvas.get2D()`  
C) `document.getCanvasContext()`  
D) `canvas.draw("2d")`  

---

### Вопрос 2
Чем `fillRect` отличается от `strokeRect`?

A) `fillRect` рисует только круг, а `strokeRect` — прямоугольник  
B) `fillRect` рисует закрашенную фигуру, а `strokeRect` — только контур  
C) `fillRect` работает быстрее  
D) Между ними нет разницы  

---

### Вопрос 3
Какой метод нужно вызвать ОБЯЗАТЕЛЬНО перед началом рисования новой сложной фигуры (линии, дуги)?

A) `ctx.stop()`  
B) `ctx.clear()`  
C) `ctx.beginPath()`  
D) `ctx.newPath()`  

---

### Вопрос 4
Почему рекомендуется использовать `requestAnimationFrame` для анимации вместо `setInterval`?

A) `requestAnimationFrame` работает только в 3D  
B) `requestAnimationFrame` синхронизируется с частотой обновления экрана и экономит ресурсы (не работает в фоновых вкладках)  
C) `setInterval` запрещен в современном JavaScript  
D) Разницы нет  

---

### Вопрос 5
Как изменить цвет заливки для последующих фигур?

A) `ctx.color = "red"`  
B) `ctx.paint = "red"`  
C) `ctx.fillStyle = "red"`  
D) `ctx.setBackground("red")`  

---

## Ответы

<details>
<summary>Нажмите, чтобы увидеть ответы</summary>

1. **A) canvas.getContext("2d")** (Это стандартный метод для начала работы).
2. **B) fillRect рисует закрашенную фигуру, а strokeRect — только контур.**
3. **C) ctx.beginPath()** (Иначе новые линии будут соединяться со старыми точками).
4. **B) requestAnimationFrame синхронизируется с частотой обновления экрана...** (Это делает анимацию плавной и эффективной).
5. **C) ctx.fillStyle = "red"** (Свойство `fillStyle` задает цвет для всех последующих операций заливки).

</details>

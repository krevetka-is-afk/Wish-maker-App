# Wish-maker-App

IOS App  

---  

## Answers for questions :  
### Question: What issues prevent us from using storyboards in real projects?
Основные проблемы при использовании сторибордов в реальных проектах:
1. **Конфликты при слиянии**: Storyboard — это XML, и его сложнее мержить в командной работе. В процессе столкнулся с некоорректным мерджем.. 2 часа убил на откаты.
2. **Проблемы с производительностью**: Сториборды загружаются сразу, это замедлит запуск приложения, особенно если сториборд большой.
3. **Масштабируемость**: Сториборды неудобны для поддержки больших проектов, поскольку вся логика смешивается в одном проекте.
4. **Отсутствие гибкости и кода**: Ограниченные возможности кастомизации и анимации.

---

### Question: What does the code on lines 25 and 29 do?
```swift
25. title.translatesAutoresizingMaskIntoConstraints = false
29. view.addSubview(title)
```
- **Line 25**: `title.translatesAutoresizingMaskIntoConstraints = false` указывает, что автоматически генерируемые ограничения для `title` не должны использоваться. Как я понял это нужно для установки кастомных значений верстки.
- **Line 29**: `view.addSubview(title)` добавляет элемент `title` (UILabel) в иерархию представлений, делает его видимым на экране.

---

### Question: What is a safe area layout guide?
Safe Area Layout Guide — это область экрана, которая должна быть всегда свободной от элементов интерфейса. safe area layout guide гарантирует, что контент не будет перекрыт системными элементами.

---

### Question: What is `[weak self]` and why is it important?
`[weak self]` используется в замыканиях closures для предотвращения сильной ссылки на `self`, чтобы избежать цикла удержания (retain cycle). Без него замыкание и `self` будут удерживать друг друга, что наверняка вызывет утечку памяти. По сути `[weak self]` гарантирует, что `self` освободится, когда больше не будет использоваться.

---

### Question: What does `clipsToBounds` mean?
Свойство `clipsToBounds` определяет, будут ли дочерние представления, выходящие за границы родительского представления, обрезаны. Если `clipsToBounds` установлено в `true`, части дочерних представлений, выходящие за границы, не будут отображаться.

---

### Question: What is the `valueChanged` type? What is `Void` and what is `Double`?
- **`valueChanged`** — это свойство, которое, имеет тип замыкания `((Double) -> Void)?`, представляющее собой функцию обратного вызова.

---
banner: "![[banner7.jpg]]"
banner_x:
cssClass: wide-page
cssclasses:
  - wide-page
---

# <center>Categories</center> 
---

> [!blank]
> -  ### Dead line #mcl/list-card
> 	- ![[Soren Miles Loyola.jpg]]
> 
> - ### Учеба
> 	- ![[Wyatt Nero Vergara.jpg]]
> 
----

# Personal Projects MOC

```dataviewjs
// Фильтрация проектов: выбираем только те, где есть тег #ProjectMain и тип = персональный
const projects = dv.pages()
    .where(p => p.tags && p.tags.includes("#ProjectMain") && p.type === "персональный");

// Группировка по статусу проекта
for (let group of projects.groupBy(p => p.status)) {
    dv.header(3, group.key); // Заголовок — статус группы

    // Таблица со списком проектов
    dv.table(
        ["📂 Проект", "🔥 Приоритет", "📌 Тип", "📅 Начало", "⏳ Дедлайн", "🏷 Теги"],
        group.rows.map(p => [
            p.file.link,                                     // Ссылка на файл проекта
            p.priority ?? "—",                              // Приоритет
            p.FBF ?? "—",                                   // Тип (FBF у тебя)
            p.start ?? "—",                                 // Дата начала
            p.deadline ?? "—",                              // Дедлайн
            (p.tags ?? []).filter(t => t !== "#ProjectMain").join(", ") // Остальные теги
        ])
    );
}
```

# Client Projects MOC

```dataviewjs
const projects = dv.pages().where(p => p.tags && p.tags.includes("#ProjectMain") && p.type === "заказной");

for (let group of projects.groupBy(p => p.status)) {
    dv.header(3, group.key);
    dv.table(["Проект", "Приоритет", "Тип", "Начало", "Дедлайн", "Теги"],
        group.rows.map(p => [
            p.file.link,
            p.priority,
            p.FBF,
            p.start,
            p.deadline,
            p.tags.filter(t => t !== "#ProjectMain").join(", ")
        ])
    );
}
```
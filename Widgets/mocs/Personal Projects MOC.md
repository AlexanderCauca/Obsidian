---
tags:
cssclasses:
  - minimal-float  wide-page
---

# Personal Projects MOC

```dataviewjs
const projects = dv.pages().where(p => p.tags && p.tags.includes("#ProjectMain") && p.type === "персональный");

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
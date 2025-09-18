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
> 	- [[0002 Project/Projects|Projects]] - 
> 	- [[0001 Programming/Programming|Programming]] — 
> 	- [[Journal MOC|Journal]] — 
> 
> - ### **Учеба**
> 	- ![[Wyatt Nero Vergara.jpg]]) 
> 	- [[Education]] - #education
> 	- [[Research]]  — #research
> 	- [[Papers MOC|Liturature]]  — #paper 
> 
> - ### **Развличение**
> 	- ![[Enrico Vance Magno.jpg]])
> 	- [[Movie Database]]  

----

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
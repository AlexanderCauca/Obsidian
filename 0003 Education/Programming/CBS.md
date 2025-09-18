---
tags:
cssclasses:
  - wide-page
banner: "![[gif(1).gif]]"
banner_y: 0.46445
excludeFromStats: true
---

# <center>CBS</center> 
# <center>Categories</center> 
> [!blank]
> - ### 🖥 С-sharp start #mcl/list-card
>   - ![C# logo](https://cdn.iconscout.com/icon/free/png-256/free-csharp-1175240.png)
>   - ![[CBS1]]
>   - - -
>   - [x] S 1 ✅ 2025-09-18
>   - [x] S 1 HomeWork ✅ 2025-09-18
>   - [x] S 2 ✅ 2025-09-18
>   - [x] S 2 HomeWork ✅ 2025-09-18
>   - [x] S 3 ✅ 2025-09-18
>   - [ ] S 3 HomeWork
>   - [ ] S 4
>   - [ ] S 4 HomeWork
>   - [ ] S 5
>   - [ ] S 5 HomeWork
>   - [ ] S 6
>   - [ ] S 6 HomeWork
>   - [ ] S 7
>   - [ ] S 7 HomeWork
>   - [ ] S 8
>   - [ ] S 8 HomeWork
>   - [ ] S 9
>   - [ ] S 9 HomeWork
> - ### 🎙️.NET base #mcl/list-card
>   - ![Microphone icon](https://img.icons8.com/ios/452/microphone.png)
>   - ![[CBS2]]
>   - --
>   - [x] B 1 ✅ 2025-09-18
>   - [ ] B 1 HomeWork
>   - [x] B 2 ✅ 2025-09-18
>   - [ ] B 2 HomeWork
>   - [x] B 3 ✅ 2025-09-18
>   - [ ] B 3 HomeWork
>   - [x] B 4 ✅ 2025-09-18
>   - [ ] B 4 HomeWork
>   - [ ] B 5
>   - [ ] B 5 HomeWork
>   - [ ] B 6
>   - [ ] B 6 HomeWork
>   - [ ] B 7
>   - [ ] B 7 HomeWork
>   - [ ] B 8
>   - [ ] B 8 HomeWork
>   - [ ] B 9
>   - [ ] B 9 HomeWork
>   - [ ] B 10
>   - [ ] B 10 HomeWork
>   - [ ] B 11
>   - [ ] B 11 HomeWork
>   - [ ] B 12
>   - [ ] B 12 HomeWork
>   - [ ] B 13
>   - [ ] B 13 HomeWork
>   - [ ] B 14
>   - [ ] B 14 HomeWork
>   - [ ] B 15
>   - [ ] B 15 HomeWork
>   - [ ] B 16
>   - [ ] B 16 HomeWork
>   - [ ] B 17
>   - [ ] B 17 HomeWork
>   - [ ] B 18
>   - [ ] B 18 HomeWork
> - ### 🤖  .NET  #mcl/list-card
>   - ![Robot icon](https://img.icons8.com/ios/452/artificial-intelligence.png)
>   - ![[CBS3]]
>   - --
>     - [ ] P 1
>     - [ ] P 1 HomeWork
>     - [ ] P 2
>     - [ ] P 2 HomeWork
>     - [ ] P 3
>     - [ ] P 3 HomeWork
>     - [ ] P 4
>     - [ ] P 4 HomeWork
>     - [ ] P 5
>     - [ ] P 5 HomeWork
>     - [ ] P 6
>     - [ ] P 6 HomeWork
>     - [ ] P 7
>     - [ ] P 7 HomeWork
>     - [ ] P 8
>     - [ ] P 8 HomeWork
>     - [ ] P 9
>     - [ ] P 9 HomeWork
>     - [ ] P 10
>     - [ ] P 10 HomeWork
>     - [ ] P 11
>     - [ ] P 11 HomeWork




> [!blank]
> - ### 💾  SQL #mcl/list-card
>   - ![Database icon](https://img.icons8.com/ios/452/database.png)
>   - ![[CBS4]]
>   - [ ] SQL 1
>   - [ ] SQL 1 HomeWork
>   - [ ] SQL 2
>   - [ ] SQL 2 HomeWork
>   - [ ] SQL 3
>   - [ ] SQL 3 HomeWork
>   - [ ] SQL 4
>   - [ ] SQL 4 HomeWork
>   - [ ] SQL 5
>   - [ ] SQL 5 HomeWork
>   - [ ] SQL 6
>   - [ ] SQL 6 HomeWork
>   - [ ] SQL 7
>   - [ ] SQL 7 HomeWork
>   - [ ] SQL 8
>   - [ ] SQL 8 HomeWork
>
> - ### 📱 EntityFramework
>   - ![Database icon](https://img.icons8.com/ios/452/database.png)
>   - ![[CBS5]]
>   - [ ] EF 1
>   - [ ] EF 1 HomeWork
>   - [ ] EF 2
>   - [ ] EF 2 HomeWork
>   - [ ] EF 3
>   - [ ] EF 3 HomeWork
>   - [ ] EF 4
>   - [ ] EF 4 HomeWork
>   - [ ] EF 5
>   - [ ] EF 5 HomeWork
> - ### 🚀 Дополнительные функции #mcl/list-card
>   - ![Features icon](https://img.icons8.com/ios/452/settings.png)
>   - ![[CBS6]]
>   - [ ] ASP 1
>   - [ ] ASP 1 HomeWork
>   - [ ] ASP 2
>   - [ ] ASP 2 HomeWork
>   - [ ] ASP 3
>   - [ ] ASP 3 HomeWork
>   - [ ] ASP 4
>   - [ ] ASP 4 HomeWork
>   - [ ] ASP 5
>   - [ ] ASP 5 HomeWork
>   - [ ] ASP 6
>   - [ ] ASP 6 HomeWork
>   - [ ] ASP 7
>   - [ ] ASP 7 HomeWork


```dataviewjs
// Берём все задачи из текущего файла
const tasks = dv.current().file.tasks;

// Считаем общее кол-во
let total = tasks.length;
let done = tasks.where(t => t.completed).length;

// Процент выполнения
let percent = total === 0 ? 0 : Math.round((done / total) * 100);

// Прогресс-бар
let bar = "█".repeat(percent/5) + "░".repeat(20 - percent/5);

dv.paragraph(`📊 Общий прогресс: ${done}/${total} (${percent}%)\n${bar}`);


```



```dataview
table 
    date as "Дата",
    importance as "Важность",
    type as "Тип"
from #notes
where date.weekyear = date(today).weekyear
  and date.week = date(today).week
sort date desc
```
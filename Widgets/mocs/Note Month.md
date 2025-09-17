```dataview
table 
    date as "Дата",
    importance as "Важность",
    type as "Тип"
from #notes
where date.year = date(today).year
  and date.month = date(today).month
sort date desc
```
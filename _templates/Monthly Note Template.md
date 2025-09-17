---
type: monthly
month: 2025-09
cssClass: wide-page, table-100
banner: "![[Mbanner.jpg]]"
banner_y: 0.33667
---

## Month: **{{date:gggg-MM}}**


> [!multi-column]
> 
>>[!info]+ Energy
>> ![[Energy M]]
>
>>[!info]+ Mood
>> ![[Mood M]]

> [!blank]
> - ### Programming #mcl/list-card
>   ```contributionGraph
>   title: 
>   graphType: calendar
>   dateRangeValue: 180
>   dateRangeType: FIXED_DATE_RANGE
>   startOfWeek: 0
>   showCellRuleIndicators: true
>   titleStyle:
>     textAlign: left
>     fontSize: 17px
>     fontWeight: normal
>   dataSource:
>     type: PAGE
>     value: "#programming"
>     dateField: {}
>   fillTheScreen: false
>   enableMainContainerShadow: false
>   fromDate: 2025-08-01
>   toDate: 2025-08-31
>   cellStyle:
>     minWidth: 17px
>     minHeight: 17px
>   cellStyleRules: []
>   ```
>
> - ### Courses #mcl/list-card
>   ```contributionGraph
>   title: 
>   graphType: calendar
>   dateRangeValue: 180
>   dateRangeType: FIXED_DATE_RANGE
>   startOfWeek: 0
>   showCellRuleIndicators: true
>   titleStyle:
>     textAlign: left
>     fontSize: 17px
>     fontWeight: normal
>   dataSource:
>     type: PAGE
>     value: "#courses"
>     dateField: {}
>   fillTheScreen: false
>   enableMainContainerShadow: false
>   fromDate: 2025-08-01
>   toDate: 2025-08-31
>   cellStyleRules:
>     - id: Ocean_a
>       color: "#8dd1e2"
>       min: 1
>       max: 2
>     - id: Ocean_b
>       color: "#63a1be"
>       min: 2
>       max: 3
>     - id: Ocean_c
>       color: "#376d93"
>       min: 3
>       max: 5
>     - id: Ocean_d
>       color: "#012f60"
>       min: 5
>       max: 9999
>   cellStyle:
>     minWidth: 17px
>     minHeight: 17px
>   ```
>
> - ### Book #mcl/list-card
>   ```contributionGraph
>   title: ""
>   graphType: calendar
>   dateRangeValue: 180
>   dateRangeType: FIXED_DATE_RANGE
>   startOfWeek: 0
>   showCellRuleIndicators: true
>   titleStyle:
>     textAlign: left
>     fontSize: 17px
>     fontWeight: normal
>   dataSource:
>     type: PAGE
>     value: "#book"
>     dateField: {}
>   fillTheScreen: false
>   enableMainContainerShadow: false
>   fromDate: 2025-08-01
>   toDate: 2025-08-31
>   cellStyle:
>     minWidth: 17px
>     minHeight: 17px
>   cellStyleRules:
>     - id: Halloween_a
>       color: "#fdd577"
>       min: 1
>       max: 2
>     - id: Halloween_b
>       color: "#faaa53"
>       min: 2
>       max: 3
>     - id: Halloween_c
>       color: "#f07c44"
>       min: 3
>       max: 5
>     - id: Halloween_d
>       color: "#d94e49"
>       min: 5
>       max: 9999
>   ```
---
### New Notes
```dataview
LIST bullet.text
FLATTEN file.lists as bullet
WHERE type = "daily" AND month = date({{date:gggg-MM}}) AND meta(bullet.section).subpath = "New Notes"
```

---
### Tasks
```dataview
TASK
WHERE type = "daily" AND month = date({{date:gggg-MM}})
```

---
### Tasks Progress

```dataviewjs
// get all tasks for the month
let dateFilter = dv.date("{{date:gggg-MM}}");
let tasks = dv.pages().where(p => p.type == "daily" && p.month.ts === dateFilter.ts).file.tasks;

//calculate total and completed tasks this month
let totalMonth = tasks.length;
let completedMonth = tasks.where(t => t.completed).length;

//print progress bar
function progress(value, total) {
    let pct = value/total * 100;
    return `<progress value="${parseInt(pct)}" max="100"></progress> | ${parseInt(pct)} %`
}

//print progress bars in table
dv.span(`
|     | Progress  | Percentage |
| --- | --- |:---:|
| **Tasks Completed**| ${progress(completedMonth, totalMonth)}  |
`)

```


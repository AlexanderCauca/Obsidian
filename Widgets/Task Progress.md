```dataviewjs
const today = new Date();
const daysToMonday = (8 - today.getDay()) % 7;  // ближайший понедельник (сегодня - воскресенье = 0)
const oneWeekFromNow = new Date(today.getTime() + daysToMonday * 24 * 60 * 60 * 1000);

const firstDayOfNextMonth = new Date(today.getFullYear(), today.getMonth() + 1, 1);
const oneMonthFromNow = firstDayOfNextMonth.getTime();

let tasks = [];

for (const page of dv.pages()) {
  // Исключаем заметки с excludeFromStats === true
  if (page.excludeFromStats === true) continue;

  if (page.file && page.file.tasks) {
    tasks.push(...page.file.tasks);
  }
}

// Функция для проверки даты и сравнения с указанной
function isDueBefore(task, date) {
  if (!task.due) return false;
  let dueDate = new Date(task.due);
  if (isNaN(dueDate)) return false;
  return dueDate <= date;
}

let totalTasks = tasks.length;
let completedTasks = tasks.filter(t => t.completed).length;

let monthlyTasks = tasks.filter(t => isDueBefore(t, oneMonthFromNow));
let completedMonthly = monthlyTasks.filter(t => t.completed);

let weeklyTasks = tasks.filter(t => isDueBefore(t, oneWeekFromNow));
let completedWeekly = weeklyTasks.filter(t => t.completed);

function progress(value, total) {
  if (total === 0) return "Нет задач";
  let pct = (value / total) * 100;
  return `<progress value="${pct.toFixed(1)}" max="100"></progress> | ${pct.toFixed(1)} %`;
}

dv.span(`
|     | Progress  | Percentage |
| --- | --- |:---:|
| **Всего задач** | ${progress(completedTasks, totalTasks)} | 
| **За месяц**| ${progress(completedMonthly.length, monthlyTasks.length)}  | 
| **За неделю** | ${progress(completedWeekly.length, weeklyTasks.length)}  | 
`);

```
^1
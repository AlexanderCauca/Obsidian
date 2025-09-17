```dataviewjs
const today = new Date();
const daysToMonday = (8 - today.getDay()) % 7;
const oneWeekFromNow = new Date(today.getTime() + daysToMonday * 24 * 60 * 60 * 1000);

const firstDayOfNextMonth = new Date(today.getFullYear(), today.getMonth() + 1, 1);
const oneMonthFromNow = firstDayOfNextMonth.getTime();

let tasks = [];

for (const page of dv.pages()) {
  if (page.excludeFromStats === true) continue;
  if (page.file && page.file.tasks) {
    tasks.push(...page.file.tasks);
  }
}

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

dv.span(`
Всего задач: ${totalTasks}, из них выполнено: ${completedTasks}  
Задач за месяц: ${monthlyTasks.length}, выполнено: ${completedMonthly.length}  
Задач за неделю: ${weeklyTasks.length}, выполнено: ${completedWeekly.length}  
`);

```

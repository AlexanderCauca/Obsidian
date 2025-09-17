```dataviewjs
// ---------- Общий прогресс ----------
const tasks = dv.current().file.tasks;
let total = tasks.length;
let done = tasks.where(t => t.completed).length;
let percent = total === 0 ? 0 : Math.round((done / total) * 100);
let bar = "█".repeat(percent/5) + "░".repeat(20 - percent/5);

// создаём контейнер с колонками
let container = dv.el("div", "", { cls: "progress-grid" });



// ---------- Функция для разделов ----------
function sectionProgress(name, keyword, parent) {
  let sectTasks = tasks.where(t => t.text.includes(keyword));
  let totalS = sectTasks.length;
  let doneS = sectTasks.where(t => t.completed).length;
  let percentS = totalS === 0 ? 0 : Math.round((doneS / totalS) * 100);
  let barS = "█".repeat(percentS/5) + "░".repeat(20 - percentS/5);

  let box = dv.el("div", "", { cls: "progress-box" }, parent);
  box.innerHTML = `<h4>${name}</h4><p>${doneS}/${totalS} (${percentS}%)<br>${barS}</p>`;
}

// ---------- Отдельные блоки ----------

sectionProgress("📱 ASP.NET", "ASP", container);

```
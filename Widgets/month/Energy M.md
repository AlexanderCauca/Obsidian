
```dataviewjs
const startOfMonth = moment().startOf('month');
const endOfMonth = moment().endOf('month');

// Все дни месяца
const allDays = [];
let day = startOfMonth.clone();
while (day.isSameOrBefore(endOfMonth, 'day')) {
    allDays.push(day.format("YYYY-MM-DD")); // формат YYYY-MM-DD
    day.add(1, 'day');
}

// Страницы за месяц
const pageList = dv.pages('"MainObsidian/_journal/2025/Daily Notes"')
    .where(p => p.date && moment(p.date, "YYYY-MM-DD").isBetween(startOfMonth, endOfMonth, 'day', '[]'))
    .values;

// Словарь по дате
const pages = pageList.reduce((acc, p) => {
    // нормализуем дату в такой же формат
    const d = moment(p.date, ["YYYY-MM-DD", "YYYY/MM/DD", "YYYY.MM.DD"]).format("YYYY-MM-DD");
    acc[d] = p;
    return acc;
}, {});

// Метки = все дни месяца
const labels = allDays;

// Игнорируем служебные поля
const excludeFields = [
    'date', 'tags', 'cssclasses',
    'banner', 'banner_x', 'banner_y',
    'type', 'month'
];

// Берём числовые поля (строки тоже конвертим)
const firstPage = pageList[0];
const fields = firstPage
    ? Object.keys(firstPage).filter(k => !excludeFields.includes(k))
    : [];

if (!fields.includes('morning_energy')) fields.push('morning_energy');
if (!fields.includes('evening_energy')) fields.push('evening_energy');
if (!fields.includes('health')) fields.push('health');

// Датасеты
const datasets = fields.map((field, idx) => ({
    label: field,
    data: allDays.map(d => {
        const val = pages[d]?.[field];
        return val !== undefined ? Number(val) : null; // конвертируем в число
    }),
    backgroundColor: `hsla(${idx * 60}, 70%, 70%, 0.2)`,
    borderColor: `hsla(${idx * 60}, 70%, 50%, 1)`,
    borderWidth: 1,
    tension: 0.3,
    pointBackgroundColor: `hsla(${idx * 60}, 70%, 50%, 1)`,
    pointRadius: 4,
    pointHoverRadius: 6
}));

// Рендер
const chartData = {
    type: 'line',
    data: {
        labels: labels,
        datasets: datasets
    }
};

window.renderChart(chartData, this.container);

```
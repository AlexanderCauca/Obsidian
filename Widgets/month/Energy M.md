
```dataviewjs
const startOfMonth = moment().startOf("month");
const endOfMonth = moment().endOf("month");

// Все страницы за месяц
const pages = dv.pages('"MainObsidian/_journal/2025/Daily Notes"')
    .where(p => p.date && moment(p.date).isBetween(startOfMonth, endOfMonth, null, "[]"))
    .sort(p => p.date, 'asc');

// Преобразуем в словарь { "2025-09-18": { ...данные... } }
const pageMap = {};
for (let p of pages) {
    const key = moment(p.date).format("YYYY-MM-DD");
    pageMap[key] = p;
}

// Генерируем список дат за месяц
const labels = [];
const daysData = {};
for (let d = startOfMonth.clone(); d.isSameOrBefore(endOfMonth); d.add(1, "day")) {
    const key = d.format("YYYY-MM-DD");
    labels.push(d.format("DD"));

    daysData[key] = {
        morning_energy: pageMap[key]?.morning_energy ?? null,
        evening_energy: pageMap[key]?.evening_energy ?? null,
        health: pageMap[key]?.health ?? null
    };
}

// Датасеты
const datasets = [
    {
        label: "Morning Energy",
        data: Object.values(daysData).map(v => v.morning_energy),
        borderColor: "rgba(255, 99, 132, 1)",
        backgroundColor: "rgba(255, 99, 132, 0.2)",
        tension: 0.3
    },
    {
        label: "Evening Energy",
        data: Object.values(daysData).map(v => v.evening_energy),
        borderColor: "rgba(54, 162, 235, 1)",
        backgroundColor: "rgba(54, 162, 235, 0.2)",
        tension: 0.3
    },
    {
        label: "Health",
        data: Object.values(daysData).map(v => v.health),
        borderColor: "rgba(75, 192, 192, 1)",
        backgroundColor: "rgba(75, 192, 192, 0.2)",
        tension: 0.3
    }
];

const chartData = {
    type: "line",
    data: {
        labels: labels,
        datasets: datasets
    }
};

window.renderChart(chartData, this.container);


```



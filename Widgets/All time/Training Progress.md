---
cssclasses:
---


```dataviewjs
const startDate = moment().startOf('year'); // начало года
this.container.style.height = "800px"; // высота графика

const pages = dv
	.pages('"training"')
	.where(p => p.date && moment(p.date).isSameOrAfter(startDate))
	.where(p => !p.file.path.includes("/tasks/")) // исключаем папку с задачами
	.sort(p => p.date, 'asc');

if (!pages.length) {
	dv.paragraph("Нет данных за этот год.");
} else {
	const labels = pages.map(p => p.file.name).values;

	const excludeFields = ['date', 'tags', 'cssclasses'];
	const fields = Object.keys(pages[0])
		.filter(k => !excludeFields.includes(k) && typeof pages[0][k] === 'number');

	if (!fields.includes('pushups')) fields.push('pushups');

	const datasets = fields.map((field, idx) => ({
		label: field,
		data: pages.map(p => p[field] ?? null).values,
		backgroundColor: `hsla(${idx * 60}, 70%, 70%, 0.2)`,
		borderColor: `hsla(${idx * 60}, 70%, 50%, 1)`,
		borderWidth: 1,
		tension: 0.3,
		pointBackgroundColor: `hsla(${idx * 60}, 70%, 50%, 1)`,
		pointRadius: 4,
		pointHoverRadius: 6
	}));

	const chartData = {
		type: 'line',
		data: {
			labels: labels,
			datasets: datasets
		}
	};

	window.renderChart(chartData, this.container);
}

```
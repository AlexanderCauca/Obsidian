
```dataviewjs
const startOfWeek = moment().startOf('month'); // понедельник текущей недели

const pages = dv
	.pages('"_journal/2025/Daily Notes"')
	.where(p => p.date && moment(p.date).isSameOrAfter(startOfWeek))
	.sort(p => p.date, 'asc');

if (!pages.length) {
	dv.paragraph("Нет данных за текущую неделю.");
} else {
	const labels = pages.map(p => p.file.name).values;

	// Игнорируем служебные поля
	const excludeFields = [
		'date', 'tags', 'cssclasses',
		'banner', 'banner_x', 'banner_y',
		'type', 'month'
	];

	// Берём только нужные числовые поля
	const fields = Object.keys(pages[0])
		.filter(k => !excludeFields.includes(k) && typeof pages[0][k] === 'number');

	// Добавляем, если нет
	if (!fields.includes('morning_mood')) fields.push('morning_mood');
	if (!fields.includes('evening_mood')) fields.push('evening_mood');
	if (!fields.includes('health')) fields.push('health');

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
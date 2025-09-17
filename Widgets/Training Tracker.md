```dataviewjs
dv.span("**🏋️ Тренировки**");

const calendarData = {
    colors: ["#d0f0c0", "#a2e087", "#72c45a", "#459c33", "#2e6e1f"],
    showCurrentDayBorder: true,
    defaultEntryIntensity: 10,
    intensityScaleStart: 10,
    intensityScaleEnd: 10,
    entries: []
};

const convertDate = (date) => {
    return date ? moment(date.toString()).format("YYYY-MM-DD") : null;
};

for (let page of dv.pages("#training")) {
    calendarData.entries.push({
        date: convertDate(page.date),
        intensity: 10,
        content: await dv.span(`[[${page.file.name}]]`)
    });
}

renderHeatmapCalendar(this.container, calendarData);
```

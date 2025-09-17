```dataviewjs
dv.span("**📚 Обучение**");

dv.span("** Papers Read 📝**")
const calendarData = {
    year: 2025,  // (optional) defaults to current year
    colors: {    // (optional) defaults to green
        
        orange:      ["#ffa244", "#fd7f00", "#dd6f00", "#bf6000", "#9b4e00"],
        pink:        ["#ff96cb", "#ff70b8", "#ff3a9d", "#ee0077", "#c30062"],
        orangeToRed: ["#ffdf04", "#ffbe04", "#ff9a03", "#ff6d02", "#ff2c01"]
    },
    showCurrentDayBorder: true, // (optional) defaults to true
    defaultEntryIntensity: 10,   // (optional) defaults to 4
    intensityScaleStart: 10,    // (optional) defaults to lowest value passed to entries.intensity
    intensityScaleEnd: 100,     // (optional) defaults to highest value passed to entries.intensity
    entries: [],                // (required) populated in the DataviewJS loop below
}

const countRead = (status)=>{
	return status ? 10 : 0;
}

const convertDate = (date)=>{
	var dateformat = "YYYY-MM-DD";
	if (date === null) {
		return "";
	}
	return moment(date.toString()).format(dateformat);
}

for (let page of dv.pages("#learning")) {
    calendarData.entries.push({
        date: convertDate(page.date),
        intensity: 10,
        content: await dv.span(`[[${page.file.name}]]`)
    });
}

renderHeatmapCalendar(this.container, calendarData);
```

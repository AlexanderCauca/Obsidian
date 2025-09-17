---
date: <%tp.date.now("YYYY-MM-DD")%>
week: <% tp.date.now("YYYY-WW") %>
month: <% tp.date.now("YYYY-MM") %>
tags:
  - "#training"
cssclasses:
  - wide-page
banner: "![[bannersportg1.gif]]"
banner_y: 
excludeFromStats: true
type: силовая
workout_time: 45
dumbbell_min: 10
dumbbell_max: 16
barbell_min: 20
barbell_max: 25
meditation: 10
abs_reps: 60
pushups: 50
---

<%*
const folderPath = "training/home";
const templateFile = tp.file.find_tfile("training-note-template"); // имя файла шаблона
if (!templateFile) throw "Template 'training-note-template' not found";
const fileName = tp.date.now("YYYY-MM-DD") + " Тренировка";
const newFile = await tp.file.create_new(templateFile, fileName, true, folderPath);
// newFile — TFile созданного файла, можно вывести ссылку, если нужно
%>

![[Training]]


> [!blank]
> - ### **Штанга** #mcl/list-card
> 	- ![[Mash Burnedead.jpg]]
> 	 - [ ] Жим штанги лёжа  
> 	 - [ ] становая тяга 
> 	 - [ ] Подъем штанги стоя до уровня груди с прогибом назад  
> 	 
> 
> - ### **Гантели**
> 	- ![[bannersport.jpg]]
> 	- [ ] Подъем гантелей поочередно стоя  
> 	- [ ] Подъем гантелей с поворотом кисти  
> 	- [ ]  Разведение гантелей лёжа ("флайсы") 
> 
> - ### **пресс**
> 	- ![[bannersport1.jpg]]
> 	- [ ] Пресс классический  
> 	- [ ] Скручивания с поворотом корпуса (косые мышцы)  
> 	- [ ] Планка ("мост дракона")  


![[Training Progress]]

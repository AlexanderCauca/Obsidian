---
tags:
  - cbs/base
  - programming/c-sharp/oop
cssclasses:
  - wide-page
  - minimal-float
  - c
banner: "![[PixeLɑnd ◇.gif]]"
banner_y: 0.5
---

# <center>Properties</center> 



> [!blank-container|right] 
> ## Definition  
> [[Properties|Properties]] — special members of a class that provide **controlled access** to [[Fields|fields]].  
> They allow reading and writing values using `get` and `set`.  
>
> Example:
> ```csharp
> private int age;
> public int Age
> {
>     get { return age; }
>     set { age = value; }
> }
> ```
>
> ## Characteristics  
> - Encapsulate [[Fields|fields]]  
> - Support read-only (`get`) or write-only (`set`) access  
> - May include extra logic (validation, calculations, etc.)  
> - Work like [[Methods|methods]] but look like [[Fields|fields]] 

 ## Определение  
 [[Properties|Свойства]] — это специальные члены класса, которые обеспечивают **контролируемый доступ** к [[Fields|полям]].  
 Они позволяют читать и изменять значения с помощью `get` и `set` методов.  

 Пример:
 ```csharp
 private int age;
 public int Age
 {
     get { return age; }   //блок инициализатор
     set { age = value; }
 }
 ```

 ## Особенности  
 - Позволяют инкапсулировать [[Fields|поля]]  
 - Поддерживают доступ только для чтения (`get`) или только для записи (`set`)  
 - Могут содержать дополнительную логику (валидация, вычисления и т.д.)  
 - Используются как [[Methods|методы]], но выглядят как [[Fields|поля]]  

> [!blank-container|right] 
> ## Definition  
> [[Auto-Properties|Auto-Properties]] — a simplified form of [[Properties|properties]], where the compiler generates a hidden [[Fields|field]] automatically.  
> Only `get` and `set` accessors are declared.  
>
> Example:
> ```csharp
> public class Person
> {
>     public string Name { get; set; }   // Auto-Property
>     public int Age { get; set; }       // Auto-Property
> }
>
> Person p = new Person { Name = "Alex", Age = 30 };
> ```
>
> ## Characteristics  
> - Do not require an explicit [[Fields|field]] — compiler creates it automatically  
> - Can restrict access: e.g. `public string Name { get; private set; }`  
> - Support default initialization  
> - Useful when no extra logic is needed in `get`/`set`  



 ## Определение  
 [[Auto-Properties|Автосвойства]] — это упрощённая форма [[Properties|свойств]], при которой не нужно явно объявлять [[Fields|поле]].  
 Компилятор автоматически создаёт скрытое поле, а мы описываем только `get` и `set`.  

 Пример:
 ```csharp
 public class Person
 {
     public string Name { get; set; }   // Автосвойство
     public int Age { get; set; }       // Автосвойство
 }

 Person p = new Person { Name = "Alex", Age = 30 };
 ```

 ## Особенности  
 - Не требуют явного [[Fields|поля]] — компилятор создаёт его автоматически  
 - Можно ограничить доступ: например, `public string Name { get; private set; }`  
 - Поддерживают инициализацию по умолчанию  
 - Используются чаще всего, когда не нужна дополнительная логика в `get`/`set`  



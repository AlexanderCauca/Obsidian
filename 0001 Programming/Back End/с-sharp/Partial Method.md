---
tags:
  - cbs/base
  - programming/c-sharp/oop
cssclasses:
  - wide-page
  - minimal-float
  - c
banner: "![[PixeLɑnd ◇.gif]]"
---

# Partial class#

> [!blank-container|right] 
> ## Definition  
> [[Partial Method|Partial method]] — a method declared in one part of a [[Partial Class|partial class]]  
> with the `partial` modifier and optionally implemented in another part.  
>
> If it’s not implemented, the compiler **removes its declaration and calls**.  
>
> Example:
> ```csharp
> // File: Person.Data.cs
> public partial class Person
> {
>     public string Name { get; set; }
>     public int Age { get; set; }
>
>     partial void OnCreated();
>
>     public Person()
>     {
>         OnCreated();
>     }
> }
>
> // File: Person.Methods.cs
> public partial class Person
> {
>     partial void OnCreated()
>     {
>         Console.WriteLine("Person object created!");
>     }
> }
> ```
>
> ## Characteristics  
> - Declared with `partial` modifier  
> - Must return `void` and are implicitly `private`  
> - Cannot have `out` parameters (only `ref`)  
> - If not implemented → removed at compile time  
> - Useful for extending auto-generated code without modifying it  



 ## Определение  
 [[Partial Method|Частичный метод]] — это метод, который **объявляется в одной части класса** с модификатором `partial`,  
 а **реализуется (или не реализуется) в другой части** того же [[Partial Class|частичного класса]].  

 Если метод не реализован, то компилятор **полностью удаляет его объявление и вызовы** → не будет ни накладных расходов, ни ошибок.  

 Пример:
 ```csharp
 // File: Person.Data.cs
 public partial class Person
 {
     public string Name { get; set; }
     public int Age { get; set; }

     partial void OnCreated(); // Объявление частичного метода

     public Person()
     {
         OnCreated(); // Вызов частичного метода
     }
 }

 // File: Person.Methods.cs
 public partial class Person
 {
     // Реализация частичного метода
     partial void OnCreated()
     {
         Console.WriteLine("Person object created!");
     }
 }

 // Использование
 Person p = new Person(); // => "Person object created!"
 ```

 ## Особенности  
 - Определяются с помощью модификатора `partial`  
 - Должны быть `void` и `private` (по умолчанию)  
 - Не могут иметь `out` параметры (только `ref`)  
 - Если метод **не реализован**, он и все вызовы удаляются на этапе компиляции  
 - Используются для расширения автоматически сгенерированного кода без его изменения  



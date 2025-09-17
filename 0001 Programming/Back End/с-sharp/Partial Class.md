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
> [[Partial Class|Partial class]] — a class whose definition can be **split across multiple files**.  
> The compiler combines them into **a single class** at compile time.  
>
> Useful when:  
> - multiple developers work on the same class  
> - part of the code is auto-generated (e.g., WinForms/WPF designer)  
> - separating logic into multiple files improves readability  
>
> Example:
> ```csharp
> // File: Person.Data.cs
> public partial class Person
> {
>     public string Name { get; set; }
>     public int Age { get; set; }
> }
>
> // File: Person.Methods.cs
> public partial class Person
> {
>     public void PrintInfo()
>     {
>         Console.WriteLine($"{Name}, {Age} years old");
>     }
> }
> ```
>
> ## Characteristics  
> - Declared with the `partial` modifier  
> - All parts must have the same [[Access Modifiers|access modifiers]]  
> - All parts must be in the same namespace  
> - Compiler merges all parts into one class  
> - Can also split [[Struct|structs]], [[Interface|interfaces]], and [[Record|records]]  


 ## Определение  
 [[Partial Class|Частичный класс]] — это класс, определение которого может быть **разделено на несколько файлов**.  
 Все части объединяются компилятором в **один класс** при сборке.  

 Это удобно, когда:  
 - над классом работает несколько разработчиков  
 - код автоматически генерируется (например, дизайнер форм в WinForms/WPF)  
 - нужно разделить логику на отдельные файлы для удобства поддержки  

 Пример:
 ```csharp
 // File: Person.Data.cs
 public partial class Person
 {
     public string Name { get; set; }
     public int Age { get; set; }
 }

 // File: Person.Methods.cs
 public partial class Person
 {
     public void PrintInfo()
     {
         Console.WriteLine($"{Name}, {Age} years old");
     }
 }

 // Использование
 Person p = new Person { Name = "Alex", Age = 30 };
 p.PrintInfo(); // Alex, 30 years old
 ```

 ## Особенности  
 - Объявляются с модификатором `partial`  
 - Все части должны иметь одинаковые [[Access Modifiers|модификаторы доступа]]  
 - Все части должны находиться в **одном пространстве имён**  
 - Компилятор объединяет части в один класс  
 - Можно разделять не только классы, но и [[Struct|структуры]], [[Interface|интерфейсы]] и [[Record|записи]]  


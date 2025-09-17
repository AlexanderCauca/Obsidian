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

# <center>Constructors</center> 



> [!blank-container|right] 
> ## Definition  
> [[Constructors|Constructor]] — a special [[Methods|method]] of a class that is called when an object is created.  
> It is used to initialize [[Fields|fields]] and set the initial state of the object.  
>
> Example:
> ```csharp
> public class Person
> {
>     public string Name { get; set; }
>     public int Age { get; set; }
>
>     // Constructor
>     public Person(string name, int age)
>     {
>         Name = name;
>         Age = age;
>     }
> }
>
> Person p = new Person("Alex", 30);
> ```
>
> ## Characteristics  
> - Has the same name as the [[Class|class]]  
> - Has no return type (not even `void`)  
> - Can be overloaded (multiple constructors with different parameters)  
> - Can call another constructor via `this()`  
> - Can call a base class constructor via `base()`  
> - If not defined explicitly, a default constructor is created  



 ## Определение  
 [[Constructors|Конструктор]] — это специальный [[Methods|метод]] класса, который вызывается при создании объекта.  
 Он используется для инициализации [[Fields|полей]] и установки начального состояния объекта.  

 Пример:
 ```csharp
 public class Person
 {
     public string Name { get; set; }
     public int Age { get; set; }

     // Конструктор
     public Person(string name, int age)
     {
         Name = name;
         Age = age;
     }
 }

 Person p = new Person("Alex", 30);
 ```

 ## Особенности  
 - Имя конструктора совпадает с именем [[Class|класса]]  
 - Не имеет возвращаемого типа (даже `void`)  
 - Может быть перегружен (несколько конструкторов с разными параметрами)  
 - Может вызывать другой конструктор через `this()`  
 - Может вызывать конструктор базового класса через `base()`  
 - Если явно не определён, создаётся конструктор по умолчанию  

---
tags:
  - cbs/base
  - programming/c-sharp/oop
cssclasses:
  - wide-page
banner: "![[PixeLɑnd ◇.gif]]"
---

# <center>Еncapsulation</center> 

> [!blank-container|right] 
> ## Definition  
> [[Encapsulation|Encapsulation]] — a principle of [[OOP|object-oriented programming]]  
> that means combining data ([[Fields|fields]], [[Properties|properties]]) and [[Methods|methods]]  
> into a single [[Class|class]] while controlling access to them.  
>
> The main goal is to **hide internal implementation** and provide a safe interface.  
>
> Example:
> ```csharp
> public class Person
> {
>     private int age;
>
>     public int Age
>     {
>         get { return age; }
>         set
>         {
>             if (value >= 0) age = value;
>         }
>     }
> }
> ```
>
> ## Characteristics  
 >- Hides implementation details from external code  
 >- Controls access with [[Access Modifiers|access modifiers]]  
 >- Uses [[Properties|properties]] and [[Methods|methods]] for data access  
 >- Improves code reliability and security  

## Определение  
 [[Encapsulation|Инкапсуляция]] — это принцип [[OOP|объектно-ориентированного программирования]],  
который заключается в **объединении данных** ([[Fields|полей]], [[Properties|свойств]]) и [[Methods|методов]]  
 в единый [[Class|класс]] с контролем доступа к этим данным.  

 Главная цель — **скрыть внутреннюю реализацию** и предоставить только безопасный интерфейс для работы.  

 Пример:
 ```csharp
 public class Person
 {
     // Закрытое поле
     private int age;

     // Свойство для безопасного доступа
     public int Age
     {
         get { return age; }
         set
         {
             if (value >= 0) age = value; // Валидация
         }
     }
 }

 Person p = new Person();
 p.Age = 25;         // допустимо
 p.Age = -5;         // игнорируется (валидация)
 ```

 ## Особенности  
 - Скрывает детали реализации от внешнего кода  
 - Управляет доступом с помощью [[Access Modifiers|модификаторов доступа]]  
 - Использует [[Properties|свойства]] и [[Methods|методы]] для работы с данными  
 - Повышает надёжность и безопасность кода  



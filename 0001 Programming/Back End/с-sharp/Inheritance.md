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
> [[Inheritance|Inheritance]] — one of the core principles of [[OOP|object-oriented programming]], 
> allowing a [[Class|child class]] to **reuse fields and methods** of a [[Class|parent class]].  
>  
> It helps:  
> - reuse code  
> - extend base class functionality  
> - build object hierarchies  
>
> ## Characteristics  
> - Declared with `:` after the class name  
> - Supports [[Polymorphism|polymorphism]] (methods can be overridden)  
> - C# supports only single class inheritance  
> - A class can implement multiple [[Interfaces|interfaces]]  

 ## Определение  
 [[Inheritance|Наследование]] — это один из основных принципов [[OOP|объектно-ориентированного программирования]], который позволяет [[Class|классу]]-потомку **использовать поля и методы** [[Class|класса]]-родителя.  
  
 Наследование помогает:  
 - повторно использовать код  
 - расширять функциональность базовых классов  
 - строить иерархии объектов  

 ## Особенности  
 - Класс-потомок объявляется через двоеточие `:`  
 - Поддерживает [[Polymorphism|полиморфизм]] (можно переопределять методы)  
 - Может наследовать только один класс (в C# — одиночное наследование)  
 - Может реализовывать несколько [[Interfaces|интерфейсов]]  

Information Technology Video Developer Network https://itvdn.comITVDN
C# Базовий


Конструктор

Існує кілька дій, що є частиною ініціалізації нового екземпляра. Ці дії виконуються у такому порядку:
1. Для полів екземпляра встановлено значення 0. Зазвичай це робиться середовищем виконання.
2. Запускаються ініціалізатори полів. Виконуються ініціалізатори полів у похідних типах.
3. Запускаються ініціалізатори полів базового типу. Ініціалізатори полів починаються з прямого зв’язку
кожного типу з базовим типом System.Object.
4. Запускаються конструктори базових типів. Усі конструктори екземплярів, починаючи з Object.Object
кожного базового класу до прямого базового класу.
5. Виконується конструктор екземпляра конкретного типу.
6. Запускаються ініціалізатори об'єктів.
https://learn.microsoft.com/ru-ru/dotnet/csharp/programming-guide/classes-and-structs/constructors

> ## Пример
> ```csharp
> // Базовый класс
> class Animal
> {
>     public void Eat() => Console.WriteLine("Я ем!");
>     public virtual void Speak() => Console.WriteLine("Животное издаёт звук");
> }
>
> // Класс-наследник
> class Dog : Animal
> {
>     public override void Speak() => Console.WriteLine("Гав!");
> }
>
> class Program
> {
>     static void Main()
>     {
>         Animal a = new Animal();
>         a.Speak(); // Животное издаёт звук
>
>         Dog d = new Dog();
>         d.Eat();   // Я ем!
>         d.Speak(); // Гав!
>     }
> }
> ```
>

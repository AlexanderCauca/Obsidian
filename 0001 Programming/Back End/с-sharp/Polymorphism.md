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
> [[Polymorphism|Polymorphism]] — a principle of [[OOP|object-oriented programming]]
> that allows objects of **different classes** to respond differently to the same method calls.  
>
> Types of polymorphism in C#:  
> - [[Virtual Methods|Virtual methods]] and `override` — redefine behavior in child classes  
> - [[Abstract Classes|Abstract classes]] — force child classes to implement methods  
> - [[Interfaces|Interfaces]] — different classes can implement the same behavior by contract  
>
> ## Characteristics  
> - Provides flexibility and extensibility of code  
> - Achieved via `virtual`, `override`, `abstract`, and `interface`  
> - Enables working with objects through a common type (base class or interface)  
> ## [[Upcasting и Downcasting]]  
> - **Upcasting** — safe conversion of a child class object to its parent type  
> - **Downcasting** — explicit conversion of a parent type object back to a child type  
>

 ## Определение  
 [[Polymorphism|Полиморфизм]] — это принцип [[OOP|объектно-ориентированного программирования]], который позволяет объектам **разных классов** реагировать по-разному на одни и те же вызовы методов.  
  
 Слово "полиморфизм" буквально означает *"много форм"*.  

 Основные виды полиморфизма в C#:  
 - [[Virtual Methods|Виртуальные методы]] и `override` — переопределение поведения в наследниках  
 - [[Abstract Classes|Абстрактные классы]] — заставляют наследников реализовать методы  
 - [[Interfaces|Интерфейсы]] — разные классы могут реализовать одинаковое поведение по контракту  

 ## Особенности  
 - Обеспечивает гибкость и расширяемость кода  
 - Поддерживается через ключевые слова `virtual`, `override`, `abstract` и `interface`  
 - Позволяет работать с объектами через общий тип (родительский класс или интерфейс)  
 -  ## [[Upcasting и Downcasting]]  
- **Upcasting** – преобразование объекта **дочернего класса** к **типу родительского класса**.  
  🔹 Безопасно, выполняется автоматически.  
- **Downcasting** – преобразование объекта **родительского класса** к **типу дочернего класса**.  
  🔹 Может быть небезопасно, требует явного указания. 


 ## Пример 1. Виртуальные методы и override
 ```csharp
 class Animal
 {
     public virtual void Speak() => Console.WriteLine("Животное издаёт звук");
 }

 class Dog : Animal
 {
     public override void Speak() => Console.WriteLine("Гав!");
 }

 class Cat : Animal
 {
     public override void Speak() => Console.WriteLine("Мяу!");
 }

 class Program
 {
     static void Main()
     {
         Animal[] animals = { new Dog(), new Cat(), new Animal() };
         
         foreach (var a in animals)
             a.Speak(); 
        // Гав!
         // Мяу!
         // Животное издаёт звук
     }
 }
 ```

 ## Пример 2. Абстрактные классы
 ```csharp
 abstract class Shape
 {
     public abstract double Area();
 }

 class Circle : Shape
 {
     public double Radius { get; set; }
     public Circle(double r) => Radius = r;
     public override double Area() => Math.PI * Radius * Radius;
 }

 class Rectangle : Shape
 {
     public double Width { get; set; }
     public double Height { get; set; }
     public Rectangle(double w, double h) { Width = w; Height = h; }
     public override double Area() => Width * Height;
 }

 class Program
{
     static void Main()
     {
         Shape[] shapes = { new Circle(5), new Rectangle(4, 6) };
         foreach (var s in shapes)
            Console.WriteLine(s.Area());
         // 78.5398...
         // 24
     }
 }
 ```

 ## Пример 3. Интерфейсы
 ```csharp
 interface IMovable
 {
     void Move();
 }

 class Car : IMovable
 {
     public void Move() => Console.WriteLine("Машина едет");
 }

 class Person : IMovable
 {
     public void Move() => Console.WriteLine("Человек идёт");
 }

 class Program
 {
     static void Main()
     {
         IMovable[] movables = { new Car(), new Person() };
         foreach (var m in movables)
             m.Move();
         // Машина едет
         // Человек идёт
     }
 }
 ```
> ## Сравнение способов полиморфизма  
>
> | Подход | Можно содержать реализацию? | Обязателен override/реализация? | Поддержка множественного наследования | Пример использования |
> |--------|-----------------------------|---------------------------------|---------------------------------------|----------------------|
> | Виртуальные методы | ✅ Да (базовая реализация есть) | ❌ Нет (можно не переопределять) | ❌ Только один базовый класс | Когда есть поведение "по умолчанию", но наследник может переопределить |
> | Абстрактные классы | ⚠ Частично (могут быть как реализованные методы, так и абстрактные) | ✅ Да, для абстрактных методов | ❌ Только один абстрактный класс | Когда нужно задать общую основу, но часть поведения обязаны описать наследники |
> | Интерфейсы| ❌ Нет (только сигнатуры методов) | ✅ Всегда | ✅ Можно реализовывать много интерфейсов | Когда нужно задать контракт, который разные классы будут выполнять по-своему |
>
> ## Вывод  
> - Используй **виртуальные методы**, когда есть базовая логика, которую иногда нужно менять.  
> - Используй [[Abstract Classes|Абстрактные классы]], когда нужна общая база + строгие обязательства для наследников.  
> - Используй **интерфейсы**, когда разные классы должны выполнять один контракт, но не имеют общей реализации.  

 ## Визуальные UML-схемы полиморфизма  

> [!multi-column]
> > [!note]+ ### [[Virtual Methods|Виртуальные методы]]
> >     ```
> >     Animal
> >     + Speak()
>>        │ (virtual)
> >       ▼
> >     Dog : Animal
> >     + Speak() (override)
> >     ```
> >     Пример: `Dog` наследует `Animal` и переопределяет метод `Speak()`.
> 
> > [!note]+  ### [[Abstract Classes|Абстрактные классы]]
> >     ```
> >     Shape (abstract)
> >     + Area() (abstract)
> >       │ (обязательная реализация)
> >       ▼
> >     Circle : Shape
> >     + Area()
> >     
> >     Rectangle : Shape
> >     + Area()
> >     ```
> >     Пример: все фигуры должны реализовать `Area()`.
> 
> > [!note]+ ### [[Interfaces|Интерфейсы]]
> >     ```
> >     IMovable (interface)
> >     + Move()
> >       ▲
> >       │ (реализация контракта)
> >     ┌───┴────────────┐
> >     │                │
> >     Car           Person
> >     + Move()       + Move()
> >     ```
> >     Пример: и `Car`, и `Person` реализуют интерфейс `IMovable`, но по-своему.
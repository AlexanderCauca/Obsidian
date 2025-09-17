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

# <center>Abstract Classes</center>  

> [!blank-container|right] 
> ## Definition  
> [[Abstract Classes|Abstract Classes]] in C# are classes that cannot be instantiated directly 
> and are intended to be a base class for other classes.  
>
> Abstract classes can contain:  
> - [[Fields|fields]]  
> - [[Properties|properties]]  
> - [[Methods|methods]] (both abstract and implemented)  
> - [[Constructors|constructors]]  
>
> ## Example  
> ```csharp
> // Абстрактный класс
> abstract class Shape
> {
>     public string Name { get; set; }
>
>     public Shape(string name)
>     {
>         Name = name;
>     }
>
>     // Абстрактный метод — реализация в наследниках
>     public abstract double GetArea();
>
>     // Метод с реализацией
>     public void DisplayName()
>     {
>         Console.WriteLine($"Shape: {Name}");
>     }
> }
>
> // Наследник
> class Circle : Shape
> {
>     public double Radius { get; set; }
>
>     public Circle(string name, double radius) : base(name)
>     {
>         Radius = radius;
>     }
>
>     public override double GetArea()
>     {
>         return Math.PI * Radius * Radius;
>     }
> }
>
> class Program
> {
>     static void Main()
> {
>     Shape myCircle = new Circle("My Circle", 5);
>     myCircle.DisplayName();
>     Console.WriteLine($"Area: {myCircle.GetArea()}");
> }
> }
> ```
>
> ## Characteristics  
> - Cannot create an object directly from an abstract class  
> - Can contain abstract methods that must be implemented by derived classes  
> - Can contain concrete methods with implementation  
> - Supports inheritance and polymorphism  

## Определение  
[[Abstract Classes|Абстрактные классы]] в C# — это классы, которые **не могут быть созданы напрямую** и предназначены для использования в качестве базового класса для других классов.  

Абстрактные классы могут содержать:  
- [[Fields|поля]]  
- [[Properties|свойства]]  
- [[Methods|методы]] (как абстрактные, так и с реализацией)  
- [[Constructors|конструкторы]]  

## Пример  
- Создаём абстрактный класс `Shape` с абстрактным методом `GetArea()` и обычным методом `DisplayName()`.  
- Создаём наследника `Circle`, который реализует `GetArea()`.  
- В `Main` создаём объект через базовый тип `Shape`, вызываем методы `DisplayName()` и `GetArea()`.  

## Особенности  
- Нельзя создать объект напрямую из абстрактного класса  
- Абстрактные методы должны быть реализованы в наследниках  
- Можно использовать методы с реализацией внутри абстрактного класса  
- Поддерживает наследование и полиморфизм  

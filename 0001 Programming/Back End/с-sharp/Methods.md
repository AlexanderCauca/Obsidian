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

# <center>Methods</center>  

> [!blank-container|right] 
> ## Definition  
> [[Methods|Methods]] in C# are blocks of code that perform specific tasks and can be called on [[Object|objects]] or [[Class|classes]].  
>
> Methods can have:  
> - Parameters — input values  
> - Return values — output results  
> - Access modifiers — control visibility  
> - Abstract methods — declared without implementation in [[Abstract Classes|abstract classes]]  
>
> ## Example  
> ```csharp
> // Абстрактный класс с абстрактным методом
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
>     // Обычный метод с реализацией
>     public void DisplayName()
>     {
>         Console.WriteLine($"Shape: {Name}");
>     }
> }
>
> class Circle : Shape
> {
>     public double Radius { get; set; }
>
>     public Circle(string name, double radius) : base(name)
>     {
>         Radius = radius;
>     }
>
>     // Реализация абстрактного метода
>     public override double GetArea()
>     {
>         return Math.PI * Radius * Radius;
>     }
> }
>
> class Program
> {
>     static void Main()
> 
>     {
>         Shape myCircle = new Circle("My Circle", 5);
>         myCircle.DisplayName();
>         Console.WriteLine($"Area: {myCircle.GetArea()}");
>     }
> }
> ```

## Определение  
[[Methods|Методы]] в C# — это блоки кода, которые выполняют определённые задачи и могут быть вызваны на [[Object|объектах]] или [[Class|классах]].  

Методы могут иметь:  
- Параметры — входные значения  
- Возвращаемое значение — результат работы метода  
- Модификаторы доступа — контролируют видимость  
- Абстрактные методы — объявлены без реализации в [[Abstract Classes|абстрактных классах]]  
- [[Virtual Methods|Виртуальные методы]] в C# — это методы базового класса, которые могут быть **переопределены** в производных классах с помощью ключевого слова `override`.  

## Пример  
- Создаём абстрактный класс `Shape` с абстрактным методом `GetArea()` и обычным методом `DisplayName()`.  
- Создаём наследника `Circle`, который реализует `GetArea()`.  
- В `Main` создаём объект через базовый тип `Shape`, вызываем методы `DisplayName()` и `GetArea()`.  

## Особенности  
- Инкапсулируют код для повторного использования  
- Можно вызывать несколько раз с разными параметрами  
- Могут возвращать значение или быть `void`  
- Могут быть экземплярными или статическими методами  
- Абстрактные методы должны быть реализованы в наследниках  

 ## Characteristics  
 - Encapsulate code for reuse  
 - Can be called multiple times with different parameters  
 - Can return a value or be void  
 - Can be instance or static methods  
 - Abstract methods must be implemented in derived classes  


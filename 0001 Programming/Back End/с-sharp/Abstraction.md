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


# <center>Abstraction Example</center>  

> [!blank-container|right] 
> ## Example in C#  
> ```csharp
> // Интерфейс для животных
> interface IAnimal
> {
>     void Speak(); // Метод без реализации
> }
>
> // Абстрактный класс
> abstract class Animal : IAnimal
> {
>     public string Name { get; set; }
>
>     public Animal(string name)
>     {
>         Name = name;
>     }
>
>     // Абстрактный метод — реализация в потомках
>     public abstract void Speak();
>
>     // Обычный метод с реализацией
>     public void Eat()
>     {
>         Console.WriteLine($"{Name} is eating.");
>     }
> }
>
> // Конкретный класс
> class Dog : Animal
> {
>     public Dog(string name) : base(name) {}
>
>     public override void Speak()
> {
>         Console.WriteLine($"{Name} barks!");
>     }
> }
>
> class Program
> {
>     static void Main()
>     {
>         Animal myDog = new Dog("Buddy"); // Абстракция через базовый класс
>         myDog.Speak(); // вызывает конкретную реализацию
>         myDog.Eat();   // вызывает метод из абстрактного класса
>
>         IAnimal animalInterface = myDog; // Абстракция через интерфейс
>         animalInterface.Speak();
>     }
> }
> ```



## Определение  
[[Abstraction|Абстракция]] в C# — это принцип скрытия деталей реализации и предоставления только необходимых характеристик класса или объекта.  

Абстракция достигается с помощью [[Abstract Classes|абстрактных классов]] и [[Interfaces|интерфейсов]].  

## Особенности  
- Позволяет сосредоточиться на том, что делает объект, а не как он это делает  
- Упрощает работу с комплексными системами, показывая только необходимый функционал  
- Поддерживает [[Polymorphism|полиморфизм]] через общий интерфейс  
- Реализуется через абстрактные методы, свойства или интерфейсы

## Особенности  
- Абстракция позволяет работать с объектом через **общий интерфейс или базовый класс**, не заботясь о деталях реализации.  
- Абстрактные методы и интерфейсы обеспечивают **обязательную реализацию в потомках**.  
- Упрощает поддержку кода и делает его более расширяемым.  

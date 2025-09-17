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

# <center>Interfaces</center>  

> [!blank-container|right] 
> ## Definition  
> [[Interfaces|Interfaces]] in C# define a contract that classes can implement.  
> They contain method, property, indexer, or event signatures without implementation.  
>
> ## Example  
> ```csharp
> // Интерфейс
> interface IAnimal
> {
>     void Speak();  // Метод без реализации
> }
>
> // Класс реализует интерфейс
> class Dog : IAnimal
> {
>     public string Name { get; set; }
>
>     public Dog(string name)
>     {
>         Name = name;
>     }
>
>     public void Speak()
>     {
>         Console.WriteLine($"{Name} barks!");
>     }
> }
>
> class Program
> {
>     static void Main()
>     {
>         IAnimal myDog = new Dog("Buddy");
>         myDog.Speak(); // вызов метода через интерфейс
>     }
> }
> ```
>


## Определение  
[[Interfaces|Интерфейсы]] в C# — это контракт, который должны реализовать классы.  
Они содержат **подписи методов, свойств, индексаторов или событий**, но не имеют реализации.  

## Пример  
- Создаём интерфейс `IAnimal` с методом `Speak()`.  
- Создаём класс `Dog`, который реализует метод `Speak()`.  
- В `Main` создаём объект через интерфейс `IAnimal` и вызываем метод `Speak()`.  

## Особенности  
- Определяют контракт, который обязаны реализовать классы  
- Позволяют множественное наследование поведения  
- Поддерживают [[Polymorphism|полиморфизм]]  
- Не могут содержать поля, только подписи методов и свойств, константы
- методы приватные
 
## Characteristics  
- Define a contract that must be implemented by classes  
- Allow multiple inheritance of behavior  
- Support [[Polymorphism|polymorphism]]  
- Cannot contain fields, only signatures  


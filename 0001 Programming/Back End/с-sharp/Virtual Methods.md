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

# <center>Virtual Methods</center>  

> [!blank-container|right] 
> ## Definition  
> [[Virtual Methods|Virtual Methods]] in C# are methods in a base class that can be **overridden** in derived classes using the `override` keyword.  
>
> ## Example  
> ```csharp
> class Animal
> {
>     public virtual void Speak()
>     {
>         Console.WriteLine("Some generic animal sound");
>     }
> }
>
> class Dog : Animal
> {
>     public override void Speak()
>     {
>         Console.WriteLine("Bark!");
>     }
> }
>
> class Program
> {
>     static void Main()
>     {
>         Animal myAnimal = new Animal();
>         myAnimal.Speak(); // Some generic animal sound
>
>         Animal myDog = new Dog();
>         myDog.Speak(); // Bark! — вызов переопределённого метода
>     }
> }
> ```
>
> ## Characteristics  
> - Allow **runtime polymorphism**  
> - Must be declared with `virtual` in the base class  
> - Can be overridden in derived classes with `override`  
> - Can still be called on the base class reference  

## Определение  
[[Virtual Methods|Виртуальные методы]] в C# — это методы базового класса, которые могут быть **переопределены** в производных классах с помощью ключевого слова `override`.  

## Пример  
- Создаём класс `Animal` с виртуальным методом `Speak()`.  
- Создаём наследника `Dog`, который переопределяет метод `Speak()`.  
- В `Main` создаём объекты через базовый тип `Animal` и вызываем метод, чтобы увидеть **полиморфное поведение**.  

## Особенности  
- Обеспечивают **полиморфизм во время выполнения**  
- Должны быть объявлены с ключевым словом `virtual` в базовом классе  
- Могут быть переопределены в производных классах с ключевым словом `override`  
- Можно вызывать через ссылку на базовый класс  


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

# <center>is и as</center>  

> [!blank-container|right] 
> ## Definition  
> [[is and as|is and as]] — operators in C# used for type checking and safe type casting in [[OOP|object-oriented programming]].  
>
> - `is` — checks whether an object is an instance of a specific type.  
> - `as` — performs type conversion and returns `null` if the conversion is not possible.  
>
> ## Characteristics  
> - `is`:  
>   - Returns `true` or `false`  
>   - Used for conditional checks before casting  
> - `as`:  
>   - Returns a converted object or `null`  
>   - Avoids throwing exceptions on failed casting  
>
> ## Example  
> ```csharp
> class Animal 
> {
>     public virtual void Speak() => Console.WriteLine("Animal speaks");
> }
>
> class Dog : Animal 
> {
>     public override void Speak() => Console.WriteLine("Dog barks");
>     public void Fetch() => Console.WriteLine("Dog fetches a stick");
> }
>
> class Program 
> {
>     static void Main() 
>     {
>         Animal animal = new Dog();
>         Animal another = new Animal();
>
>         // is operator
>         if (animal is Dog d) 
>         {
>             d.Fetch(); // Safe cast + Dog method call
>         }
>
>         // as operator
>         Dog dog1 = another as Dog;  // another is not Dog → dog1 = null
>         if (dog1 != null) 
>         {
>             dog1.Fetch();
>         }
>         else 
>         {
>             Console.WriteLine("Conversion failed");
>         }
>     }
> }
> ```

## Определение  
[[is and as|is и as]] — это операторы C#, используемые для проверки типов и безопасного преобразования в [[OOP|объектно-ориентированном программировании]].  

- `is` — проверяет, является ли объект экземпляром определённого типа.  
- `as` — выполняет преобразование и возвращает `null`, если оно невозможно.  

## Особенности  
- `is`:  
  - Возвращает `true` или `false`  
  - Используется для проверки типа перед приведением  
- `as`:  
  - Возвращает преобразованный объект или `null`  
  - Избегает выброса исключений при ошибке  

## Пример  
```csharp
class Animal 
{
    public virtual void Speak() => Console.WriteLine("Animal speaks");
}

class Dog : Animal 
{
    public override void Speak() => Console.WriteLine("Dog barks");
    public void Fetch() => Console.WriteLine("Dog fetches a stick");
}

class Program 
{
    static void Main() 
    {
        Animal animal = new Dog();
        Animal another = new Animal();

        // оператор is
        if (animal is Dog d) 
        {
            d.Fetch(); // безопасное приведение + вызов метода Dog
        }

        // оператор as
        Dog dog1 = another as Dog;  // another не является Dog → dog1 = null
        if (dog1 != null) 
        {
            dog1.Fetch();
        }
        else 
        {
            Console.WriteLine("Преобразование не удалось");
        }
    }
}


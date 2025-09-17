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

# Class in C#

> [!blank-container|right] 
> ## Определение  
> [[Class|Класс]] — это описание объекта, которое задаёт его данные и поведение.  
> Он определяет:  
> - [[Fields|Поля]] — внутренние данные (состояние)  
> - [[Properties|Свойства]] — безопасный доступ к данным (инкапсуляция)  
> - [[Methods|Методы]] — действия и поведение объекта  
> - [[Constructors|Конструкторы]] — способ создания и начальной настройки объекта  
>
> ## Особенности  
> - Объявляется с помощью ключевого слова `class`  
> - Является [[Reference type|ссылочным типом]]  
> - Может содержать [[Fields|поля]], [[Properties|свойства]], [[Methods|методы]], [[Constructors|конструкторы]]  
> - Поддерживает [[Inheritance|наследование]] и [[Polymorphism|полиморфизм]]  
> - Может реализовывать [[Interfaces|интерфейсы]]  
>
> ## Definition  
> [[Class|Class]] — a description of an object that defines its data and behavior.  
> It includes:  
> - [[Fields|Fields]] — internal data (state)  
> - [[Properties|Properties]] — controlled access to data (encapsulation)  
> - [[Methods|Methods]] — actions and behavior of the object  
> - [[Constructors|Constructors]] — rules for creating and initializing an object  
>
> ## Characteristics  
> - Declared with the `class` keyword  
> - Is a [[Reference type|reference type]]  
> - Can have [[Fields|fields]], [[Properties|properties]], [[Methods|methods]], [[Constructors|constructors]]  
> - Supports [[Inheritance|inheritance]] and [[Polymorphism|polymorphism]]  
> - Can implement [[Interfaces|interfaces]]



## Структура класса

```csharp
// Определение класса
public class Person
{
    // Поля (состояние объекта)
    private string _name;
    private int _age;
    
    // Свойства (доступ к полям)
    public string Name
    {
        get => _name;
        set => _name = value;
    }
    
    public int Age
    {
        get => _age;
        set => _age = value;
    }
    
    // Конструктор (создание и инициализация)
    public Person(string name, int age)
    {
        _name = name;
        _age = age;
    }
    
    // Метод (поведение)
    public void Introduce()
    {
        Console.WriteLine($"Меня зовут {_name}, мне {_age} лет");
    }
}

// Использование класса
Person person = new Person("Иван", 25);
person.Introduce();
```

```csharp
MyClass instance = new MyClass(); //создаеться Экземплер класа\обьект(одно и тоже)
```


```csharp
using System;

// Классы.

namespace Classes
{
    // Создаём класс с именем MyClass.
    // В теле класса создаём открытое поле типа string с именем field и метод с именем Method.

    class MyClass
    {
        public string field;

        public void Method()
        {
            Console.WriteLine(field);
        }
    }

    class Program
    {
        static void Main()
        {
            // 1. Создаём экземпляр класса MyClass (по сильной ссылке).
            // 2. Создаём экземпляр класса MyClass с именем instance.
            // 3. Инстанцируем класс MyClass.
            // 4. Создаём переменную с именем instance типа MyClass и присваиваем ей адрес экземпляра в куче.
            // (instance — это ссылка на экземпляр класса MyClass, созданный в куче)

            MyClass instance = new MyClass();

            // Полю field экземпляра instance присваиваем значение "Green!".

            instance.field = "Green!";

            // Выводим на экран значение поля field экземпляра instance.

            Console.WriteLine(instance.field);

            // Вызываем метод Method у экземпляра instance.
            instance.Method();

            new MyClass().Method(); // Создаём экземпляр класса MyClass (по слабой ссылке)

            // Задержка.
            Console.ReadKey();
        }
    }
}

```
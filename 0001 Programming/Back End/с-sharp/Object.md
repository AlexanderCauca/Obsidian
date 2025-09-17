---
tags:
  - cbs/base
  - programming/c-sharp/oop
cssclasses:
  - wide-page
  - minimal-float
banner: "![[PixeLɑnd ◇.gif]]"
banner_y: 0.38667
---



# Объект в C#
> [!blank-container|right-large] 
>  ## Определение
> **Объект** - это экземпляр класса, который создается в памяти во время выполнения программы и содержит:
> - **Состояние** (поля/свойства) - данные объекта
> - **Поведение** (методы) - операции, которые объект может выполнять
> - **Идентичность** - уникальность каждого объекта в памяти
> ## Особенности
> - Создаются с помощью оператора `new`
> - Являются ссылочными типами
> -  Управляются сборщиком мусора
> - Занимают память в куче (heap)
> - Каждый объект имеет уникальный адрес в памяти
>  ## Definition
> **Object** - an instance of a class that is created in memory during program execution and contains:
> - **State** (fields/properties) - object data
> - **Behavior** (methods) - operations the object can perform
> - **Identity** - uniqueness of each object in memory
> ## Characteristics
> - Created using the `new` operator
> - Are reference types
> - Managed by garbage collector
> - Occupy heap memory
> - Each object has unique memory address


## Структура объекта

```csharp
// Класс (шаблон)
class Person
{
    // Поля (состояние)
    public string Name;
    public int Age;
    
    // Метод (поведение)
    public void Introduce()
    {
        Console.WriteLine($"Меня зовут {Name}, мне {Age} лет");
    }
}

// Создание объекта
Person person1 = new Person();
person1.Name = "Иван";
person1.Age = 25;
person1.Introduce();
```
экземпляр - динамический(field переменная своя часть памяти) . Обьект-статический(Metod метод своя часть памяти)

![[экземпляр обьект.png]]
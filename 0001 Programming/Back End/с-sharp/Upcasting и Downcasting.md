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

# <center>Upcasting и Downcasting</center> 

 [!blank-container|right] 
 ## Definition  
 [[Upcasting и Downcasting]] — механизмы преобразования типов в [[OOP|объектно-ориентированном программировании]],  
 которые позволяют работать с объектами через их базовые и производные классы.  

 - **Upcasting** — преобразование объекта дочернего класса в тип его родителя.  
   - Выполняется **неявно** (implicit).  
   - Безопасно, так как любой `Dog` всегда является `Animal`.  

 - **Downcasting** — преобразование объекта родительского типа в дочерний.  
   - Выполняется **явно** (explicit).  
   - Может быть небезопасным, т.к. не каждый `Animal` является `Dog`.  

 ## Characteristics  
 - [[Upcasting|Upcasting]]:  
   - Используется для обобщённого кода.  
   - Позволяет хранить объекты разных типов в одной коллекции базового класса.  
 - [[Downcasting|Downcasting]]:  
   - Используется для доступа к специфическому поведению дочернего класса.  
   - Требует проверки через `is` или `as`.  

 ## Examples  
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
         // 🟢 Upcasting (безопасно)
         Animal animal = new Dog();   // Dog воспринимается как Animal
         animal.Speak();              // Выведет: Dog barks

         // 🔴 Downcasting (нужна проверка)
         if (animal is Dog d) 
         {
             d.Fetch(); // Доступ к методу Dog
         }

         // ⚠️ Опасный Downcasting (если animal не Dog — будет исключение)
         Dog anotherDog = (Dog)animal; 
         anotherDog.Fetch();
     }
 }
 ```

 ## Summary  
 - **Upcasting**: безопасно, используется для полиморфизма.  
 - **Downcasting**: потенциально опасно, нужно использовать проверки.  


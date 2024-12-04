## Polymorphism for Generalization
Polymorphism allows a single interface to be used for different types. In C#, polymorphism is often achieved through inheritance or interfaces, and it allows you to define a common method that can be implemented differently by each derived class.
### Examples in C#
**Before (Without Polymorphism)**:
```csharp
public class Dog
{
    public void MakeSound()
    {
        Console.WriteLine("Woof");
    }
}

public class Cat
{
    public void MakeSound()
    {
        Console.WriteLine("Meow");
    }
}
```
**After (Using Polymorphism)**:
```csharp
public abstract class Animal
{
    public abstract void MakeSound();  // Generalized method
}

public class Dog : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Woof");
    }
}

public class Cat : Animal
{
    public override void MakeSound()
    {
        Console.WriteLine("Meow");
    }
}

public class Zoo
{
    public void AnimalSound(Animal animal)
    {
        animal.MakeSound();  // Uses polymorphism
    }
}
```
**Usage**:
```csharp
Zoo zoo = new Zoo();
zoo.AnimalSound(new Dog());  // Woof
zoo.AnimalSound(new Cat());  // Meow
```
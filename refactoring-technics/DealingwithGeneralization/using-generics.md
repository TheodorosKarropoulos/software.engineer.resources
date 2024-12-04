## Using Generics for Generalization
Generics allow you to create reusable code that works with any type while maintaining type safety. By using generics, you can write methods, classes, or interfaces that work with different types of data without duplicating code.
### Examples in C#
**Before (Without Generics)**:
```csharp
public class StringPrinter
{
    public void PrintString(string value)
    {
        Console.WriteLine(value);
    }
}

public class IntPrinter
{
    public void PrintInt(int value)
    {
        Console.WriteLine(value);
    }
}
```
**After (Using Generics)**:
```csharp
public class Printer<T>
{
    public void Print(T value)
    {
        Console.WriteLine(value);
    }
}
```
**Usage**:
```csharp
var stringPrinter = new Printer<string>();
stringPrinter.Print("Hello, World!");

var intPrinter = new Printer<int>();
intPrinter.Print(123);
```
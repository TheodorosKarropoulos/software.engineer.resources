## Spaghetti code
The term `Spaghetti code` refers to a situation in software development where the structure of the code becomes tangled and difficult to understand, much like a plate of spaghetti. It often arises when a program's code lacks clear organization and structure, making it challenging to maintain, debug, and extend.
Here's a simple example of Spaghetti code in C#
### Spaghetti code example:
```csharp
using System;

class Program
{
    static void Main()
    {
        Console.WriteLine("Welcome to the area calculator!");
        Console.Write("Enter the radius: ");
        double radius = double.Parse(Console.ReadLine());

        double area = 3.14 * Math.Pow(radius, 2);
        Console.WriteLine("The area is: " + area);
    }
}
```
In this example, the code for calculating the area is directly mixed with user input/output, making it harder to understand and maintain.
Now, let's refactor this code to make it more organized.
### Refactored Code:
```csharp
using System;

class Program
{
    static double CalculateArea(double radius)
    {
        return 3.14 * Math.Pow(radius, 2);
    }

    static void PrintResult(double area)
    {
        Console.WriteLine("The area is: " + area);
    }

    static double GetRadiusFromUser()
    {
        Console.Write("Enter the radius: ");
        return double.Parse(Console.ReadLine());
    }

    static void Main()
    {
        Console.WriteLine("Welcome to the area calculator!");

        double radius = GetRadiusFromUser();
        double area = CalculateArea(radius);

        PrintResult(area);
    }
}

```
In the refactored code:

1. The calculation logic is moved to the CalculateArea function.
2. The printing logic is moved to the PrintResult function.
3. User input is handled by the GetRadiusFromUser function.

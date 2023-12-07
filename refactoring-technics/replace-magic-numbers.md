## Replace Magic Numbers with Constants
The `Replace Magic Numbers with Constants` refactoring technique involves replacing hard-coded numerical values (magic numbers) in your code with named constants. This makes the code more readable, maintainable, and less error-prone.
### Simple Explanation:
If you have numbers in your code that are not immediately clear in terms of their purpose, you can replace them with named constants to improve readability and maintainability.
### Example of Code Before Replace Magic Numbers with Constants:
Consider a scenario where a method has a hard-coded number (magic number) that represents a specific condition:
```csharp
public class MathOperations
{
    public int Square(int number)
    {
        // Magic number: 2
        return number * 2;
    }
}
```
### Refactored Code using Replace Magic Numbers with Constants:
In this refactored code, we'll replace the magic number with a named constant:
```csharp
public class MathOperations
{
    // Named constant
    private const int SquareMultiplier = 2;

    public int Square(int number)
    {
        return number * SquareMultiplier;
    }
}
```
In the refactored code, the magic number `2` has been replaced with the named constant `SquareMultiplier`. This makes the code more self-explanatory and provides a single point of control if the multiplier needs to be changed in the future.

This refactoring technique is applicable not only to simple numeric values but also to any constant value used in your code. Using named constants improves code maintainability and reduces the likelihood of introducing bugs caused by changes to hard-coded values.
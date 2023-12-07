## Premature optimization
The `Premature Optimization` anti-pattern refers to the practice of optimizing code for performance before it is necessary. Developers may spend time and effort on making the code run faster or use fewer resources without first identifying whether there is a real performance issue. This can lead to code that is harder to read, understand, and maintain without significant gains in performance.

#### Simple Explanation:
Imagine you're building a piece of software, and you start optimizing the code for speed or resource usage before you even know if there's a performance problem. This is premature optimization.

#### Example of Premature Optimization (Before):

Let's say you have a simple method for calculating the square of a number, and you decide to optimize it by using bitwise left shift for multiplication:

```csharp
public class SquareCalculator
{
    public int CalculateSquare(int number)
    {
        // Premature optimization: using bitwise left shift for multiplication
        return number * number;
    }
}
```

In this example, the use of bitwise left shift (`<<`) is an optimization technique, but it might be considered premature if there's no evidence that the multiplication operation is a performance bottleneck.

#### Refactored Code (After):

To address premature optimization, focus on writing clear and maintainable code first. Optimize only when there's a demonstrated performance issue. Here's a simplified version:

```csharp
public class SquareCalculator
{
    public int CalculateSquare(int number)
    {
        return number * number;
    }
}
```

In the refactored code, the focus is on simplicity and readability. The multiplication operation is straightforward, and optimizations are deferred until there's evidence that performance improvements are necessary. This makes the code more maintainable and easier to understand, especially in the absence of specific performance concerns.
## Accidental complexity
The `Accidental Complexity` anti-pattern refers to complexity in software development that arises not from the inherent complexity of the problem being solved but from poor design choices, unnecessary intricacies, or unintended complications introduced during the development process.
#### Simple Explanation:
Imagine you're solving a problem, but the solution becomes unnecessarily complex due to accidental complications or choices that make the code harder to understand and maintain. This is accidental complexity.
#### Example of Accidental Complexity (Before):
Let's consider a simple scenario where a method for calculating the average of a list introduces unnecessary complexity:
```csharp
public class AverageCalculator
{
    public double CalculateAverage(List<int> numbers)
    {
        int sum = 0;
        int count = 0;

        // Unnecessarily complex loop structure
        foreach (var num in numbers)
        {
            sum += num;
            count++;
        }

        if (count == 0)
        {
            return 0; // Avoid division by zero
        }

        return (double)sum / count;
    }
}
```
In this example, the loop structure for summing up the numbers and counting them introduces unnecessary complexity. It makes the code harder to read and understand without providing any real benefits.

#### Refactored Code (After):
To address accidental complexity, you can simplify the code while maintaining its clarity and correctness:
```csharp
public class AverageCalculator
{
    public double CalculateAverage(List<int> numbers)
    {
        if (numbers.Count == 0)
        {
            return 0; // Avoid division by zero
        }

        return numbers.Average();
    }
}
```
In the refactored code, the LINQ `Average()` method is used to calculate the average directly from the list, eliminating the need for a custom loop structure. This simplifies the code and reduces accidental complexity by leveraging built-in language features and libraries. The intent of the code is clearer, making it easier to maintain and understand.
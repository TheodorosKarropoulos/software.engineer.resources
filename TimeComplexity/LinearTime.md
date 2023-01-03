### Example of an algorithm with time complexity O(n) in C#

This algorithm calculates the sum of the elements in an array by iterating through the array and adding each element to a running total. The time complexity of the algorithm is O(n), because the number of iterations is directly proportional to the size of the array.

```csharp
public int Sum(int[] array)
{
    int sum = 0;
    foreach (int element in array)
    {
        sum += element;
    }
    return sum;
}
```

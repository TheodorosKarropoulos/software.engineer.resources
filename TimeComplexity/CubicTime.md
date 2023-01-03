### Example of an algorithm with time complexity O(n^3) in C#:

This algorithm counts the number of triplets in an array that sum to zero. The time complexity of the algorithm is O(n^3), because the outer loop iterates n times, the middle loop iterates n times on each iteration of the outer loop, and the inner loop iterates n times on each iteration of the middle loop. The result is O(n * n * n) = O(n^3).

```csharp
public int ThreeSum(int[] array)
{
    int count = 0;
    for (int i = 0; i < array.Length - 2; i++)
    {
        for (int j = i + 1; j < array.Length - 1; j++)
        {
            for (int k = j + 1; k < array.Length; k++)
            {
                if (array[i] + array[j] + array[k] == 0)
                {
                    count++;
                }
            }
        }
    }
    return count;
}
```

### Example of an algorithm with time complexity O(n^2) in C#:

This is an implementation of the selection sort algorithm, which sorts an array by iterating through the array and selecting the minimum element on each pass. The time complexity of the algorithm is O(n^2), because the outer loop iterates n times, and the inner loop iterates n times on each iteration of the outer loop. The result is O(n * n) = O(n^2).

```csharp
public void SelectionSort(int[] array)
{
    for (int i = 0; i < array.Length - 1; i++)
    {
        int minIndex = i;
        for (int j = i + 1; j < array.Length; j++)
        {
            if (array[j] < array[minIndex])
            {
                minIndex = j;
            }
        }
        int temp = array[minIndex];
        array[minIndex] = array[i];
        array[i] = temp;
    }
}
```

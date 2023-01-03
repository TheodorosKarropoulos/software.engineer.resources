### Example of an algorithm with time complexity O(2^n) in C#:

This algorithm generates all subsets of an array using recursion. The time complexity of the algorithm is O(2^n), because on each recursive call, the algorithm has two options (to include or exclude the current element), and it makes n recursive calls in total. The result is 2^n.

```csharp
public void GenerateAllSubsets(int[] array, int index, List<int> current)
{
    if (index == array.Length)
    {
        Console.WriteLine(string.Join(", ", current));
    }
    else
    {
        current.Add(array[index]);
        GenerateAllSubsets(array, index + 1, current);
        current.RemoveAt(current.Count - 1);
        GenerateAllSubsets(array, index + 1, current);
    }
}
```

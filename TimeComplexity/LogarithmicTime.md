###  Example of an algorithm with time complexity O(log n) in C#

This algorithm finds the smallest factor of a given integer (other than 1). If the number is even, it returns 2 immediately. Otherwise, it starts from 3 and checks odd numbers up to the square root of the number. If it finds a factor, it returns it; otherwise, it returns the number itself (since the number is prime).

```csharp
public int FindSmallestFactor(int n)
{
    if (n <= 1)
    {
        return -1;
    }

    if (n % 2 == 0)
    {
        return 2;
    }

    int factor = 3;
    int maxFactor = (int) Math.Sqrt(n);

    while (factor <= maxFactor)
    {
        if (n % factor == 0)
        {
            return factor;
        }

        factor += 2;
    }

    return n;
}

```

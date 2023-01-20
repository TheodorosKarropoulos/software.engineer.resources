# Time Complexity

Time complexity is a measure of how long an algorithm takes to run, based on the size of the input. It is typically expressed using big O notation, which describes the upper bound on the number of steps the algorithm takes.

For example, an algorithm with a time complexity of O(n) takes an amount of time that is directly proportional to the size of the input (n). An algorithm with a time complexity of O(1) takes a constant amount of time, regardless of the size of the input.

There are several factors that can affect the time complexity of an algorithm, such as:

- The data structures used to store and access the data
- The number of iterations or recursive calls performed
- The number of operations performed on each element of the input

To optimize the time complexity of an algorithm, you can consider the following strategies:

- Use data structures that provide fast access to elements, such as arrays or hash tables
- Avoid unnecessary iterations or recursive calls
- Use algorithms with a better time complexity for the specific problem you are trying to solve

### List of common time complexities, ordered from best to worst:

1. O(1): [Constant time](ConstantTime.md). The number of operations does not depend on the size of the input.
2. O(log n): [Logarithmic time](LogarithmicTime.md). The number of operations is proportional to the logarithm of the size of the input.
3. O(n): [Linear time](LinearTime.md). The number of operations is proportional to the size of the input.
4. O(n log n): [Linear logarithmic time](LinearLogarithmicTime.md). The number of operations is proportional to the size of the input multiplied by the logarithm of the size of the input.
5. O(n^2): [Quadratic time](QuadraticTime.md). The number of operations is proportional to the square of the size of the input.
6. O(n^3): [Cubic time](CubicTime.md). The number of operations is proportional to the cube of the size of the input.
7. O(2^n): [Exponential time](ExponentialTime.md). The number of operations is proportional to 2 raised to the power of the size of the input.

### List of common operations and their time complexities:
1. Accessing an element in an array or list by index: O(1)
2. Adding or removing an element from the end of an array or list: O(1)
3. Adding or removing an element from the beginning of an array or list: O(n)
4. Sorting an array or list: O(n log n) for most sorting algorithms
5. Searching for an element in an unsorted array or list: O(n)
6. Searching for an element in a sorted array or list using binary search: O(log n)
7. Accessing a value in a hash table: O(1)
8. Inserting or deleting a value in a hash table: O(1)
9. Accessing a value in a balanced binary search tree: O(log n)
10. Inserting or deleting a value in a balanced binary search tree: O(log n)

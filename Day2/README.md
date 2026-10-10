## 📘 Day 2 — Arrays in C#

### What is an Array?

An array is a collection of elements of the same data type stored under a single variable name. Elements are accessed using zero-based indexes in C#.

### Key Characteristics

* Fixed size after creation.
* Stores elements of a specific type.
* Uses zero-based indexing.
* Provides constant-time indexed access, `O(1)`.
* Can be one-dimensional, multidimensional, or jagged.

### Types of Arrays in C#

**1. One-dimensional array**

```csharp
int[] numbers = { 10, 20, 30, 40, 50 };

Console.WriteLine(numbers[0]); // 10
Console.WriteLine(numbers.Length); // 5
```

**2. Two-dimensional array**

```csharp
int[,] matrix =
{
    { 1, 2, 3 },
    { 4, 5, 6 }
};

Console.WriteLine(matrix[1, 2]); // 6
```

**3. Jagged array**

```csharp
int[][] jagged = new int[3][];

jagged[0] = new int[] { 1, 2, 3 };
jagged[1] = new int[] { 4, 5 };
jagged[2] = new int[] { 6, 7, 8, 9 };
```

A jagged array is an array whose elements are themselves arrays. Each inner array can have a different length.

### Example 1 — Traversing an Array

```csharp
int[] numbers = { 10, 20, 30, 40, 50 };

for (int i = 0; i < numbers.Length; i++)
{
    Console.WriteLine(numbers[i]);
}
```

**Time Complexity:** `O(n)`
**Auxiliary Space:** `O(1)`

The loop visits every element once.

### Example 2 — Finding the Maximum Element

```csharp
int[] numbers = { 10, 20, 30, 40, 50 };

int max = numbers[0];

for (int i = 1; i < numbers.Length; i++)
{
    if (numbers[i] > max)
    {
        max = numbers[i];
    }
}

Console.WriteLine($"Maximum: {max}");
```

**Output:**

```text
Maximum: 50
```

**Time Complexity:** `O(n)`
**Auxiliary Space:** `O(1)`

The algorithm checks each remaining element once and keeps track of the largest value.

### Common Array Operations

| Operation                      | Typical Time Complexity |
| ------------------------------ | ----------------------- |
| Access by index                | `O(1)`                  |
| Update by index                | `O(1)`                  |
| Linear search                  | `O(n)`                  |
| Traverse all elements          | `O(n)`                  |
| Find maximum or minimum        | `O(n)`                  |
| Insert or delete in the middle | `O(n)` due to shifting  |

*Note: Inserting or deleting at the end may be O(1) when no shifting is required. These complexities describe typical array operations.*

### Practice Questions

1. Write a C# program to calculate the sum of all array elements.
2. Find the largest element in an integer array.
3. Reverse an array without using another array.
4. Print all elements of a two-dimensional array.
5. Explain why accessing an array element by index takes `O(1)` time.

### What I Learned

* Arrays provide efficient indexed access.
* Traversal and maximum-element searches take linear time.
* Multidimensional and jagged arrays represent data in different structures.
* Choosing the right data structure helps improve algorithm efficiency.


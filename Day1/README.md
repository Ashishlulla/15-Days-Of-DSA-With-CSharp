# 🚀 15 Days of DSA with C#

Welcome to my **15 Days of Data Structures and Algorithms (DSA) with C#** learning series!

This repository documents my daily learning journey to strengthen problem-solving skills, understand algorithm efficiency, and prepare for technical interviews as a .NET developer.

## 🎯 Goals

* Understand core DSA concepts.
* Implement algorithms using C#.
* Analyze time and space complexity.
* Solve practical coding problems.
* Build consistency through daily learning and practice.


## 📘 Day 1 — Big O & Time/Space Complexity

### What is Big O Notation?

Big O notation describes how an algorithm's resource usage grows as the input size increases. It is commonly used to analyze time complexity and auxiliary space complexity.

### Common Time Complexities

| Complexity | Name         | Example                            |
| ---------- | ------------ | ---------------------------------- |
| O(1)       | Constant     | Accessing an array element         |
| O(log n)   | Logarithmic  | Binary search on a sorted array    |
| O(n)       | Linear       | Traversing an array                |
| O(n log n) | Linearithmic | Merge sort                         |
| O(n²)      | Quadratic    | Comparing pairs using nested loops |
| O(2ⁿ)      | Exponential  | Some recursive subset problems     |
| O(n!)      | Factorial    | Generating all permutations        |

### C# Example: O(n)

```csharp
static int SumArray(int[] arr)
{
    int sum = 0;

    for (int i = 0; i < arr.Length; i++)
    {
        sum += arr[i];
    }

    return sum;
}
```

**Explanation:** The loop visits each element once, so the time complexity is O(n). The algorithm uses O(1) auxiliary space because it only maintains a fixed number of variables.

### C# Example: O(n²)

```csharp
static void PrintPairs(int n)
{
    for (int i = 0; i < n; i++)
    {
        for (int j = 0; j < n; j++)
        {
            Console.WriteLine($"{i}, {j}");
        }
    }
}
```

**Explanation:** For every outer-loop iteration, the inner loop runs n times. The total number of iterations is n × n, giving O(n²) time complexity.

### What I Learned

* Big O helps compare algorithm efficiency.
* Input size affects how an algorithm scales.
* Nested loops often indicate quadratic complexity when both loops depend linearly on n.
* Time complexity measures growth in execution work; space complexity measures growth in memory usage.
* Lower asymptotic complexity is often preferable, but actual performance also depends on constants, input sizes, and implementation details.

### Practice Questions

1. What is the time complexity of accessing `arr[0]`?
2. What is the time complexity of traversing an array?
3. What is the time complexity of two nested loops, each running n times?
4. What is the average time complexity of binary search on a sorted array?

**Answers:** O(1), O(n), O(n²), and O(log n), respectively.



## 🤝 Follow the Journey

I'll update this repository throughout the 15-day series with C# implementations, explanations, practice problems, and key takeaways.

If you find this useful, feel free to ⭐ the repository and share your feedback!

**Author:** Ashish Lulla
**Focus:** C# | .NET | Data Structures & Algorithms | Interview Preparation

Let's learn, practice, and improve together! 💪

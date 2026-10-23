# Day 15: Dynamic Programming + Final Review 🚀

## 📌 Overview

Welcome to **Day 15 of 15 Days of DSA with C#!**

Today, I learned the basics of **Dynamic Programming (DP)** and reviewed the concepts covered throughout this learning journey.

Dynamic Programming helps solve problems by breaking them into smaller subproblems and storing their results to avoid unnecessary repeated calculations.

## 🧠 What Is Dynamic Programming?

Dynamic Programming is useful when a problem has:

- **Overlapping Subproblems:** The same smaller problems are solved repeatedly.
- **Optimal Substructure:** A larger problem's solution can be built from solutions to its smaller subproblems.

Two common approaches are:

1. **Memoization (Top-Down):** Use recursion and store results that have already been calculated.
2. **Tabulation (Bottom-Up):** Solve smaller problems first and store their results in a table or array.

## 💻 1. Fibonacci Using Recursion

The Fibonacci sequence starts with `0, 1`, and each subsequent number is the sum of the previous two numbers.

```csharp
static int FibonacciRecursive(int n)
{
    if (n <= 1)
        return n;

    return FibonacciRecursive(n - 1)
         + FibonacciRecursive(n - 2);
}
```

This implementation is simple, but it repeats many calculations.

- **Time Complexity:** O(2ⁿ) as a common upper-bound estimate
- **Auxiliary Space:** O(n) due to recursion depth

## 💻 2. Fibonacci Using Memoization

Memoization stores previously calculated results so they can be reused.

```csharp
static int FibonacciMemo(
    int n,
    Dictionary<int, int> memo)
{
    if (n <= 1)
        return n;

    if (memo.TryGetValue(n, out int result))
        return result;

    result = FibonacciMemo(n - 1, memo)
           + FibonacciMemo(n - 2, memo);

    memo[n] = result;

    return result;
}
```

Usage:

```csharp
var memo = new Dictionary<int, int>();

Console.WriteLine(FibonacciMemo(6, memo));
```

**Output:**

```text
8
```

- **Time Complexity:** O(n), assuming dictionary operations take O(1) on average
- **Auxiliary Space:** O(n), including stored results and recursion

## 💻 3. Fibonacci Using Tabulation

Tabulation solves smaller subproblems first and builds up to the required answer.

```csharp
static int FibonacciTabulation(int n)
{
    if (n <= 1)
        return n;

    int[] dp = new int[n + 1];

    dp[0] = 0;
    dp[1] = 1;

    for (int i = 2; i <= n; i++)
    {
        dp[i] = dp[i - 1] + dp[i - 2];
    }

    return dp[n];
}
```

Usage:

```csharp
Console.WriteLine(FibonacciTabulation(6));
```

**Output:**

```text
8
```

- **Time Complexity:** O(n)
- **Auxiliary Space:** O(n)

## ⚖️ Comparing the Approaches

| Approach | Time Complexity | Auxiliary Space |
|---|---|---|
| Simple Recursion | O(2ⁿ) upper-bound estimate | O(n) |
| Memoization | O(n) average-case | O(n) |
| Tabulation | O(n) | O(n) |

Dynamic Programming can improve performance significantly when a problem contains overlapping subproblems.

## 🎯 Key Takeaways

- Dynamic Programming avoids repeated calculations by storing results.
- Memoization follows a top-down approach.
- Tabulation follows a bottom-up approach.
- Choosing the right approach can improve both execution time and clarity.
- Understanding time and space complexity helps compare solutions.
- Not every problem requires Dynamic Programming; it is most useful when its properties fit the problem.

## 📚 Final Review — 15 Days of DSA with C#

- [x] Day 1 — Big O & Time/Space Complexity
- [x] Day 2 — Arrays
- [x] Day 3 — Strings
- [x] Day 4 — Two Pointers
- [x] Day 5 — Sliding Window
- [x] Day 6 — Hashing & Dictionary
- [x] Day 7 — Stack
- [x] Day 8 — Queue
- [x] Day 9 — Linked List
- [x] Day 10 — Recursion
- [x] Day 11 — Binary Search
- [x] Day 12 — Sorting Algorithms
- [x] Day 13 — Trees & Binary Trees
- [x] Day 14 — Graph Basics
- [x] Day 15 — Dynamic Programming + Final Review



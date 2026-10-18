# Day 10: Recursion in C#

## 📌 What Is Recursion?

**Recursion** is a programming technique in which a method calls itself to solve a problem by breaking it into smaller subproblems.

Every recursive solution should have:

- **Base Case:** Stops the recursion.
- **Recursive Case:** Calls the method with a smaller or simpler input.

Without a suitable base case, recursion can continue until a stack overflow occurs.

## 💻 Example 1: Factorial Using Recursion

The factorial of a positive integer is the product of all positive integers up to that number.

For example:

`5! = 5 × 4 × 3 × 2 × 1 = 120`

```csharp
static int Factorial(int n)
{
    if (n < 0)
    {
        throw new ArgumentOutOfRangeException(nameof(n));
    }

    if (n <= 1)
    {
        return 1;
    }

    return n * Factorial(n - 1);
}

Console.WriteLine(Factorial(5));
```

**Output:**

```text
120
```

**Time Complexity:** O(n)  
**Auxiliary Space:** O(n) due to recursive calls.

## 💻 Example 2: Sum of Numbers

Calculate the sum of integers from 1 to `n`.

```csharp
static int Sum(int n)
{
    if (n <= 0)
    {
        return 0;
    }

    return n + Sum(n - 1);
}

Console.WriteLine(Sum(5));
```

**Output:**

```text
15
```

**Explanation:**

`Sum(5)` becomes `5 + Sum(4)`, then `4 + Sum(3)`, continuing until the base case returns `0`.

**Time Complexity:** O(n)  
**Auxiliary Space:** O(n)

## 💻 Example 3: Fibonacci Using Recursion

The Fibonacci sequence starts with `0, 1`, and each subsequent number is the sum of the previous two numbers.

```csharp
static int Fibonacci(int n)
{
    if (n < 0)
    {
        throw new ArgumentOutOfRangeException(nameof(n));
    }

    if (n <= 1)
    {
        return n;
    }

    return Fibonacci(n - 1) + Fibonacci(n - 2);
}

Console.WriteLine(Fibonacci(6));
```

**Output:**

```text
8
```

Here, `Fibonacci(6)` returns the seventh value when counting from index `0`.

**Time Complexity:** O(2ⁿ) as a simple upper bound  
**Auxiliary Space:** O(n) for the maximum recursion depth.

*Note: This straightforward recursive solution repeats calculations. Memoization or an iterative approach can improve its efficiency.*

## 🔑 How Recursion Works

For `Factorial(3)`:

```text
Factorial(3)
    3 × Factorial(2)
        2 × Factorial(1)
            1  ← Base case
        Returns 2
    Returns 6
```

The calls build up until the base case is reached, then return their results.

## ⏱️ Recursion vs Iteration

| Feature | Recursion | Iteration |
|---|---|---|
| Approach | Method calls itself | Uses loops |
| Stopping condition | Base case | Loop condition |
| Memory | Uses call stack | Often uses less auxiliary memory |
| Readability | Natural for some problems | Often simpler for repetitive tasks |
| Risk | Stack overflow for deep recursion | Infinite loop if condition is incorrect |

## 🧠 What I Learned

- What recursion means.
- Why a base case is necessary.
- How to calculate factorials recursively.
- How to solve a sum problem using recursion.
- Why simple recursive Fibonacci is inefficient.

## 🏋️ Practice Questions

1. Print numbers from `n` to `1` using recursion.
2. Calculate the sum of digits of a number.
3. Reverse a string using recursion.
4. Find the power of a number recursively.
5. Calculate Fibonacci numbers using memoization.

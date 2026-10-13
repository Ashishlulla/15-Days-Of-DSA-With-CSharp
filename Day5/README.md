# Day 5: Sliding Window in C#

## 📌 What is the Sliding Window Technique?

Sliding Window is a problem-solving technique used to process a continuous range of elements in an array or string.

Instead of recalculating everything for every new range, we update the window by adding new elements and removing elements that are no longer needed.

It is commonly used for subarray and substring problems.

## 🔑 Types of Sliding Window

**1. Fixed-size window**

The window always contains a fixed number of elements.

Examples:
- Maximum sum of a subarray of size `k`.
- Average of every subarray of size `k`.

**2. Variable-size window**

The window expands or shrinks depending on a condition.

Examples:
- Longest substring without repeating characters.
- Smallest subarray with a sum greater than or equal to a target, when the array contains positive numbers.

## 💻 Example 1: Maximum Sum of a Subarray of Size K

Given an array and a window size `k`, find the maximum sum of any contiguous subarray of size `k`.

```csharp
int[] numbers = { 2, 1, 5, 1, 3, 2 };
int k = 3;

if (k <= 0 || k > numbers.Length)
{
    throw new ArgumentOutOfRangeException(nameof(k));
}

int windowSum = 0;

// Calculate the first window
for (int i = 0; i < k; i++)
{
    windowSum += numbers[i];
}

int maxSum = windowSum;

// Slide the window
for (int i = k; i < numbers.Length; i++)
{
    windowSum += numbers[i];
    windowSum -= numbers[i - k];

    maxSum = Math.Max(maxSum, windowSum);
}

Console.WriteLine(maxSum);
```

**Output:**
```text
9
```

**Explanation:**

The subarray `[5, 1, 3]` has the maximum sum of `9`.

Instead of calculating every window from scratch, we add the new element and subtract the element leaving the window.

**Time Complexity:** O(n)  
**Auxiliary Space:** O(1)

## 💻 Example 2: Maximum Sum with a Fixed Window

For the array `{ 1, 4, 2, 10, 3, 1, 0, 20 }` and `k = 3`, the maximum sum is `21`, from the subarray `[1, 0, 20]`.

The sliding window technique avoids repeatedly summing all three elements for each window.

## 💻 Example 3: Smallest Subarray with Sum at Least Target

This example assumes all array elements are positive.

```csharp
static int MinSubArrayLength(int[] numbers, int target)
{
    int left = 0;
    int sum = 0;
    int minLength = int.MaxValue;

    for (int right = 0; right < numbers.Length; right++)
    {
        sum += numbers[right];

        while (sum >= target)
        {
            minLength = Math.Min(minLength, right - left + 1);
            sum -= numbers[left];
            left++;
        }
    }

    return minLength == int.MaxValue ? 0 : minLength;
}
```

**Usage:**

```csharp
int[] numbers = { 2, 3, 1, 2, 4, 3 };

Console.WriteLine(MinSubArrayLength(numbers, 7));
```

**Output:**
```text
2
```

The smallest qualifying subarray is `[4, 3]`.

**Time Complexity:** O(n)  
**Auxiliary Space:** O(1)

**Important:** This shrinking-window approach relies on positive elements. With negative numbers, the window sum may not behave predictably, so a different algorithm may be needed.

## ⏱️ Sliding Window vs. Brute Force

| Approach | Typical Time Complexity |
|---|---|
| Recalculate every fixed-size window | O(n × k) |
| Sliding window for fixed-size sums | O(n) |
| Variable-size sliding window with positive values | O(n) |

The sliding window technique is useful when a problem involves contiguous elements and the window can be updated efficiently.

## 🧠 What I Learned

- What the sliding window technique is.
- The difference between fixed-size and variable-size windows.
- How to update a window without recalculating its entire sum.
- How sliding windows can reduce repeated work.
- Why problem constraints matter when choosing an algorithm.

## 🏋️ Practice Questions

1. Find the maximum sum of a subarray of size `k`.
2. Calculate the average of every window of size `k`.
3. Find the smallest subarray with a sum greater than or equal to a target, assuming positive numbers.
4. Find the longest substring without repeating characters.
5. Find the maximum number of consecutive ones after allowing at most one zero to be flipped.


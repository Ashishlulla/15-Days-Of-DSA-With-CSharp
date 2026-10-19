# Day 11: Binary Search 🔍

## 📌 Overview

Today, I learned about **Binary Search**, an efficient searching algorithm used to find an element in a **sorted array**.

Instead of checking every element one by one, Binary Search repeatedly divides the search range into half.

## 🧠 How Binary Search Works

1. Set `left` to the first index and `right` to the last index.
2. Calculate the middle index.
3. If the middle element matches the target, return its index.
4. If the target is smaller, search the left half.
5. If the target is larger, search the right half.
6. Repeat until the element is found or the search range becomes empty.

**Important:** Binary Search requires the array to be sorted.

## 💻 C# Implementation

```csharp
using System;

class Program
{
    static int BinarySearch(int[] numbers, int target)
    {
        int left = 0;
        int right = numbers.Length - 1;

        while (left <= right)
        {
            int mid = left + (right - left) / 2;

            if (numbers[mid] == target)
            {
                return mid;
            }
            else if (numbers[mid] < target)
            {
                left = mid + 1;
            }
            else
            {
                right = mid - 1;
            }
        }

        return -1;
    }

    static void Main()
    {
        int[] numbers = { 10, 20, 30, 40, 50, 60 };
        int target = 40;

        int result = BinarySearch(numbers, target);

        if (result != -1)
        {
            Console.WriteLine($"Element found at index: {result}");
        }
        else
        {
            Console.WriteLine("Element not found.");
        }
    }
}
```

### Output

```text
Element found at index: 3
```

## ⏱️ Time and Space Complexity

| Case | Complexity |
|---|---|
| Best Case | O(1) |
| Average Case | O(log n) |
| Worst Case | O(log n) |
| Auxiliary Space | O(1) |

The iterative implementation uses constant extra space. Each step eliminates approximately half of the remaining search range.

## ⚖️ Linear Search vs Binary Search

| Feature | Linear Search | Binary Search |
|---|---|---|
| Data requirement | Sorted or unsorted | Must be sorted |
| Worst-case time | O(n) | O(log n) |
| Approach | Check one by one | Divide search range in half |

## 🎯 Key Takeaways

- Binary Search works on sorted data.
- It repeatedly halves the search range.
- It is generally much faster than Linear Search for large sorted arrays.
- The `left`, `right`, and `mid` variables help manage the search range.
- Returning `-1` indicates that the target was not found.

## 🏋️ Practice Problems

1. Implement Binary Search to find a target in a sorted array.
2. Return `-1` when the target does not exist.
3. Find the first occurrence of a duplicate element in a sorted array.
4. Compare the number of steps taken by Linear Search and Binary Search.

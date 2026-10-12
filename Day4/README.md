# Day 4: Two Pointers in C#

## 📌 What is the Two-Pointer Technique?

Two Pointers is a problem-solving technique that uses two indexes to process data efficiently.

The pointers can move toward each other or in the same direction, depending on the problem.

This technique is commonly used with arrays and strings.

## 🔑 When to Use Two Pointers

- Finding a pair with a given sum in a sorted array.
- Removing duplicates from a sorted array.
- Checking whether a string is a palindrome.
- Reversing an array.
- Comparing elements from opposite ends.

## 💻 Example 1: Find a Pair with a Given Sum

Given a sorted array, check whether two elements add up to a target sum.

```csharp
int[] numbers = { 1, 2, 4, 6, 8, 10 };
int target = 12;

int left = 0;
int right = numbers.Length - 1;

while (left < right)
{
    int sum = numbers[left] + numbers[right];

    if (sum == target)
    {
        Console.WriteLine(
            $"{numbers[left]} + {numbers[right]} = {target}");
        break;
    }
    else if (sum < target)
    {
        left++;
    }
    else
    {
        right--;
    }
}
```

**Output:**
```text
2 + 10 = 12
```

**Time Complexity:** O(n)  
**Auxiliary Space:** O(1)

**Explanation:** Since the array is sorted, we move the left pointer forward when the sum is too small and the right pointer backward when the sum is too large.

## 💻 Example 2: Remove Duplicates from a Sorted Array

Use one pointer to track the position of the next unique element and another to scan the array.

```csharp
int[] numbers = { 1, 1, 2, 2, 3, 4, 4 };

if (numbers.Length > 0)
{
    int uniqueIndex = 0;

    for (int i = 1; i < numbers.Length; i++)
    {
        if (numbers[i] != numbers[uniqueIndex])
        {
            uniqueIndex++;
            numbers[uniqueIndex] = numbers[i];
        }
    }

    for (int i = 0; i <= uniqueIndex; i++)
    {
        Console.Write(numbers[i] + " ");
    }
}
```

**Output:**
```text
1 2 3 4
```

**Time Complexity:** O(n)  
**Auxiliary Space:** O(1)

**Explanation:** The algorithm modifies the original array in place. The unique values occupy the beginning of the array; elements beyond the last unique index should be ignored.

## 💻 Example 3: Check for a Palindrome

A palindrome reads the same forward and backward.

```csharp
static bool IsPalindrome(string text)
{
    int left = 0;
    int right = text.Length - 1;

    while (left < right)
    {
        if (text[left] != text[right])
        {
            return false;
        }

        left++;
        right--;
    }

    return true;
}
```

**Usage:**

```csharp
Console.WriteLine(IsPalindrome("madam")); // True
Console.WriteLine(IsPalindrome("hello")); // False
```

**Time Complexity:** O(n)  
**Auxiliary Space:** O(1)

## 🧠 Types of Two-Pointer Approaches

| Approach | Description | Example |
|---|---|---|
| Opposite Direction | Pointers start at opposite ends and move inward | Pair sum, palindrome |
| Same Direction | Both pointers move forward | Removing duplicates |
| Fast and Slow | Pointers move at different speeds | Detecting a cycle in a linked list |

## ⏱️ Key Takeaways

- Two pointers can reduce unnecessary comparisons.
- Sorted arrays are especially useful for pair-sum problems.
- Many two-pointer solutions run in O(n) time.
- In-place techniques can avoid allocating an additional array.
- Always check the conditions under which each pointer should move.

## 🏋️ Practice Questions

1. Reverse an array using two pointers.
2. Find a pair with a target sum in a sorted array.
3. Remove duplicates from a sorted array.
4. Check whether a string is a palindrome.
5. Move all zeros to the end of an array.


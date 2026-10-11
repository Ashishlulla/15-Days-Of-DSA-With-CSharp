# Day 3: Strings in C#

## 📌 What is a String?

A string is a sequence of characters used to store text in C#.

```csharp
string name = "Ashish";
Console.WriteLine(name);
```

**Output:**
```text
Ashish
```

## 🔑 Key Concepts

- Strings are immutable, meaning their contents cannot be changed after creation.
- String indexing starts from `0`.
- The `Length` property returns the number of characters.
- C# provides built-in methods for common string operations.

## 🛠️ Common String Operations

| Operation | Example |
|---|---|
| Get length | `text.Length` |
| Access character | `text[0]` |
| Convert to lowercase | `text.ToLower()` |
| Convert to uppercase | `text.ToUpper()` |
| Check substring | `text.Contains("Hello")` |
| Find character | `text.IndexOf('a')` |
| Replace text | `text.Replace("old", "new")` |
| Split string | `text.Split(' ')` |
| Extract substring | `text.Substring(0, 3)` |

## 💻 Example 1: String Traversal

```csharp
string text = "Hello";

for (int i = 0; i < text.Length; i++)
{
    Console.WriteLine(text[i]);
}
```

**Output:**
```text
H
e
l
l
o
```

**Time Complexity:** O(n)  
**Auxiliary Space:** O(1)

## 💻 Example 2: Reverse a String

```csharp
string text = "Hello";
char[] characters = text.ToCharArray();

Array.Reverse(characters);

string reversed = new string(characters);

Console.WriteLine(reversed);
```

**Output:**
```text
olleH
```

**Time Complexity:** O(n)  
**Auxiliary Space:** O(n)

## 💻 Example 3: Check for a Palindrome

A palindrome reads the same forward and backward.

Examples: `madam`, `level`, `racecar`

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

This approach compares characters from both ends using two pointers.

## ⏱️ Common Time Complexities

| Operation | Typical Complexity |
|---|---|
| Access character by index | O(1) |
| Traverse a string | O(n) |
| Compare two strings | O(n) |
| Reverse a string | O(n) |
| Check palindrome | O(n) |

*Note: String comparison depends on the number of characters compared. Creating new strings can require additional memory.*

## 🧠 What I Learned

- How strings work in C#.
- String immutability and indexing.
- Common built-in string methods.
- Traversing and reversing strings.
- Checking palindromes using two pointers.

## 🏋️ Practice Questions

1. Reverse a string without using `Array.Reverse()`.
2. Count the vowels in a string.
3. Check whether a string is a palindrome.
4. Remove all spaces from a string.
5. Find the first non-repeating character in a string.




# Day 7: Stack in C#

## 📌 What Is a Stack?

A **Stack** is a linear data structure that follows the **LIFO** principle:

**Last In, First Out** — the last element added is the first one removed.

Think of a stack of plates: you add and remove plates from the top.

## 🔑 Basic Stack Operations

| Operation | Description |
|---|---|
| `Push()` | Adds an element to the top |
| `Pop()` | Removes and returns the top element |
| `Peek()` | Returns the top element without removing it |
| `Count` | Returns the number of elements |
| `Clear()` | Removes all elements |

## 💻 Example 1: Basic Stack Operations

C# provides the built-in `Stack<T>` collection.

```csharp
using System;
using System.Collections.Generic;

Stack<int> stack = new Stack<int>();

stack.Push(10);
stack.Push(20);
stack.Push(30);

Console.WriteLine(stack.Peek());  // 30
Console.WriteLine(stack.Pop());   // 30
Console.WriteLine(stack.Peek());  // 20
Console.WriteLine(stack.Count);   // 2
```

**Output:**

```text
30
30
20
2
```

**Explanation:** The last element pushed was `30`, so it is the first element returned by `Peek()` and `Pop()`.

## 💻 Example 2: Reverse a String Using a Stack

```csharp
using System;
using System.Collections.Generic;

string text = "HELLO";
Stack<char> stack = new Stack<char>();

foreach (char character in text)
{
    stack.Push(character);
}

while (stack.Count > 0)
{
    Console.Write(stack.Pop());
}
```

**Output:**

```text
OLLEH
```

**Time Complexity:** O(n)  
**Auxiliary Space:** O(n)

**Explanation:** Characters are pushed in their original order and popped in reverse order.

## 💻 Example 3: Check Balanced Parentheses

A stack can help determine whether brackets are properly matched and nested.

```csharp
using System;
using System.Collections.Generic;

static bool IsBalanced(string expression)
{
    Stack<char> stack = new Stack<char>();

    foreach (char character in expression)
    {
        if (character == '(')
        {
            stack.Push(character);
        }
        else if (character == ')')
        {
            if (stack.Count == 0)
            {
                return false;
            }

            stack.Pop();
        }
    }

    return stack.Count == 0;
}

Console.WriteLine(IsBalanced("(a+b)"));  // True
Console.WriteLine(IsBalanced("(a+b"));   // False
Console.WriteLine(IsBalanced("a+b)"));   // False
```

**Time Complexity:** O(n)  
**Auxiliary Space:** O(n)

**Note:** This example checks parentheses `()` only. Handling `[]` and `{}` requires checking matching bracket types as well.

## ⏱️ Time Complexity

| Operation | Time Complexity |
|---|---|
| `Push()` | O(1) amortized |
| `Pop()` | O(1) |
| `Peek()` | O(1) |
| `Count` | O(1) |
| Search for an element | O(n) |

## 🧠 What I Learned

- The LIFO principle.
- Basic stack operations in C#.
- How to reverse a string using a stack.
- How stacks help solve bracket-matching problems.
- Common stack operation complexities.

## 🏋️ Practice Questions

1. Reverse a string using a stack.
2. Check whether parentheses are balanced.
3. Implement a stack using an array.
4. Find the next greater element for each element in an array.
5. Design a stack that supports retrieving the minimum element efficiently.



# Day 8: Queue in C#

## 📌 What Is a Queue?

A **Queue** is a linear data structure that follows the **FIFO** principle:

**First In, First Out** — the first element added is the first one removed.

Think of a queue at a ticket counter: the person who arrives first is served first.

## 🔑 Basic Queue Operations

| Operation | Description |
|---|---|
| `Enqueue()` | Adds an element to the end |
| `Dequeue()` | Removes and returns the front element |
| `Peek()` | Returns the front element without removing it |
| `Count` | Returns the number of elements |
| `Clear()` | Removes all elements |

## 💻 Example 1: Basic Queue Operations

C# provides the built-in `Queue<T>` collection.

```csharp
using System;
using System.Collections.Generic;

Queue<int> queue = new Queue<int>();

queue.Enqueue(10);
queue.Enqueue(20);
queue.Enqueue(30);

Console.WriteLine(queue.Peek());     // 10
Console.WriteLine(queue.Dequeue());  // 10
Console.WriteLine(queue.Peek());     // 20
Console.WriteLine(queue.Count);      // 2
```

**Output:**

```text
10
10
20
2
```

**Explanation:** The first element added was `10`, so it is the first element returned by `Peek()` and `Dequeue()`.

## 💻 Example 2: Process Tasks in Order

```csharp
using System;
using System.Collections.Generic;

Queue<string> tasks = new Queue<string>();

tasks.Enqueue("Send Email");
tasks.Enqueue("Generate Report");
tasks.Enqueue("Backup Data");

while (tasks.Count > 0)
{
    string task = tasks.Dequeue();
    Console.WriteLine($"Processing: {task}");
}
```

**Output:**

```text
Processing: Send Email
Processing: Generate Report
Processing: Backup Data
```

**Time Complexity:** O(n) for processing all tasks  
**Auxiliary Space:** O(n) for storing the queue

**Explanation:** Tasks are processed in the same order in which they were added.

## 💻 Example 3: Reverse a Queue

A stack can help reverse the order of elements in a queue.

```csharp
using System;
using System.Collections.Generic;

Queue<int> queue = new Queue<int>();

queue.Enqueue(1);
queue.Enqueue(2);
queue.Enqueue(3);

Stack<int> stack = new Stack<int>();

while (queue.Count > 0)
{
    stack.Push(queue.Dequeue());
}

while (stack.Count > 0)
{
    queue.Enqueue(stack.Pop());
}

Console.WriteLine(string.Join(", ", queue));
```

**Output:**

```text
3, 2, 1
```

**Time Complexity:** O(n)  
**Auxiliary Space:** O(n)

## ⏱️ Time Complexity

| Operation | Typical Time Complexity |
|---|---|
| `Enqueue()` | O(1) amortized |
| `Dequeue()` | O(1) |
| `Peek()` | O(1) |
| `Count` | O(1) |
| Search for an element | O(n) |

## 🧠 What I Learned

- The FIFO principle.
- Basic queue operations in C#.
- How queues process tasks in order.
- How a stack can be used to reverse a queue.
- Where queues are useful in real-world applications.

## 🏋️ Practice Questions

1. Implement a queue using an array.
2. Reverse a queue using a stack.
3. Generate binary numbers from 1 to n using a queue.
4. Implement a circular queue.
5. Explain the difference between a stack and a queue.

## 📊 Stack vs Queue

| Feature | Stack | Queue |
|---|---|---|
| Principle | LIFO | FIFO |
| Insert operation | `Push()` | `Enqueue()` |
| Remove operation | `Pop()` | `Dequeue()` |
| Removal happens at | Top | Front |
| Example | Undo operation | Task scheduling |


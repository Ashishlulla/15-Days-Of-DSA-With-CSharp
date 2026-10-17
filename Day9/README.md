# Day 9: Linked List in C#

## 📌 What Is a Linked List?

A **Linked List** is a linear data structure made up of nodes.

Each node stores:
- **Data:** The value stored in the node.
- **Next:** A reference to the next node.

Unlike arrays, linked-list nodes do not need to be stored in contiguous memory locations.

## 🔑 Types of Linked Lists

1. **Singly Linked List:** Each node points to the next node.
2. **Doubly Linked List:** Each node points to both the previous and next nodes.
3. **Circular Linked List:** The last node points back to the first node.

## 💻 Example 1: Create a Singly Linked List

```csharp
class Node
{
    public int Data;
    public Node? Next;

    public Node(int data)
    {
        Data = data;
        Next = null;
    }
}

Node first = new Node(10);
Node second = new Node(20);
Node third = new Node(30);

first.Next = second;
second.Next = third;

Node? current = first;

while (current != null)
{
    Console.Write(current.Data + " ");
    current = current.Next;
}
```

**Output:**

```text
10 20 30
```

**Explanation:** Each node stores a value and a reference to the next node. Traversal starts at the first node and continues until `Next` is `null`.

## 💻 Example 2: Insert a Node at the Beginning

```csharp
static Node InsertAtBeginning(Node? head, int data)
{
    Node newNode = new Node(data);
    newNode.Next = head;

    return newNode;
}
```

**Usage:**

```csharp
Node? head = new Node(20);
head = InsertAtBeginning(head, 10);
```

The new node becomes the head of the linked list.

**Time Complexity:** O(1)

## 💻 Example 3: Search for an Element

```csharp
static bool Search(Node? head, int target)
{
    Node? current = head;

    while (current != null)
    {
        if (current.Data == target)
        {
            return true;
        }

        current = current.Next;
    }

    return false;
}
```

**Usage:**

```csharp
Console.WriteLine(Search(head, 10)); // True
Console.WriteLine(Search(head, 50)); // False
```

**Time Complexity:** O(n)  
**Auxiliary Space:** O(1)

## 💻 Example 4: Delete the First Node with a Given Value

```csharp
static Node? Delete(Node? head, int target)
{
    if (head == null)
    {
        return null;
    }

    if (head.Data == target)
    {
        return head.Next;
    }

    Node current = head;

    while (current.Next != null)
    {
        if (current.Next.Data == target)
        {
            current.Next = current.Next.Next;
            break;
        }

        current = current.Next;
    }

    return head;
}
```

**Explanation:** If the target is at the head, the head moves to the next node. Otherwise, the previous node is linked directly to the node after the target.

**Time Complexity:** O(n)  
**Auxiliary Space:** O(1)

## ⏱️ Common Linked List Operations

| Operation | Singly Linked List |
|---|---|
| Access by position | O(n) |
| Search by value | O(n) |
| Insert at head | O(1) |
| Delete at head | O(1) |
| Insert after a known node | O(1) |
| Delete after a known previous node | O(1) |

*Note: Finding the node or its previous node may require O(n) traversal.*

## ⚖️ Array vs Linked List

| Feature | Array | Linked List |
|---|---|---|
| Indexed access | O(1) | O(n) |
| Search | O(n) | O(n) |
| Insert at beginning | O(n) | O(1) when updating the head |
| Memory layout | Contiguous elements | Nodes connected by references |
| Extra memory | Usually low overhead | References stored with nodes |

## 🧠 What I Learned

- How nodes connect to form a linked list.
- How to traverse a singly linked list.
- How to insert and delete nodes.
- How linked lists differ from arrays.
- The time complexity of common linked-list operations.

## 🏋️ Practice Questions

1. Reverse a singly linked list.
2. Find the middle node of a linked list.
3. Detect a cycle in a linked list.
4. Find the nth node from the end.
5. Merge two sorted linked lists.

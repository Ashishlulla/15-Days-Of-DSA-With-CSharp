# Day 13: Trees & Binary Trees 🌳

## 📌 Overview

Today, I learned about **Trees and Binary Trees**, which are important data structures used to organize data hierarchically.

A tree consists of nodes connected by edges. A binary tree is a tree in which each node can have at most two children: a left child and a right child.

## 🧠 Important Tree Concepts

- **Root:** The topmost node of a tree.
- **Parent:** A node that has one or more children.
- **Child:** A node connected below another node.
- **Leaf:** A node with no children.
- **Edge:** A connection between two nodes.
- **Height:** The number of edges in the longest downward path from a node to a leaf.

## 🌳 Example of a Binary Tree

```text
        10
       /  \
      5    20
     / \
    3   7
```

- Root: `10`
- Children of `10`: `5` and `20`
- Leaf nodes: `3`, `7`, and `20`

## 💻 1. Creating a Binary Tree in C#

```csharp
using System;

class Node
{
    public int Data;
    public Node? Left;
    public Node? Right;

    public Node(int data)
    {
        Data = data;
    }
}

class Program
{
    static void Main()
    {
        Node root = new Node(10);

        root.Left = new Node(5);
        root.Right = new Node(20);

        root.Left.Left = new Node(3);
        root.Left.Right = new Node(7);

        Console.WriteLine(root.Data);
    }
}
```

**Output:**

```text
10
```

## 🔄 2. Tree Traversal

Tree traversal means visiting every node in a particular order.

### Inorder Traversal (Left → Root → Right)

```csharp
static void Inorder(Node? root)
{
    if (root == null)
        return;

    Inorder(root.Left);
    Console.Write(root.Data + " ");
    Inorder(root.Right);
}
```

**Output:**

```text
3 5 7 10 20
```

### Preorder Traversal (Root → Left → Right)

```csharp
static void Preorder(Node? root)
{
    if (root == null)
        return;

    Console.Write(root.Data + " ");
    Preorder(root.Left);
    Preorder(root.Right);
}
```

**Output:**

```text
10 5 3 7 20
```

### Postorder Traversal (Left → Right → Root)

```csharp
static void Postorder(Node? root)
{
    if (root == null)
        return;

    Postorder(root.Left);
    Postorder(root.Right);
    Console.Write(root.Data + " ");
}
```

**Output:**

```text
3 7 5 20 10
```

## ⏱️ Time and Space Complexity

For a binary tree containing `n` nodes:

| Operation | Time Complexity |
|---|---|
| Visit all nodes using traversal | O(n) |
| Search for a value in a general binary tree | O(n) |
| Insert a node (depends on the approach) | Depends on the tree |

**Auxiliary space for recursive traversal:** O(h), where `h` is the tree height due to the recursion call stack.

For a balanced tree, the height is typically O(log n). For a completely skewed tree, it can be O(n).

## ⚖️ Tree vs Binary Tree

| Feature | General Tree | Binary Tree |
|---|---|---|
| Children per node | Can vary | At most two |
| Child positions | Depends on the tree | Left and right |
| Example use | Hierarchical data | Searching and hierarchical processing |

## 🎯 Key Takeaways

- Trees represent hierarchical relationships.
- A binary tree node has at most two children.
- Traversal helps visit every node in a specific order.
- Inorder, Preorder, and Postorder use different visiting sequences.
- Recursive methods are a common way to implement tree traversal.
- A general binary tree is not automatically a Binary Search Tree (BST).

## 🏋️ Practice Questions

1. Create a binary tree containing five nodes.
2. Implement Inorder, Preorder, and Postorder traversal.
3. Count the total number of nodes in a binary tree.
4. Find the maximum value in a binary tree.
5. Calculate the height of a binary tree.


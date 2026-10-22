# Day 14: Graph Basics 🕸️

## 📌 Overview

Today, I learned about **Graphs**, a data structure used to represent connections and relationships between objects.

A graph consists of:
- **Vertices (Nodes):** The objects or points in a graph.
- **Edges:** The connections between vertices.

Graphs are widely used in maps, social networks, computer networks, and recommendation systems.

## 🧠 Types of Graphs

1. **Undirected Graph:** Edges have no direction. If A is connected to B, the connection works both ways.
2. **Directed Graph:** Edges have a direction, such as A → B.
3. **Weighted Graph:** Edges have values such as distance, time, or cost.
4. **Unweighted Graph:** Edges represent connections without an assigned weight.

## 🔗 Example of a Graph

```text
    A ----- B
    |       |
    |       |
    C ----- D
```

In this undirected graph, the vertices are A, B, C, and D. The edges represent the connections between them.

## 💻 1. Representing a Graph Using an Adjacency List in C#

An adjacency list stores the neighbors of each vertex.

```csharp
using System;
using System.Collections.Generic;

class Program
{
    static void Main()
    {
        Dictionary<string, List<string>> graph = new()
        {
            ["A"] = new List<string> { "B", "C" },
            ["B"] = new List<string> { "A", "D" },
            ["C"] = new List<string> { "A", "D" },
            ["D"] = new List<string> { "B", "C" }
        };

        foreach (var vertex in graph)
        {
            Console.WriteLine(
                $"{vertex.Key}: {string.Join(", ", vertex.Value)}");
        }
    }
}
```

### Output

```text
A: B, C
B: A, D
C: A, D
D: B, C
```

Because this is an undirected graph, each connection is listed in both vertices' neighbor lists.

## 🔍 2. Breadth-First Search (BFS)

BFS visits graph nodes level by level and uses a queue to keep track of which node to visit next.

```csharp
static void BFS(
    Dictionary<string, List<string>> graph,
    string start)
{
    Queue<string> queue = new();
    HashSet<string> visited = new();

    queue.Enqueue(start);
    visited.Add(start);

    while (queue.Count > 0)
    {
        string current = queue.Dequeue();
        Console.Write(current + " ");

        foreach (string neighbor in graph[current])
        {
            if (visited.Add(neighbor))
            {
                queue.Enqueue(neighbor);
            }
        }
    }
}
```

Call it using:

```csharp
BFS(graph, "A");
```

### Output

```text
A B C D
```

This output assumes the adjacency list is defined in the order shown above.

## 🔍 3. Depth-First Search (DFS)

DFS explores one path as deeply as possible before returning to explore other paths. Recursion can be used to implement it.

```csharp
static void DFS(
    Dictionary<string, List<string>> graph,
    string current,
    HashSet<string> visited)
{
    if (!visited.Add(current))
        return;

    Console.Write(current + " ");

    foreach (string neighbor in graph[current])
    {
        DFS(graph, neighbor, visited);
    }
}
```

Call it using:

```csharp
DFS(graph, "A", new HashSet<string>());
```

### Output

```text
A B D C
```

The traversal order depends on the order of neighbors in the adjacency lists.

## ⏱️ Time and Space Complexity

Let `V` represent the number of vertices and `E` the number of edges.

| Operation | Complexity |
|---|---|
| Store graph using an adjacency list | O(V + E) space |
| BFS traversal | O(V + E) |
| DFS traversal | O(V + E) |
| Check whether an edge exists in a basic adjacency list | O(degree of vertex) |

These traversal complexities assume an adjacency-list representation and that each vertex and edge is processed a constant number of times.

## ⚖️ BFS vs DFS

| Feature | BFS | DFS |
|---|---|---|
| Approach | Level by level | Explore deeply first |
| Common implementation | Queue | Recursion or stack |
| Useful for | Shortest path in an unweighted graph | Exploring paths and connectivity |
| Traversal order | Depends on neighbor order | Depends on neighbor order |

## 🌍 Real-World Applications

- Maps and route planning
- Social networks and friend connections
- Computer network routing
- Website link analysis
- Recommendation systems

## 🎯 Key Takeaways

- Graphs represent relationships between nodes.
- Vertices are connected using edges.
- Graphs can be directed, undirected, weighted, or unweighted.
- An adjacency list stores each vertex's neighbors.
- BFS uses a queue, while DFS can use recursion or a stack.
- A visited set helps prevent repeatedly processing nodes and handles cycles safely.

## 🏋️ Practice Questions

1. Create an undirected graph with five vertices.
2. Convert the graph into an adjacency list.
3. Implement BFS starting from a given vertex.
4. Implement DFS using recursion.
5. Modify the graph to represent directed connections.
6. Find whether a path exists between two vertices.

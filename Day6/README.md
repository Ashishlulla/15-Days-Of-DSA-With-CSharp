# Day 6: Hashing & Dictionary in C#

## 📌 What Is Hashing?

Hashing uses a hash function to map a key to a location or hash code so data can be stored and retrieved efficiently.

In C#, `Dictionary<TKey, TValue>` uses hashing to store key-value pairs and supports efficient lookups by key.

## 🔑 What Is a Dictionary?

A dictionary stores data as **key-value pairs**.

Each key must be unique, while values can be duplicated.

```csharp
Dictionary<string, int> ages = new Dictionary<string, int>
{
    { "Ashish", 25 },
    { "Rahul", 28 },
    { "Priya", 24 }
};

Console.WriteLine(ages["Ashish"]);
```

**Output:**
```text
25
```

## 💻 Example 1: Count the Frequency of Elements

Count how many times each number appears in an array.

```csharp
int[] numbers = { 1, 2, 2, 3, 1, 2, 4 };

Dictionary<int, int> frequency = new Dictionary<int, int>();

foreach (int number in numbers)
{
    if (frequency.ContainsKey(number))
    {
        frequency[number]++;
    }
    else
    {
        frequency[number] = 1;
    }
}

foreach (var item in frequency)
{
    Console.WriteLine($"{item.Key}: {item.Value}");
}
```

**Possible output:**
```text
1: 2
2: 3
3: 1
4: 1
```

**Time Complexity:** O(n) average  
**Auxiliary Space:** O(n)

The dictionary stores each distinct number and its frequency. The expected total time is O(n) with typical hash-table performance.

## 💻 Example 2: Using `TryGetValue()`

Use `TryGetValue()` to safely retrieve a value without first checking whether a key exists.

```csharp
Dictionary<string, int> scores = new Dictionary<string, int>
{
    { "Ashish", 90 },
    { "Rahul", 85 }
};

if (scores.TryGetValue("Ashish", out int score))
{
    Console.WriteLine(score);
}
else
{
    Console.WriteLine("Student not found");
}
```

**Output:**
```text
90
```

## 💻 Example 3: Find the First Repeating Number

```csharp
int[] numbers = { 4, 2, 7, 2, 8, 4 };

HashSet<int> seen = new HashSet<int>();

foreach (int number in numbers)
{
    if (!seen.Add(number))
    {
        Console.WriteLine(number);
        break;
    }
}
```

**Output:**
```text
2
```

**Time Complexity:** O(n) average  
**Auxiliary Space:** O(n)

A `HashSet<T>` stores unique values. Its `Add()` method returns `false` when a value already exists, helping identify the first repeated value encountered during traversal.

## ⏱️ Common Dictionary Operations

| Operation | Average Time |
|---|---|
| Add a key-value pair | O(1) |
| Search by key | O(1) |
| Update a value | O(1) |
| Remove by key | O(1) |
| Check whether a key exists | O(1) |

*Note: These are average-case complexities. Some operations can take O(n) in the worst case.*

## 🧠 What I Learned

- How hashing helps organize and retrieve data.
- How dictionaries store unique keys and associated values.
- How to count element frequencies.
- How `TryGetValue()` checks for a key and retrieves its value.
- How `HashSet<T>` helps identify repeated elements.

## 🏋️ Practice Questions

1. Count the frequency of each character in a string.
2. Find the first non-repeating character in a string.
3. Find duplicate elements in an array.
4. Solve the Two Sum problem using a dictionary.
5. Check whether two strings are anagrams using character frequencies.


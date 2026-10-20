# Day 12: Sorting Algorithms 🔢

## 📌 Overview

Today, I learned about **Sorting Algorithms** and how they arrange elements in ascending or descending order.

Sorting is an important concept in Data Structures and Algorithms (DSA) because sorted data can make searching and processing easier.

## 🧠 Algorithms Covered

1. **Bubble Sort** — Compares adjacent elements and swaps them when they are in the wrong order.
2. **Selection Sort** — Finds the smallest element and places it in the correct position.
3. **Insertion Sort** — Builds a sorted section by inserting each element into its correct position.

## 💻 1. Bubble Sort in C#

```csharp
using System;

class Program
{
    static void BubbleSort(int[] numbers)
    {
        for (int i = 0; i < numbers.Length - 1; i++)
        {
            bool swapped = false;

            for (int j = 0; j < numbers.Length - 1 - i; j++)
            {
                if (numbers[j] > numbers[j + 1])
                {
                    int temp = numbers[j];
                    numbers[j] = numbers[j + 1];
                    numbers[j + 1] = temp;

                    swapped = true;
                }
            }

            if (!swapped)
                break;
        }
    }

    static void Main()
    {
        int[] numbers = { 5, 2, 8, 1, 3 };

        BubbleSort(numbers);

        Console.WriteLine(string.Join(", ", numbers));
    }
}
```

**Output:**

```text
1, 2, 3, 5, 8
```

## 💻 2. Selection Sort in C#

```csharp
static void SelectionSort(int[] numbers)
{
    for (int i = 0; i < numbers.Length - 1; i++)
    {
        int minIndex = i;

        for (int j = i + 1; j < numbers.Length; j++)
        {
            if (numbers[j] < numbers[minIndex])
                minIndex = j;
        }

        int temp = numbers[i];
        numbers[i] = numbers[minIndex];
        numbers[minIndex] = temp;
    }
}
```

**Idea:** Find the smallest element in the unsorted section and move it to the front.

## 💻 3. Insertion Sort in C#

```csharp
static void InsertionSort(int[] numbers)
{
    for (int i = 1; i < numbers.Length; i++)
    {
        int key = numbers[i];
        int j = i - 1;

        while (j >= 0 && numbers[j] > key)
        {
            numbers[j + 1] = numbers[j];
            j--;
        }

        numbers[j + 1] = key;
    }
}
```

**Idea:** Take each element and insert it into its correct position within the already-sorted section.

## ⏱️ Time and Space Complexity

| Algorithm | Best Case | Average Case | Worst Case | Extra Space |
|---|---|---|---|---|
| Bubble Sort (optimized) | O(n) | O(n²) | O(n²) | O(1) |
| Selection Sort | O(n²) | O(n²) | O(n²) | O(1) |
| Insertion Sort | O(n) | O(n²) | O(n²) | O(1) |

*Note: Best-case O(n) for Bubble Sort assumes the optimized version checks whether any swaps occurred.*

## ⚖️ Comparison

| Algorithm | Main Idea | Useful For |
|---|---|---|
| Bubble Sort | Swap adjacent elements | Learning sorting fundamentals |
| Selection Sort | Select the minimum element | Understanding selection-based sorting |
| Insertion Sort | Insert into the sorted section | Small or nearly sorted arrays |

## 🎯 Key Takeaways

- Sorting arranges elements in a chosen order.
- Bubble Sort compares and swaps adjacent elements.
- Selection Sort repeatedly selects the smallest element.
- Insertion Sort inserts elements into their correct positions.
- These three algorithms use O(1) auxiliary space in the implementations shown.
- For large datasets, more efficient algorithms such as Merge Sort and Quick Sort are often preferred.

## 🏋️ Practice Questions

1. Sort an array in ascending order using Bubble Sort.
2. Modify the sorting logic to arrange elements in descending order.
3. Implement Selection Sort and Insertion Sort.
4. Count how many comparisons and swaps each algorithm performs.
5. Compare the algorithms using an already-sorted array and a reverse-sorted array.

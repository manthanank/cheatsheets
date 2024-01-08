---
title: Data Structure and Algorithms
date: "2023-01-03"
description: "Data Structure and Algorithms."
tags: ["dsa"]
---

## Algorithms

### Sorting

**Bubble Sort** - A sorting algorithm that compares two adjacent elements and swaps them until they are in the intended order.

```javascript
function bubbleSort(array) {
  // Loop to access each array element
  for (let i = 0; i < array.length; i++) {
    // Loop to compare array elements
    for (let j = 0; j < array.length - i - 1; j++) {
      // Compare two adjacent elements
      // Change > to < to sort in descending order
      if (array[j] > array[j + 1]) {
        // Swapping elements if elements
        // are not in the intended order
        let temp = array[j];
        array[j] = array[j + 1];
        array[j + 1] = temp;
      }
    }
  }
}

let data = [-2, 45, 0, 11, -9];
bubbleSort(data);

console.log("Sorted Array in Ascending Order:");
console.log(data);
```

**Insertion Sort** - Iterates through an array, comparing elements and moving them into their correct positions one by one.

**Selection Sort** - Divides the array into sorted and unsorted parts, repeatedly selects the smallest element from the unsorted portion and places it at the beginning of the sorted part.

**Merge Sort** - It is one of the most popular sorting algorithms that is based on the principle of Divide and Conquer Algorithm.

```javascript
function mergeSort(array) {
  if (array.length > 1) {
    // Split the array into two halves
    const r = Math.floor(array.length / 2);
    const L = array.slice(0, r);
    const M = array.slice(r);

    // Sort the two halves
    mergeSort(L);
    mergeSort(M);

    let i = 0;
    let j = 0;
    let k = 0;

    // Until we reach either end of either L or M, pick larger among
    // elements L and M and place them in the correct position at A[p..r]
    while (i < L.length && j < M.length) {
      if (L[i] < M[j]) {
        array[k] = L[i];
        i += 1;
      } else {
        array[k] = M[j];
        j += 1;
      }
      k += 1;
    }

    // When we run out of elements in either L or M,
    // pick up the remaining elements and put in A[p..r]
    while (i < L.length) {
      array[k] = L[i];
      i += 1;
      k += 1;
    }

    while (j < M.length) {
      array[k] = M[j];
      j += 1;
      k += 1;
    }
  }
}

// Print the array
function printList(array) {
  for (let i = 0; i < array.length; i++) {
    console.log(array[i]);
  }
}

// Driver program
const array = [6, 5, 12, 10, 9, 1];

mergeSort(array);

console.log("Sorted array is: ");
printList(array);
```

**Quick Sort** - A divide-and-conquer algorithm that divides an array into smaller sub-arrays and sorts them recursively.

**Heap Sort** - Utilizes a binary heap data structure to sort elements in an array by repeatedly selecting the maximum element from the heap.

**Counting Sort** - Suitable for sorting integers when the range of input is known. It counts the occurrences of each element and places them in order.

**Radix Sort** - Sorts integers by processing individual digits, typically starting from the least significant digit to the most significant.

**Bucket Sort** - Distributes elements into different "buckets" and then sorts these buckets individually, usually using another sorting algorithm or technique.

### Searching

**Linear Search** - Iterates through a list sequentially to find a target element.

**Binary Search** - Requires a sorted array and repeatedly divides the search interval in half until the target element is found or the search space is exhausted.

**Depth-first Search (DFS)** - Traverses a graph or tree by going as far as possible along a branch before backtracking.

**Breadth-first Search (BFS)** - Explores all neighbor nodes at the present depth level before moving on to nodes at the next depth level.

**Best-first Search** - Uses an evaluation function to decide which adjacent node to explore next, typically used in algorithms like A*.

**Ternary Search** - Divides the search space into three parts instead of two in binary search, useful in sorted and uniformly distributed arrays.

**Interpolation Search** - An improved variant of binary search that works better for uniformly distributed arrays by using interpolation to find the probable position of the target element.

**Exponential Search** - Exploits the property of binary search to find the range in which the target element lies, followed by a binary search in that range.

### Divide and Conquer

Breaks a problem into smaller, more manageable sub-problems until they become simple enough to solve directly.

### Backtracking

A methodical way to explore all possible configurations in a search space to find a solution.

### Recursion

Solves problems by breaking them down into smaller instances of the same problem.

### Dynamic Programming

Solves problems by breaking them down into simpler overlapping sub-problems, and storing the results to avoid redundant computations.

## Data Structure

**Array** - A collection of elements stored at contiguous memory locations.

**String** - A sequence of characters.

**Linked List** - A linear collection of elements where each element points to the next one.

**Matrix/Grid** - A 2-dimensional array often representing rows and columns of elements.

**Stack** - A Last-In-First-Out (LIFO) data structure where elements are inserted and removed from the same end.

**Queue** - A First-In-First-Out (FIFO) data structure where elements are inserted at the rear and removed from the front.

**Heap** - A specialized tree-based data structure that satisfies the heap property (max-heap/min-heap).

**Hash** - A data structure that maps keys to values, allowing for efficient retrieval, insertion, and deletion.

**Tree** - A hierarchical data structure composed of nodes, each having a value and references to its child nodes.

**Graph** - A collection of nodes (vertices) connected by edges that represent relationships or connections between the nodes.

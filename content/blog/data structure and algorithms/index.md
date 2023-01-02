---
title: Data Structure and Algorithms
date: "2022-12-31"
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

Insertion Sort

Selection Sort

Merge Sort

Quick Sort

Heap Sort

Counting Sort

Radix Sort

Bucket Sort

### Searching

Linear Search

Binary Search

Depth-first Search (DFS)

Breadth-first Search (BFS)

Best-first Search

Ternary Search

Interpolation Search

Exponential Search

### Divide and Conquer

### Backtracking

### Recursion

### Dynamic Programming

## Data Structure

Array

String

Linked List

Matrix/Grid

Stack

Queue

Heap

Hash

Tree

Graph

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

Insertion Sort

Selection Sort

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

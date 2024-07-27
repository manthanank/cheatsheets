---
title: Data Structure and Algorithms
date: "2024-07-27"
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

```javascript
function insertionSort(array) {
  // Loop through the entire array
  for (let i = 1; i < array.length; i++) {
    let j = i - 1;
    let temp = array[i];
    // Compare the current element with the next one
    while (j >= 0 && array[j] > temp) {
      // If the current element is greater, move it back
      array[j + 1] = array[j];
      j--;
    }
    // Insert the current element at its correct position
    array[j + 1] = temp;
  }
}

let data = [-2, 45, 0, 11, -9];
insertionSort(data);

console.log("Sorted Array in Ascending Order:");
console.log(data);
```

**Selection Sort** - Divides the array into sorted and unsorted parts, repeatedly selects the smallest element from the unsorted portion and places it at the beginning of the sorted part.

```javascript
function selectionSort(array) {
  // Loop through the entire array
  for (let i = 0; i < array.length; i++) {
    let min = i;
    // Find the index of the minimum element
    for (let j = i + 1; j < array.length; j++) {
      if (array[j] < array[min]) {
        min = j;
      }
    }
    // Swap the minimum element with the first element
    let temp = array[i];
    array[i] = array[min];
    array[min] = temp;
  }
}

let data = [-2, 45, 0, 11, -9];
selectionSort(data);

console.log("Sorted Array in Ascending Order:");
console.log(data);
```

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

```javascript
function quickSort(array, left, right) {
  if (left < right) {
    let pivot = partition(array, left, right);

    // Recursively sort elements around the pivot
    quickSort(array, left, pivot - 1);
    quickSort(array, pivot + 1, right);
  }
}

function partition(array, left, right) {
  let pivot = array[right];
  let i = left - 1;

  for (let j = left; j < right; j++) {
    if (array[j] < pivot) {
      i++;
      // Swap elements at i and j
      let temp = array[i];
      array[i] = array[j];
      array[j] = temp;
    }
  }

  // Swap elements at i+1 and right
  let temp = array[i + 1];
  array[i + 1] = array[right];
  array[right] = temp;

  return i + 1;
}

let data = [-2, 45, 0, 11, -9];
quickSort(data, 0, data.length - 1);

console.log("Sorted Array in Ascending Order:");
console.log(data);
```

**Heap Sort** - Utilizes a binary heap data structure to sort elements in an array by repeatedly selecting the maximum element from the heap.

```javascript
function heapSort(array) {
  let n = array.length;

  // Build max heap
  for (let i = Math.floor(n / 2) - 1; i >= 0; i--) {
    heapify(array, n, i);
  }

  // Heap sort
  for (let i = n - 1; i > 0; i--) {
    // Swap root with the last element
    let temp = array[0];
    array[0] = array[i];
    array[i] = temp;

    // Heapify the reduced heap
    heapify(array, i, 0);
  }
}

function heapify(array, n, i) {
  let largest = i;
  let left = 2 * i + 1;
  let right = 2 * i + 2;

  if (left < n && array[left] > array[largest]) {
    largest = left;
  }

  if (right < n && array[right] > array[largest]) {
    largest = right;
  }

  if (largest !== i) {
    let temp = array[i];
    array[i] = array[largest];
    array[largest] = temp;

    heapify(array, n, largest);
  }
}

let data = [-2, 45, 0, 11, -9];
heapSort(data);

console.log("Sorted Array in Ascending Order:");
console.log(data);
```

**Counting Sort** - Suitable for sorting integers when the range of input is known. It counts the occurrences of each element and places them in order.

```javascript
function countingSort(array) {
  let size = array.length;
  let output = new Array(size);
  let count = new Array(256);
  let max = array[0];

  for (let i = 1; i < size; i++) {
    if (array[i] > max) {
      max = array[i];
    }
  }

  for (let i = 0; i <= max; ++i) {
    count[i] = 0;
  }

  for (let i = 0; i < size; i++) {
    count[array[i]]++;
  }

  for (let i = 1; i <= max; i++) {
    count[i] += count[i - 1];
  }

  for (let i = size - 1; i >= 0; i--) {
    output[count[array[i]] - 1] = array[i];
    count[array[i]]--;
  }

  for (let i = 0; i < size; i++) {
    array[i] = output[i];
  }
}

let data = [4, 2, 2, 8, 3, 3, 1];
countingSort(data);

console.log("Sorted Array in Ascending Order:");
console.log(data);
```

**Radix Sort** - Sorts integers by processing individual digits, typically starting from the least significant digit to the most significant.

```javascript
function radixSort(array) {
  const getMax = (array) => {
    let max = 0;
    for (let num of array) {
      max = Math.max(max, num);
    }
    return max;
  };

  const digitCount = (num) => {
    if (num === 0) return 1;
    return Math.floor(Math.log10(Math.abs(num))) + 1;
  };

  const mostDigits = (array) => {
    let maxDigits = 0;
    for (let num of array) {
      maxDigits = Math.max(maxDigits, digitCount(num));
    }
    return maxDigits;
  };

  let maxDigits = mostDigits(array);
  for (let k = 0; k < maxDigits; k++) {
    let buckets = Array.from({ length: 10 }, () => []);
    for (let i = 0; i < array.length; i++) {
      let digit = Math.floor(Math.abs(array[i]) / Math.pow(10, k)) % 10;
      buckets[digit].push(array[i]);
    }
    array = [].concat(...buckets);
  }

  return array;
}

let data = [170, 45, 75, 90, 802, 24, 2, 66];
let result = radixSort(data);

console.log("Sorted Array in Ascending Order:");
console.log(result);
```

**Bucket Sort** - Distributes elements into different "buckets" and then sorts these buckets individually, usually using another sorting algorithm or technique.

```javascript
function bucketSort(array, bucketSize = 5) {
  if (array.length === 0) {
    return array;
  }

  let min = array[0];
  let max = array[0];
  for (let i = 1; i < array.length; i++) {
    if (array[i] < min) {
      min = array[i];
    } else if (array[i] > max) {
      max = array[i];
    }
  }

  let bucketCount = Math.floor((max - min) / bucketSize) + 1;
  let buckets = new Array(bucketCount);
  for (let i = 0; i < buckets.length; i++) {
    buckets[i] = [];
  }

  for (let i = 0; i < array.length; i++) {
    buckets[Math.floor((array[i] - min) / bucketSize)].push(array[i]);
  }

  array.length = 0;
  for (let i = 0; i < buckets.length; i++) {
    insertionSort(buckets[i]);
    for (let j = 0; j < buckets[i].length; j++) {
      array.push(buckets[i][j]);
    }
  }

  return array;
}

let data = [4, 2, 2, 8, 3, 3, 1];
let result = bucketSort(data);

console.log("Sorted Array in Ascending Order:");
console.log(result);
```

### Searching

**Linear Search** - Iterates through a list sequentially to find a target element.

```javascript
function linearSearch(array, target) {
  for (let i = 0; i < array.length; i++) {
    if (array[i] === target) {
      return i;
    }
  }
  return -1;
}

let data = [2, 3, 4, 10, 40];
let target = 10;
let result = linearSearch(data, target);

if (result !== -1) {
  console.log("Element found at index:", result);
} else {
  console.log("Element not found in the array");
}
```

**Binary Search** - Requires a sorted array and repeatedly divides the search interval in half until the target element is found or the search space is exhausted.

```javascript
function binarySearch(array, target) {
  let left = 0;
  let right = array.length - 1;

  while (left <= right) {
    let mid = left + Math.floor((right - left) / 2);

    if (array[mid] === target) {
      return mid;
    }

    if (array[mid] < target) {
      left = mid + 1;
    } else {
      right = mid - 1;
    }
  }

  return -1;
}

let data = [2, 3, 4, 10, 40];
let target = 10;
let result = binarySearch(data, target);

if (result !== -1) {
  console.log("Element found at index:", result);
} else {
  console.log("Element not found in the array");
}
```

**Depth-first Search (DFS)** - Traverses a graph or tree by going as far as possible along a branch before backtracking.

```javascript
function dfs(graph, node, visited) {
  if (!visited[node]) {
    console.log(node);
    visited[node] = true;
    for (let i = 0; i < graph[node].length; i++) {
      dfs(graph, graph[node][i], visited);
    }
  }
}

let graph = {
  0: [1, 2],
  1: [2],
  2: [0, 3],
  3: [3],
};
let visited = {};

dfs(graph, 2, visited);
```

**Breadth-first Search (BFS)** - Explores all neighbor nodes at the present depth level before moving on to nodes at the next depth level.

```javascript
function bfs(graph, start) {
  let visited = {};
  let queue = [start];

  while (queue.length > 0) {
    let node = queue.shift();
    if (!visited[node]) {
      console.log(node);
      visited[node] = true;
      for (let i = 0; i < graph[node].length; i++) {
        queue.push(graph[node][i]);
      }
    }
  }
}

let graph = {
  0: [1, 2],
  1: [2],
  2: [0, 3],
  3: [3],
};

bfs(graph, 2);
```

**Best-first Search** - An informed search algorithm that uses a heuristic to determine the most promising node to explore next.

```javascript
function bestFirstSearch(graph, start, goal) {
  let visited = {};
  let queue = [start];

  while (queue.length > 0) {
    let node = queue.shift();
    if (node === goal) {
      console.log("Goal node found");
      return;
    }
    if (!visited[node]) {
      console.log(node);
      visited[node] = true;
      for (let i = 0; i < graph[node].length; i++) {
        queue.push(graph[node][i]);
      }
      queue.sort((a, b) => heuristic(a, goal) - heuristic(b, goal));
    }
  }
}

function heuristic(node, goal) {
  // Heuristic function to estimate the distance from node to goal
  return Math.abs(node - goal);
}

let graph = {
  0: [1, 2],
  1: [2],
  2: [0, 3],
  3: [3],
};

bestFirstSearch(graph, 2, 3);
```

**Ternary Search** - Divides the search space into three parts instead of two in binary search, useful in sorted and uniformly distributed arrays.

```javascript
function ternarySearch(array, target) {
  let left = 0;
  let right = array.length - 1;

  while (left <= right) {
    let mid1 = left + Math.floor((right - left) / 3);
    let mid2 = right - Math.floor((right - left) / 3);

    if (array[mid1] === target) {
      return mid1;
    }

    if (array[mid2] === target) {
      return mid2;
    }

    if (target < array[mid1]) {
      right = mid1 - 1;
    } else if (target > array[mid2]) {
      left = mid2 + 1;
    } else {
      left = mid1 + 1;
      right = mid2 - 1;
    }
  }

  return -1;
}

let data = [2, 3, 4, 10, 40];
let target = 10;
let result = ternarySearch(data, target);

if (result !== -1) {
  console.log("Element found at index:", result);
} else {
  console.log("Element not found in the array");
}
```

**Interpolation Search** - An improved variant of binary search that works better for uniformly distributed arrays by using interpolation to find the probable position of the target element.

```javascript
function interpolationSearch(array, target) {
  let left = 0;
  let right = array.length - 1;

  while (left <= right && target >= array[left] && target <= array[right]) {
    let pos = left + Math.floor(
      ((right - left) / (array[right] - array[left])) * (target - array[left])
    );

    if (array[pos] === target) {
      return pos;
    }

    if (array[pos] < target) {
      left = pos + 1;
    } else {
      right = pos - 1;
    }
  }

  return -1;
}

let data = [2, 3, 4, 10, 40];
let target = 10;
let result = interpolationSearch(data, target);

if (result !== -1) {
  console.log("Element found at index:", result);
} else {
  console.log("Element not found in the array");
}
```

**Exponential Search** - Exploits the property of binary search to find the range in which the target element lies, followed by a binary search in that range.

```javascript
function exponentialSearch(array, target) {
  let n = array.length;
  if (array[0] === target) {
    return 0;
  }

  let i = 1;
  while (i < n && array[i] <= target) {
    i = i * 2;
  }

  return binarySearch(array, target, i / 2, Math.min(i, n - 1));
}

function binarySearch(array, target, left, right) {
  if (right >= left) {
    let mid = left + Math.floor((right - left) / 2);

    if (array[mid] === target) {
      return mid;
    }

    if (array[mid] > target) {
      return binarySearch(array, target, left, mid - 1);
    }

    return binarySearch(array, target, mid + 1, right);
  }

  return -1;
}

let data = [2, 3, 4, 10, 40];
let target = 10;
let result = exponentialSearch(data, target);

if (result !== -1) {
  console.log("Element found at index:", result);
} else {
  console.log("Element not found in the array");
}
```

### Divide and Conquer

Breaks a problem into smaller, more manageable sub-problems until they become simple enough to solve directly.

```javascript
function divideAndConquer(problem, params) {
  // Base case
  if (problem is simple) {
    return simpleSolution(problem);
  }

  // Divide the problem into subproblems
  subproblems = splitProblem(problem, data);

  // Recursively solve each subproblem
  solutions = [];
  for (subproblem in subproblems) {
    solutions.push(divideAndConquer(subproblem, params));
  }

  // Combine the solutions
  result = combineSolutions(solutions);
  return result;
}

let problem = "problem";
let params = "params";
let result = divideAndConquer(problem, params);

console.log(result);
```

### Backtracking

A methodical way to explore all possible configurations in a search space to find a solution.

```javascript
function backtracking(candidate, params) {
  if (candidate is a solution) {
    output(candidate);
    return;
  }

  for (next in list) {
    if (isValid(next, candidate)) {
      place(next, candidate);
      backtracking(candidate, params);
      remove(next, candidate);
    }
  }
}

let candidate = "candidate";
let params = "params";
backtracking(candidate, params);

console.log(result);
```

### Recursion

Solves problems by breaking them down into smaller instances of the same problem.

```javascript
function recursiveFunction(input) {
  if (input <= 0) {
    return input;
  } else {
    return recursiveFunction(input - 1);
  }
}

let input = 5;
let result = recursiveFunction(input);

console.log(result);
```

### Dynamic Programming

Solves problems by breaking them down into simpler overlapping sub-problems, and storing the results to avoid redundant computations.

## Data Structure

**Array** - A collection of elements stored at contiguous memory locations.

```javascript
let array = [1, 2, 3, 4, 5];
console.log(array);
```

**String** - A sequence of characters.

```javascript
let string = "Hello, World!";
console.log(string);
```

**Linked List** - A linear collection of elements where each element points to the next one.

```javascript
class Node {
  constructor(data) {
    this.data = data;
    this.next = null;
  }
}

class LinkedList {
  constructor() {
    this.head = null;
  }

  insert(data) {
    let newNode = new Node(data);
    if (this.head === null) {
      this.head = newNode;
    } else {
      let current = this.head;
      while (current.next !== null) {
        current = current.next;
      }
      current.next = newNode;
    }
  }

  display() {
    let current = this.head;
    while (current !== null) {
      console.log(current.data);
      current = current.next;
    }
  }
}

let list = new LinkedList();
list.insert(1);
list.insert(2);
list.insert(3);
list.display();

console.log(list);
```

**Matrix/Grid** - A 2-dimensional array often representing rows and columns of elements.

```javascript
let matrix = [
  [1, 2, 3],
  [4, 5, 6],
  [7, 8, 9],
];
console.log(matrix);
```

**Stack** - A Last-In-First-Out (LIFO) data structure where elements are inserted and removed from the same end.

```javascript
class Stack {
  constructor() {
    this.items = [];
  }

  push(element) {
    this.items.push(element);
  }

  pop() {
    if (this.items.length === 0) {
      return "Underflow";
    }
    return this.items.pop();
  }

  peek() {
    return this.items[this.items.length - 1];
  }

  isEmpty() {
    return this.items.length === 0;
  }
}

let stack = new Stack();
stack.push(1);
stack.push(2);
stack.push(3);
console.log(stack.pop());
console.log(stack.peek());
console.log(stack.isEmpty());
```

**Queue** - A First-In-First-Out (FIFO) data structure where elements are inserted at the rear and removed from the front.

```javascript
class Queue {
  constructor() {
    this.items = [];
  }

  enqueue(element) {
    this.items.push(element);
  }

  dequeue() {
    if (this.items.length === 0) {
      return "Underflow";
    }
    return this.items.shift();
  }

  front() {
    if (this.items.length === 0) {
      return "No elements in Queue";
    }
    return this.items[0];
  }

  isEmpty() {
    return this.items.length === 0;
  }
}

let queue = new Queue();
queue.enqueue(1);
queue.enqueue(2);
queue.enqueue(3);
console.log(queue.dequeue());
console.log(queue.front());
console.log(queue.isEmpty());
```

**Heap** - A specialized tree-based data structure that satisfies the heap property (max-heap/min-heap).

```javascript
class Heap {
  constructor() {
    this.items = [];
  }

  insert(element) {
    this.items.push(element);
    this.heapifyUp();
  }

  extract() {
    if (this.items.length === 0) {
      return "Underflow";
    }
    if (this.items.length === 1) {
      return this.items.pop();
    }

    let root = this.items[0];
    this.items[0] = this.items.pop();
    this.heapifyDown();
    return root;
  }

  heapifyUp() {
    let index = this.items.length - 1;
    while (index > 0) {
      let element = this.items[index];
      let parentIndex = Math.floor((index - 1) / 2);
      let parent = this.items[parentIndex];
      if (element <= parent) {
        break;
      }
      this.items[index] = parent;
      this.items[parentIndex] = element;
      index = parentIndex;
    }
  }

  heapifyDown() {
    let index = 0;
    let length = this.items.length;
    let element = this.items[0];

    while (true) {
      let leftChildIndex = 2 * index + 1;
      let rightChildIndex = 2 * index + 2;
      let leftChild, rightChild;
      let swap = null;

      if (leftChildIndex < length) {
        leftChild = this.items[leftChildIndex];
        if (leftChild > element) {
          swap = leftChildIndex;
        }
      }

      if (rightChildIndex < length) {
        rightChild = this.items[rightChildIndex];
        if (
          (swap === null && rightChild > element) ||
          (swap !== null && rightChild > leftChild)
        ) {
          swap = rightChildIndex;
        }
      }

      if (swap === null) {
        break;
      }

      this.items[index] = this.items[swap];
      this.items[swap] = element;
      index = swap;
    }
  }
}

let heap = new Heap();
heap.insert(1);
heap.insert(2);
heap.insert(3);
console.log(heap.extract());
```

**Hash** - A data structure that maps keys to values, allowing for efficient retrieval, insertion, and deletion.

```javascript
class HashTable {
  constructor() {
    this.table = [];
  }

  hash(key) {
    let hash = 0;
    for (let i = 0; i < key.length; i++) {
      hash += key.charCodeAt(i);
    }
    return hash % 37;
  }

  put(key, value) {
    let index = this.hash(key);
    this.table[index] = value;
  }

  get(key) {
    let index = this.hash(key);
    return this.table[index];
  }

  remove(key) {
    let index = this.hash(key);
    this.table[index] = undefined;
  }
}

let hashTable = new HashTable();
hashTable.put("John", 123);
hashTable.put("Doe", 456);
console.log(hashTable.get("John"));
hashTable.remove("Doe");
```

**Tree** - A hierarchical data structure composed of nodes, each having a value and references to its child nodes.

```javascript
class Node {
  constructor(value) {
    this.value = value;
    this.left = null;
    this.right = null;
  }
}

class BinaryTree {
  constructor() {
    this.root = null;
  }

  insert(value) {
    let newNode = new Node(value);
    if (this.root === null) {
      this.root = newNode;
    } else {
      this.insertNode(this.root, newNode);
    }
  }

  insertNode(node, newNode) {
    if (newNode.value < node.value) {
      if (node.left === null) {
        node.left = newNode;
      } else {
        this.insertNode(node.left, newNode);
      }
    } else {
      if (node.right === null) {
        node.right = newNode;
      } else {
        this.insertNode(node.right, newNode);
      }
    }
  }

  inorder(node) {
    if (node !== null) {
      this.inorder(node.left);
      console.log(node.value);
      this.inorder(node.right);
    }
  }
}

let tree = new BinaryTree();
tree.insert(5);
tree.insert(3);
tree.insert(7);
tree.insert(1);
tree.insert(4);
tree.insert(6);
tree.insert(8);
tree.inorder(tree.root);

console.log(tree);
```

**Graph** - A collection of nodes (vertices) connected by edges that represent relationships or connections between the nodes.
  
```javascript
class Graph {
  constructor() {
    this.adjacencyList = {};
  }

  addVertex(vertex) {
    if (!this.adjacencyList[vertex]) {
      this.adjacencyList[vertex] = [];
    }
  }

  addEdge(vertex1, vertex2) {
    this.adjacencyList[vertex1].push(vertex2);
    this.adjacencyList[vertex2].push(vertex1);
  }

  removeEdge(vertex1, vertex2) {
    this.adjacencyList[vertex1] = this.adjacencyList[vertex1].filter(
      (v) => v !== vertex2
    );
    this.adjacencyList[vertex2] = this.adjacencyList[vertex2].filter(
      (v) => v !== vertex1
    );
  }

  removeVertex(vertex) {
    while (this.adjacencyList[vertex].length) {
      const adjacentVertex = this.adjacencyList[vertex].pop();
      this.removeEdge(vertex, adjacentVertex);
    }
    delete this.adjacencyList[vertex];
  }
}

let graph = new Graph();
graph.addVertex("A");
graph.addVertex("B");
graph.addVertex("C");
graph.addEdge("A", "B");
graph.addEdge("B", "C");
graph.addEdge("C", "A");
graph.removeEdge("A", "B");
graph.removeVertex("C");

console.log(graph);
```

This is a brief overview of some common algorithms and data structures. There are many more algorithms and data structures that can be explored and implemented in various programming languages.

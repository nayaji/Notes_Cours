# JavaScript Algorithm Cheat Sheet

## Basics

### Variables
```javascript
let x = 10;            // Mutable variable that can be reassigned
const y = 20;          // Immutable variable that cannot be reassigned
```

### Functions
```javascript
function add(a, b) {
  return a + b;        // Traditional function syntax
}

const subtract = (a, b) => a - b; // Arrow function for concise syntax
```

### Loops
```javascript
for (let i = 0; i < 5; i++) {
  console.log(i);      // Standard for loop for iterations
}

let j = 0;
while (j < 5) {
  console.log(j);      // Executes while the condition is true
  j++;
}
```

### Conditional Statements
```javascript
if (x > y) {
  console.log("x is greater");   // Executes if condition is true
} else if (x === y) {
  console.log("x equals y");     // Executes if the first condition is false and this one is true
} else {
  console.log("y is greater");   // Executes if all previous conditions are false
}
```

### Arrays
```javascript
const arr = [1, 2, 3, 4];
arr.push(5);   // Add element to the end
arr.pop();     // Remove element from the end
arr.shift();   // Remove element from the start
arr.unshift(0); // Add element to the start
arr.slice(1, 3); // Extracts a portion without modifying the original
arr.splice(2, 1, 99); // Modifies array at index
```

## Common Algorithms

### 1. Factorial
```javascript
const factorial = (n) => {
  if (n <= 1) return 1;  // Base case
  return n * factorial(n - 1);  // Recursive call
};
```

### 2. Fibonacci Sequence
```javascript
const fibonacci = (n) => {
  if (n <= 1) return n;   // Base cases
  return fibonacci(n - 1) + fibonacci(n - 2);  // Recursive formula
};
```

### 3. Palindrome Check
```javascript
const isPalindrome = (str) => {
  return str === str.split('').reverse().join('');  // Compare original and reversed strings
};
```

### 4. Prime Number Check
```javascript
const isPrime = (num) => {
  if (num < 2) return false;       // Numbers less than 2 are not prime
  for (let i = 2; i <= Math.sqrt(num); i++) {
    if (num % i === 0) return false;  // Check divisors up to square root
  }
  return true;
};
```

## Sorting Algorithms

### Bubble Sort
```javascript
const bubbleSort = (arr) => {
  let len = arr.length;
  for (let i = 0; i < len; i++) {
    for (let j = 0; j < len - i - 1; j++) {
      if (arr[j] > arr[j + 1]) {
        [arr[j], arr[j + 1]] = [arr[j + 1], arr[j]]; // Swap elements
      }
    }
  }
  return arr;
};
```

### Merge Sort
```javascript
const mergeSort = (arr) => {
  if (arr.length <= 1) return arr;   // Base case for recursion

  const mid = Math.floor(arr.length / 2);
  const left = mergeSort(arr.slice(0, mid));  // Recursive sort on left half
  const right = mergeSort(arr.slice(mid));   // Recursive sort on right half

  return merge(left, right);  // Merge sorted halves
};

const merge = (left, right) => {
  let result = [];
  while (left.length && right.length) {
    if (left[0] < right[0]) {
      result.push(left.shift());
    } else {
      result.push(right.shift());
    }
  }
  return result.concat(left, right);  // Append remaining elements
};
```

## Searching Algorithms

### Linear Search
```javascript
const linearSearch = (arr, target) => {
  for (let i = 0; i < arr.length; i++) {
    if (arr[i] === target) return i; // Return index if target is found
  }
  return -1;  // Return -1 if target is not in array
};
```

### Binary Search
```javascript
const binarySearch = (arr, target) => {
  let left = 0;
  let right = arr.length - 1;

  while (left <= right) {
    const mid = Math.floor((left + right) / 2);
    if (arr[mid] === target) return mid;  // Return index if found
    else if (arr[mid] < target) left = mid + 1; // Search right half
    else right = mid - 1; // Search left half
  }

  return -1;  // Target not found
};
```

## Graph Algorithms

### Depth-First Search (DFS)
```javascript
const dfs = (graph, start, visited = new Set()) => {
  if (visited.has(start)) return;  // Skip already visited nodes

  console.log(start);  // Process node
  visited.add(start);

  for (const neighbor of graph[start]) {
    dfs(graph, neighbor, visited); // Recursive call on neighbors
  }
};
```

### Breadth-First Search (BFS)
```javascript
const bfs = (graph, start) => {
  const queue = [start];
  const visited = new Set();

  while (queue.length) {
    const node = queue.shift(); // Dequeue node

    if (!visited.has(node)) {
      console.log(node); // Process node
      visited.add(node);
      queue.push(...graph[node]); // Enqueue neighbors
    }
  }
};
```

## String Manipulations

### Reverse a String
```javascript
const reverseString = (str) => {
  return str.split('').reverse().join('');  // Split, reverse, and join the string
};
```

### Anagram Check
```javascript
const isAnagram = (str1, str2) => {
  return str1.split('').sort().join('') === str2.split('').sort().join('');
  // Sort and compare the two strings
};
```

## Miscellaneous Utilities

### Random Number Generator
```javascript
const getRandomInt = (min, max) => {
  return Math.floor(Math.random() * (max - min + 1)) + min; // Generate random integer
};
```

### Debounce Function
```javascript
const debounce = (func, delay) => {
  let timeout;
  return (...args) => {
    clearTimeout(timeout);
    timeout = setTimeout(() => func.apply(this, args), delay);
  };
};
```

### Throttle Function
```javascript
const throttle = (func, limit) => {
  let lastFunc;
  let lastRan;
  return (...args) => {
    const context = this;
    if (!lastRan) {
      func.apply(context, args);
      lastRan = Date.now();
    } else {
      clearTimeout(lastFunc);
      lastFunc = setTimeout(() => {
        if (Date.now() - lastRan >= limit) {
          func.apply(context, args);
          lastRan = Date.now();
        }
      }, limit - (Date.now() - lastRan));
    }
  };
};
```

### Deep Clone
```javascript
const deepClone = (obj) => {
  return JSON.parse(JSON.stringify(obj)); // Clone object by serializing and deserializing
};
```

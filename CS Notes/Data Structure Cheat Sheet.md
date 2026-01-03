# 📘 Coding Interview Study Guide — Data Structures (Tiers 1–3)

This guide covers **Tier 1–3 data structures** you *must* know for technical interviews.  
Each section includes:
- What it is
- Why it’s used
- Core operations
- Time & space complexity
- Common interview patterns
- Example problems to practice
- Key pitfalls

---

## 1️⃣ Arrays

### What It Is
A contiguous block of memory storing elements of the same type, accessible by index.

### Why Interviewers Love It
- Simple but powerful
- Foundation for many optimizations
- Used in **sliding window**, **two pointers**, **prefix sums**

### Core Operations
| Operation                | Time |
| ------------------------ | ---- |
| Access by index          | O(1) |
| Update by index          | O(1) |
| Insert / Delete (middle) | O(n) |
| Append (amortized)       | O(1) |
| Search (unsorted)        | O(n) |

### Common Patterns
- **Two Pointers**: left/right indices
- **Sliding Window**: fixed or variable size window
- **Prefix Sum**: precompute cumulative sums
- **Sorting + Scan**

### Interview Examples
- Two Sum
- Best Time to Buy and Sell Stock
- Maximum Subarray (Kadane’s Algorithm)
- Move Zeroes
- Container With Most Water

### Pitfalls
- Off-by-one/shifting indices errors
- Forgetting edge cases (empty array, size 1)
- Modifying array while iterating incorrectly

---

## 2️⃣ Strings

### What It Is
An array of characters (often immutable depending on language).

### Why Interviewers Love It
- Tests character manipulation
- Often paired with hash maps
- Forces careful index handling

### Core Operations
| Operation | Time |
|--------|------|
| Access char | O(1) |
| Concatenation | O(n) |
| Substring | O(n) |
| Compare strings | O(n) |

### Common Patterns
- **Character frequency counting**
- **Two pointers**
- **Sliding window**
- **Palindrome checks**
- **String building**

### Interview Examples
- Valid Anagram
- Longest Substring Without Repeating Characters
- Valid Palindrome
- Longest Palindromic Substring
- String Compression

### Pitfalls
- Rebuilding strings inefficiently
- Ignoring case / whitespace rules
- Unicode edge cases (sometimes)

---

## 3️⃣ Hash Tables (Maps / Sets / Dictionaries)

### What It Is
A key-value data structure providing **average O(1)** lookup using hashing.

### Why Interviewers Love It
- Converts brute force → optimized
- Tests problem-solving instincts
- Extremely practical

### Core Operations
| Operation | Time |
|--------|------|
| Insert | O(1) |
| Lookup | O(1) |
| Delete | O(1) |

> Worst case is O(n), but interviews assume good hashing.

### Common Patterns
- **Frequency counting**
- **Existence checks**
- **Index mapping**
- **Deduplication**

### Interview Examples
- Two Sum
- Contains Duplicate
- Group Anagrams
- Subarray Sum Equals K
- First Unique Character

### Pitfalls
- Forgetting to check existence
- Using map when set is enough
- Overusing space unnecessarily

---
## 4️⃣ Linked Lists

### What It Is
A sequence of nodes where each node points to the next (and possibly previous).

### Types
- Singly Linked List
- Doubly Linked List

### Core Operations
| Operation | Time |
|--------|------|
| Insert at head | O(1) |
| Delete node | O(1) |
| Search | O(n) |
| Access by index | O(n) |

### Common Patterns
- **Fast & slow pointers**
- **In-place reversal**
- **Dummy nodes**
- **Pointer manipulation**

### Interview Examples
- Reverse Linked List
- Linked List Cycle
- Merge Two Sorted Lists
- Remove Nth Node From End

### Pitfalls
- Losing references
- Forgetting to return new head
- Mishandling single-node lists

---

## 5️⃣ Stacks

### What It Is
A **Last-In-First-Out (LIFO)** data structure.

### Core Operations
| Operation | Time |
|--------|------|
| Push | O(1) |
| Pop | O(1) |
| Peek | O(1) |

### Common Patterns
- **Parentheses validation**
- **Monotonic stack**
- **Undo / backtracking**
- **DFS simulation**

### Interview Examples
- Valid Parentheses
- Min Stack
- Daily Temperatures
- Evaluate Reverse Polish Notation

### Pitfalls
- Forgetting empty stack checks
- Misusing stack when recursion suffices

---

## 6️⃣ Queues

### What It Is
A **First-In-First-Out (FIFO)** data structure.

### Core Operations
| Operation | Time |
|--------|------|
| Enqueue | O(1) |
| Dequeue | O(1) |

### Common Patterns
- **Breadth-First Search (BFS)**
- **Level-order traversal**
- **Sliding window**

### Interview Examples
- Number of Islands (BFS)
- Binary Tree Level Order Traversal
- Sliding Window Maximum (deque variant)

### Pitfalls
- Using array shift (O(n))
- Confusing queue vs stack traversal

---

## 7️⃣ Trees

### What It Is
A hierarchical data structure with a root and child nodes.

### Types
- Binary Tree
- Binary Search Tree (BST)

### Core Traversals
| Traversal | Order |
|-------|------|
| Preorder | Root → Left → Right |
| Inorder | Left → Root → Right |
| Postorder | Left → Right → Root |
| Level Order | BFS |

### Common Patterns
- **Recursion**
- **DFS vs BFS**
- **Height / depth calculations**
- **Divide & conquer**

### Interview Examples
- Maximum Depth of Binary Tree
- Invert Binary Tree
- Validate BST
- Lowest Common Ancestor

### Pitfalls
- Forgetting base cases
- Stack overflow via deep recursion
- Mixing BST rules with regular trees

---

## 8️⃣ Heaps (Priority Queues)

### What It Is
A complete binary tree where:
- Min-heap: parent ≤ children
- Max-heap: parent ≥ children

### Core Operations
| Operation | Time |
|--------|------|
| Insert | O(log n) |
| Remove top | O(log n) |
| Peek | O(1) |

### Common Patterns
- **Top K problems**
- **Streaming data**
- **Scheduling**

### Interview Examples
- Kth Largest Element
- Top K Frequent Elements
- Merge K Sorted Lists

### Pitfalls
- Using heap when sorting is enough
- Forgetting heap size constraints

---

## 9️⃣ Graphs

### What It Is
A set of nodes (vertices) connected by edges.

### Representations
- Adjacency List (preferred)
- Adjacency Matrix

### Traversals
- **DFS** (recursive / stack)
- **BFS** (queue)

### Common Patterns
- **Cycle detection**
- **Connected components**
- **Shortest path**
- **Topological sort**

### Interview Examples
- Number of Islands
- Course Schedule
- Clone Graph
- Graph Valid Tree

### Pitfalls
- Forgetting visited set
- Infinite loops
- Confusing directed vs undirected

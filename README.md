# Data-Structures-Algorithms-iOS
I have listed down resources to get the full control of data structures and algorithms in iOS, which basically includes roadmap to crack Fangg companies. 

1. Kodeco - Basics of algorithm (https://www.kodeco.com/books/data-structures-algorithms-in-swift/)
2. Swift Algorithm Club on GitHub

# Data Structures in Swift

This document categorizes and explains common **Linear** and **Nonlinear** data structures in Swift.

## Linear Data Structures

| **Data Structure** | **Description**                                                                                                                      | **Use Case**                                                           |
| ------------------ | ------------------------------------------------------------------------------------------------------------------------------------ | ---------------------------------------------------------------------- |
| **Array**          | An ordered collection of elements of the same type stored in contiguous memory.                                                       | Efficient random access, iterating over collections.                    |
| **Linked List**    | A dynamic data structure where each element (node) contains a reference to the next element.                                           | Frequent insertions or deletions at arbitrary positions.                |
| **Stack**          | A Last In, First Out (LIFO) data structure where elements are added and removed from the same end.                                      | Undo functionality, recursive algorithms, backtracking.                 |
| **Queue**          | A First In, First Out (FIFO) data structure where elements are added at the rear and removed from the front.                           | Task scheduling, breadth-first search, and real-time systems.           |
| **Tuple**          | A fixed-size collection of multiple values of potentially different types.                                                             | Returning multiple values from a function, grouping related values.     |
| **Optional**       | A type that represents the presence or absence of a value (`nil`).                                                                     | Handling nullable values, ensuring safety when working with variables.  |
| **Dictionary**     | A collection of key-value pairs where each key is unique.                                                                              | Efficient key-based lookups, representing mappings of unique keys to values. |
| **Set**            | An unordered collection of unique elements.                                                                                           | Ensuring uniqueness, fast membership checks.                            |
| **Range**          | Represents a sequence of values, usually numeric, between a start and end value.                                                      | Looping over a sequence, generating ranges in loops and conditions.     |

---

## Nonlinear Data Structures

| **Data Structure**         | **Description**                                                                                             | **Use Case**                                                 |
| -------------------------- | ----------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| **Tree**                   | A hierarchical structure where each node can have zero or more child nodes.                                  | Representing hierarchical data such as file systems, XML, and organizational charts. |
| **Binary Search Tree (BST)**| A binary tree where the left child node is smaller than the parent, and the right child node is larger.       | Efficient searching, insertion, and deletion in a sorted dataset. |
| **Heap**                   | A complete binary tree where each parent node is greater (max-heap) or smaller (min-heap) than its children. | Implementing priority queues, fast retrieval of the smallest or largest element. |
| **Graph**                  | A collection of nodes (vertices) connected by edges, representing pairwise relationships between elements.    | Representing networks such as social networks, transportation systems, or communication networks. |


### Array Operations

1. Create Array
   * Empty Array
       ```swift
          var emptyArray = [Int]()
   * Array with elements
      ```swift
          var nums = [1,2,3,4,5]
3. Access Array
    
    _Using Index_ , _Using first and last elements__

   * Using Index
       ```swift
          let firstElement = numbers[0] // 1
   * First and Last Elements:
      ```swift
          let first = numbers.first // 1
          let last = numbers.last   // 5

4. Modify Array

    _append, insert, remove, removeLast_
    * Append
       ```swift
            numbers.append(6) // numbers becomes [1, 2, 3, 4, 5, 6]
            numbers.append(contentsOf: [7,8,9]) // numbers becomes [1, 2, 3, 4, 5, 6, 7, 8, 9]
    * Insert
        ```swift
            numbers.insert(0, at: 0) // numbers becomes [0, 1, 2, 3, 4, 5, 6, 7, 8, 9]
    * Remove
        ```swift
            numbers.remove(at: 0) // numbers becomes [1, 2, 3, 4, 5, 6]
    * Remove Last
        ```swift
            numbers.removeLast() // numbers becomes [1, 2, 3, 4, 5, 6, 7, 8]
    * RemoveAll
        ```swift
            numbers.removeAll() // numbers becomes []
5. Combine and Split Array
    * Combine
      * Concantinate
        
      * Append Contents Of Another Array:  
   
7. Sorting Arrays
8. Checking Array Properties
9. Subarray Operations
10. Searching in Arrays
11. Transformation Operations
12. Iterating Through Arrays
    

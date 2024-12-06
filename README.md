
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
            numbers = numbers + [7,8,9] // numbers becomes [1, 2, 3, 4, 5, 6, 7, 8, 9]
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
5. Split and Join Array
   * Split array into halves
     
     _prefix , suffix_
     
       ```swift
           let firstHalf = array.prefix(4)  // [1, 2, 3, 4]
           let secondHalf = array.suffix(4) // [5, 6, 7, 8]
   * Split array with separator
       ```swift
            var str = "1,2,3,4,5,6"
            var modfiedArray = str.split(separator: ",") //modifiedArray becomes  ["1", "2", "3", "4", "5", "6"]
   * Join array with separator
       ```swift
            var joinedArray = modfiedArray.joined(separator: "^") //joinedArray becomes "1^2^3^4^5^6"
6. Sorting Arrays
   * Sort in place
     ```swift
           var numbers = [1,2,5,6,3,4]
           numbers.sort() // Ascending order: [1, 2, 3, 4, 5, 6, 7]
   * Sort into new array
     ```swift
           var numbers = [1,2,5,6,3,4]
           let sortedArray = numbers.sorted() // Returns a new sorted array
   * Reverse array
      ```swift
           numbers.reverse() // [7, 6, 5, 4, 3, 2, 1]
8. Checking Array Properties
    * isEmpty
      ```swift
        let numbers = [Int]()
        numbers.isEmpty // true
    
    * count
      ```swift
       let numbers = [1, 2, 3, 4, 5]
       numbers.count // 5
    * first
      ```swift
        let numbers = [1, 2, 3]
        numbers.first // 1
    * last
      ```swift
        let numbers = [1, 2, 3]
        numbers.last //3
    * capacity: The number of elements that the array can store without reallocating memory.
      ```swift
          var numbers = [1, 2, 3]
          print(numbers.capacity) // Typically >= 3, varies by Swift implementation
    * indices
      ```swift
          numbers.indices // 0..<3
    * startIndex
      ```swift
          numbers.startIndex // 0
    * endIndex
      ```swift
          numbers.endIndex // 3
    * sorted
      ```swift
          let sortedArray = numbers.sorted() // [1, 2, 3]
    
   Reverse vs Reversed 
    * reverse
       
      Modify the array in place to reverse elements. use it for MUTATING elements, the one that is declared with var. 

      ```swift
          let reversedArray = numbers.reverse() // [3, 2, 1] 

    * reversed
      Returns new collection with reverse version of original one, but doesnt modify the original array. Used on NON MUTATING elements.

       Note: reversed() returns a lazy ReversedCollection, which generates reversed elements only when accessed, avoiding the immediate creation of a new     
          array. This saves memory and processing time. To convert it into a full array, use Array(reversed()).
      
        ```swift
            let array = [1, 2, 3]
            let reversedArray = array.reversed()  // Does not modify the original array
            print(Array(reversedArray))           // Output: [3, 2, 1]
    * description  ---  A string representation of the array.
       ```swift
          numbers.description // "[1, 2, 3]"
    *  customMirror  --- Returns a mirror reflecting the array’s structure.
       ```swift
          numbers.customMirror //Mirror for Array
    
    *  size -- length of array
       ```swift
          numbers.size // 3
    *  capacity ---  total number of elements the array can hold without allocating new storage.
       ```swift
          numbers.capacity //  Capacity might be more than 3 to avoid repeated reallocation of memory
    
10. Subarray Operations
    * Extract subarray
      ```swift
          let array = [1, 2, 3, 4, 5, 6, 7, 8]
          // Extract a subarray from index 2 to 4 (indices are inclusive of the start and exclusive of the end)
          let subArray = Array(array[2..<5]) // Output: [3, 4, 5]
          let subArray = Array(array[2...5]) // Output: [3, 4, 5, 6]

    * Replace subarray
      ```swift
          var array = [1, 2, 3, 4, 5, 6]
          let newSubArray = [10, 11, 12]

          // Replace elements at index 1 to 3 with new elements
          array[1...3] = newSubArray // Output: [1, 10, 11, 12, 5, 6]

    * Insert subarray
      ```swift
           var array = [1, 2, 3, 6, 7]
           let subArray = [4, 5]
      
           // Insert subarray at index 3
           array.insert(contentsOf: subArray, at: 3) // Output: [1, 2, 3, 4, 5, 6, 7]

      
    * Remove subarray
      ```swift
          var array = [1, 2, 3, 4, 5, 6, 7, 8]
          // Remove elements from index 2 to 4 (inclusive of the start, exclusive of the end)
          array.removeSubrange(2..<5) // Output: [1, 2, 6, 7, 8]

    * Split array into subarrays
      ```swift
          let array = [1, 2, 3, 4, 5, 6, 7, 8]

          // Split the array when the value is greater than 4
          let subArrays = array.split(whereSeparator: { $0 > 4 }) // Output: [[1, 2, 3, 4], [5, 6, 7, 8]]

      
    * Slice an array
      ```swift
            let array = [1, 2, 3, 4, 5, 6]
            let slice = array[1...3] // Output: [2, 3, 4]

    * Reversing a Subarray
      ```swift
          var array = [1, 2, 3, 4, 5, 6]
          let subArray = Array(array[1...4].reversed()) // Output: [5, 4, 3, 2]
 
    * Sorting a Subarray
       
       ```swift
           var array = [5, 3, 1, 4, 6, 2]
           // Sort elements from index 1 to 4
           array[1...4].sort() // array becomes [5, 1, 3, 4, 6, 2]
           let array = [1, 2, 3, 4, 5, 6, 7, 8]

    * Filtering a Subarray
      ```swift
          // Filter elements greater than 4 in the subarray
          let filteredSubArray = array.filter { $0 > 4 } // Output: [5, 6, 7, 8]
      
11. Searching in Arrays
    _firstIndex, contains_
    *  First Index

        ```swift
        if let index = numbers.firstIndex(of: 3) {
        print(index) // 2
        }

     *  Contains

        ```swift
        let containsElement = numbers.contains(3) // true

12. Transformation Operations

    * Map : Apply a function to all elements
      ```swift
          var numbers = [1, 2, 3, 4, 5]
          let doubled = numbers.map { $0 * 2 } // [2, 4, 6, 8, 10]

    * Reduce : Combine elements into a single value.
      ```swift
            let sum = numbers.reduce(0, +) // Sum of all elements: 15

    * Filter : Filter elements based on a condition
      ```swift
          let evens = numbers.filter { $0 % 2 == 0 } // [2, 4]

14. Iterating Through Arrays
    * For Loop
      ```swift
            for number in numbers {
              print(number)
            }

    * Enumerated (Index + Element)
      ```swift
          for (index, value) in numbers.enumerated() {
            print("Index: \(index), Value: \(value)")
          }


 ## 1D 2D 3D Arrays
 
*  1D Array (One-Dimensional Array)
  
   A 1D array is a simple list of elements, where each element can be accessed by a single index.
   ```swift
          let oneDArray = [1, 2, 3, 4, 5]
          print(oneDArray[0]) // Output: 1


   Structure: A single list of values.
   Access: Use one index (e.g., oneDArray[0]).

* 2D Array (Two-Dimensional Array)
  A 2D array is essentially an array of arrays, like a table with rows and columns. You access elements by specifying two indices: one for the row and one for 
   the column.

  ```swift
        let twoDArray = [
        [1, 2, 3],
        [4, 5, 6],
        [7, 8, 9]
      ] //  print(twoDArray[0][1]) // Output: 2

*  3D Array (Three-Dimensional Array)
     A 3D array is an array of 2D arrays, like a collection of tables. You access elements by specifying three indices.
  
   ```swift
     let threeDArray = [
      [
        [1, 2], [3, 4]
      ],
      [
          [5, 6], [7, 8]
      ]
      ]
    print(threeDArray[0][1][1]) // Output: 4

 ## Searching & Sorting Algorithms
Now that we have completed basic data structures, next step is to ace the searching and sorting algorithms.

### Searching

* Linear Search
* Binary Search

### Sorting

* Bubble Sort
* Insertion sort
* Merge sort
* Heap sort
  Learn more about them here(https://medium.com/devslopes-blog/swift-data-structures-heap-e3fbbdaa3129)
  The ones who have kodeco subscription can read from here (https://www.kodeco.com/books/data-structures-algorithms-in-swift/v3.0/chapters/22-the-heap-data-structure)
  - Min Heap
    
  - Max Heap
* Radix sort


## Practice leet code

Now practice the following questions for the leetcode. 

### Tiktok

Arrays:

- Split largest Array sum(https://leetcode.com/problems/split-array-largest-sum/description/)

DFS:

- Number of islands (https://www.hackerrank.com/contests/crescent-practice-3rd-years/challenges/islands-1)


## Important techniques

###Sliding Window technique

  The sliding window technique is an efficient way to solve problems involving subarrays or substrings by maintaining a "window" of elements and adjusting its size dynamically as needed. This helps avoid recomputing values repeatedly, improving performance.

##### Initialize Variables:

Define two pointers (start and end) to represent the boundaries of the window.
Initialize any auxiliary variables needed for the problem, such as a running sum or product, counters, or results.

##### Expand the Window:

Incrementally move the end pointer to include elements in the window.
Update the state (e.g., running sum or product) based on the element at end.

##### Shrink the Window (if needed):

While a condition is not met (e.g., the sum or product exceeds a threshold), move the start pointer to shrink the window.
Adjust the state (e.g., subtract the element at start) as the window shrinks.

##### Process the Window:

At each step, process the current window (e.g., count valid subarrays or update a result variable).

##### Continue Until end Traverses the Array:

Repeat steps 2–4 until end has iterated through all elements.

##### Return Result:

Return the final result based on the specific problem requirements.

    

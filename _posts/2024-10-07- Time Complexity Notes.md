
# Time Complexity Overview
- **Time Complexity**: Measures the amount of time an algorithm takes to run as a function of the input size \( N \).
- Focuses on how an algorithm’s runtime grows as input increases.

## Big O Notation
- **Big O Notation**: Describes the upper bound or worst-case scenario of an algorithm’s time complexity.
  - It helps to compare the performance of different algorithms in terms of scalability.

## Common Big O Notations
1. **O(1)**: Constant time
   - The algorithm’s runtime is the same, regardless of input size.
   - **Example**: Accessing an element in an array.
2. **O(log N)**: Logarithmic time
   - The runtime increases logarithmically as input size grows.
   - **Example**: Binary search.
3. **O(N)**: Linear time
   - The runtime grows in direct proportion to the input size.
   - **Example**: Looping through a list.
4. **O(N log N)**: Linearithmic time
   - The runtime grows in proportion to \( N \) times the logarithm of \( N \).
   - **Example**: Merge sort, quicksort (average case).
5. **O(N²)**: Quadratic time
   - The runtime grows proportionally to the square of the input size.
   - **Example**: Nested loops (e.g., bubble sort).
6. **O(2^N)**: Exponential time
   - The runtime doubles with each additional input.
   - **Example**: Recursive algorithms like solving the Tower of Hanoi.
7. **O(N!)**: Factorial time
   - The runtime grows factorially with input size.
   - **Example**: Solving the traveling salesman problem via brute force.

## Key Considerations
- **Best Case, Average Case, Worst Case**:
  - Big O focuses on the worst case, but **Omega (Ω)** describes the best case, and **Theta (Θ)** describes the average case.
- **Trade-offs**:
  - Consider both time complexity (speed) and space complexity (memory usage) when designing algorithms.

## Summary
- **Big O Notation** provides a way to evaluate and compare algorithm efficiency.
- Different algorithms may have the same output but perform differently depending on the input size and the time complexity category they belong to.

---

# Introduction to O(N) Time Complexity
- **O(N)** means the time complexity increases in a linear fashion with the size of the input \( N \).
  - It’s one of the simplest forms of Big O, where the number of operations directly correlates to the number of elements being processed.

## Example Code: O(N) Function
- **Function Name**: `print_items`
  - The function accepts an input \( N \) and loops \( N \) times, printing each number.

```python
def print_items(n):
    for i in range(n):
        print(i)
```

### Explanation:
- If \( N = 10 \), the function will print 0 through 9, running the loop 10 times.
- The number of operations is directly proportional to the input size \( N \).

# Breakdown of O(N) Time Complexity
### Operations:
- For every input \( N \), the code performs \( N \) iterations.
- Therefore, the time complexity is **O(N)** since the number of operations increases at the same rate as \( N \).

### Visualizing O(N)
- **X-axis**: Represents the input size \( N \).
- **Y-axis**: Represents the number of operations.
  - In **O(N)**, the graph is a straight line, demonstrating the proportional growth of operations with the input size.

### Proportionality:
- The term "proportional" refers to the fact that as \( N \) increases, the number of operations increases in direct proportion.
  - When you hear the term "proportional" related to Big O, it usually indicates **O(N)**.

### Key Takeaways
- **O(N)**: Linear time complexity where the number of operations grows in direct relation to the input size \( N \).
- It's one of the easiest time complexities to understand because it has a simple, linear relationship between input size and operations.
- The graph for **O(N)** is a straight line, laying the foundation for understanding more complex Big O notations.

# O(log N) – Logarithmic Time Complexity Breakdown

### Key Characteristics
- **Logarithmic Time**: The number of operations grows in proportion to \( \log N \), where the problem size is reduced by a constant factor (typically halved) at each step.
- **Example Algorithm**: Binary Search on a sorted array.

### Binary Search Breakdown
1. **Initial Input**: Given a sorted array of size \( N \), start by checking the middle element.
2. **Reduction**: 
   - If the target is smaller, eliminate the right half of the array.
   - If the target is larger, eliminate the left half of the array.
3. **Repeat**: Continue halving the array until the target is found or there are no elements left.
4. **Number of Steps**: The number of times the array can be halved is \( \log_2(N) \), hence the time complexity is \( O(\log N) \).

### Code Example: Binary Search in Python
```python
def binary_search(arr, target):
    low = 0
    high = len(arr) - 1
    
    while low <= high:
        mid = (low + high) // 2  # Find the middle element
        if arr[mid] == target:   # If target is found
            return mid
        elif arr[mid] < target:  # If target is in the right half
            low = mid + 1
        else:                    # If target is in the left half
            high = mid - 1
    
    return -1  # Target not found
```

- **Explanation**: Each iteration halves the search space, leading to \( O(\log N) \) time complexity.

### Operations for O(log N)
For an input of size \( N \), the number of operations to find the target is proportional to how many times you can halve the input:

| Input Size (N) | Number of Halvings (\( \log N \)) | Max Operations |
|----------------|----------------------------------|----------------|
| 10             | 4                                | 4              |
| 100            | 7                                | 7              |
| 1,000          | 10                               | 10             |
| 1,000,000      | 20                               | 20             |

- **Interpretation**: Even for a large input size like 1 million, only 20 comparisons are needed.

### Key Takeaways
- **Logarithmic Time**: Efficient for large datasets, as the number of operations grows slowly compared to input size.
- **Binary Search**: A classic example where each step eliminates half the input, resulting in \( O(\log N) \) time complexity.
- **Real-World Relevance**: Used in efficient search algorithms and data structures like binary search trees and heaps.

---

# O(1) – Constant Time Complexity
### Definition
The algorithm's runtime does not change with the input size \( N \); it remains constant.

### Characteristics
- Always performs the same number of operations, regardless of the input.
- Extremely efficient since the time is fixed, no matter how large the input gets.

### Examples
- **Accessing an element in an array by its index**:
```python
element = arr[0]  # O(1)
```
- **Checking if a number is even or odd**:
```python
if n % 2 == 0:  # O(1)
    print("Even")
```


# O(N log N) – Linearithmic Time Complexity

### Overview
- **Definition**: The runtime grows proportionally to \( N \) multiplied by \( \log N \). This occurs in algorithms that break the input into smaller parts and process them recursively.
- **Common Use**: Found in efficient divide-and-conquer algorithms like mergesort, quicksort (average case), and heapsort.

### How it Works
- **Divide-and-Conquer**: These algorithms divide the input into smaller subproblems, solve them recursively, and then combine the results.
  - The process of dividing the input takes \( \log N \) steps.
  - For each level of division, \( N \) elements need to be processed, leading to \( O(N \log N) \) complexity.

### Example: Merge Sort
#### Merge Sort Algorithm:
- Recursively splits the array into halves until each sub-array has one element.
- Merges the sub-arrays while sorting them.

```python
def merge_sort(arr):
    if len(arr) > 1:
        mid = len(arr) // 2
        left = arr[:mid]
        right = arr[mid:]
        merge_sort(left)
        merge_sort(right)
        i = j = k = 0
        while i < len(left) and j < len(right):
            if left[i] < right[j]:
                arr[k] = left[i]
                i += 1
            else:
                arr[k] = right[j]
                j += 1
            k += 1
        while i < len(left):
            arr[k] = left[i]
            i += 1
            k += 1
        while j < len(right):
            arr[k] = right[j]
            j += 1
            k += 1
```

### Time Breakdown
- Splitting the array takes \( \log N \) steps.
- Merging takes \( N \) operations at each level.
- **Total complexity**: \( O(N \log N) \).

### Real-World Examples
- **Sorting Algorithms**: Merge sort, heapsort, and quicksort (on average) have \( O(N \log N) \) time complexity, making them much more efficient than quadratic algorithms like bubble sort for large inputs.


# O(N²) – Quadratic Time Complexity

### Overview
- **Definition**: The runtime grows proportionally to the square of the input size \( N \). Typically occurs in algorithms with nested loops, where each element is processed multiple times.
- **Common Use**: Found in simple comparison-based sorting algorithms and brute-force methods.

### How it Works
- **Nested Loops**: The algorithm processes every element once in an outer loop and processes every element again in an inner loop, leading to \( N \times N = N² \) operations.
  - For each additional input element, the number of operations grows quadratically, making these algorithms inefficient for large inputs.

### Example: Bubble Sort
#### Bubble Sort Algorithm:
- Compares each element with the next and swaps them if they are out of order.
- Repeats this process for every element until the array is sorted.

```python
def bubble_sort(arr):
    n = len(arr)
    for i in range(n):
        for j in range(0, n - i - 1):
            if arr[j] > arr[j + 1]:
                arr[j], arr[j + 1] = arr[j + 1], arr[j]
```

### Time Breakdown
- Outer loop runs \( N \) times.
- Inner loop runs \( N - i - 1 \) times, roughly \( N \) times.
- **Total complexity**: \( O(N \times N) = O(N²) \).

### Real-World Examples
- **Inefficient Sorting**: Bubble sort, selection sort, and insertion sort all have \( O(N²) \) time complexity. They perform poorly on large datasets due to the rapid growth in operations as \( N \) increases.
- **Brute Force Algorithms**: Some brute force approaches, like checking all pairs of elements in a set, exhibit quadratic complexity.

# Summary of Key Differences
- **O(N log N)**: More efficient, especially for large inputs. Common in divide-and-conquer algorithms like merge sort and quicksort.
- **O(N²)**: Less efficient, typical in algorithms with nested loops or brute force solutions, like bubble sort and insertion sort. Grows quickly as the input size increases.


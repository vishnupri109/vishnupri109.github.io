### Mathematical Explanation of O(N) – Linear Time Complexity

**Linear time complexity (O(N))** means that the runtime of an algorithm increases in direct proportion to the size of the input \( N \). Mathematically, the number of operations performed by the algorithm is a linear function of \( N \), or expressed as:

\[
f(N) = c \times N
\]

Where:
- \( N \) is the size of the input.
- \( c \) is a constant that represents the number of operations required per input element (it could be 1 or some constant number of operations).

#### Key Characteristics of O(N)
- **Proportional Growth**: For each additional element in the input, the algorithm performs a fixed number of operations.
  - **Example**: In a loop that iterates over \( N \) elements, the number of iterations grows directly with \( N \).

#### Example: Iterating Through a List
Consider the following code, which iterates over a list of size \( N \) and prints each element:

```python
def print_items(arr):
    for item in arr:
        print(item)
```
#### Operations:
- For each element in the list, one `print` operation is executed.
- If the list has \( N \) elements, the algorithm performs \( N \) `print` operations.

#### Mathematical Representation
Let’s break it down step by step:
- If the list has **1 element** (\( N = 1 \)), the loop runs **1** time.
- If the list has **10 elements** (\( N = 10 \)), the loop runs **10** times.
- If the list has **1,000 elements** (\( N = 1,000 \)), the loop runs **1,000** times.

In general, for an input of size \( N \), the loop executes \( N \) iterations. Therefore, the total number of operations (or steps) is directly proportional to \( N \).

Thus, the relationship between the input size \( N \) and the number of operations is **linear**, which is why the time complexity is \( O(N) \).

#### Graphical Representation
If you plot the number of operations versus the input size \( N \), you would get a straight line:

- **X-axis**: Input size \( N \).
- **Y-axis**: Number of operations.

As \( N \) increases, the number of operations increases in a straight line, which reflects the linear relationship.

#### Conclusion
- **O(N) time complexity**: The number of operations grows linearly with the input size.
- If the input size \( N \) doubles, the number of operations also doubles, resulting in a directly proportional relationship.

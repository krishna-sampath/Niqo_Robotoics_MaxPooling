
## Overview

This project implements two different algorithms to calculate the maximum value for each position of a sliding window over a matrix (or image). The problem is to efficiently compute the maximum of all values within a moving window (size \(k \times k\)) for all possible window positions over an input matrix (size \(n \times n\)).

The first implementation is a **naive approach**, and the second one improves performance by using **deque data structures** for optimal sliding window calculations. This README contains instructions to run the code, provide custom inputs, and verify the outputs and runtime performance.

### Features:
1. **Naive implementation**: This computes the maximum of each window by iterating through all the values in the window for each window position.
2. **Optimized implementation**: This uses an optimized sliding window algorithm to efficiently compute the maximum values in \(O(n \cdot m)\), where \(n\) is the size of the matrix and \(m\) is the size of the window.

## How to Run

### Prerequisites:
- Python 3.x
- NumPy for efficient numerical operations (`pip install numpy`)

### Running the Code

1. **Input**: 
    - Enter the matrix dimensions `n` as input.
    - Provide the matrix elements (one row at a time).
    - Enter the sliding window size `k`.

2. **Steps**:
    - Clone the repository or download the `max_pooling.ipynb` file.
    - Run the script using Python.
    - The code will calculate the sliding window maximum for both the naive and optimized implementations and print the results along with their runtime.

### Instructions:

Example of how to input data:

```
Enter the size of matrix: 4
3 4 2 1
1 5 4 6
3 6 7 2
3 2 5 4
Enter the window size: 2
```

### Example Output:
```
[[5 5 6 0]
 [6 7 7 0]
 [6 7 7 0]
 [0 0 0 0]]
--- 0.001 seconds ---

Naive implementation
[[5 5 6 0]
 [6 7 7 0]
 [6 7 7 0]
 [0 0 0 0]]
--- 0.010 seconds ---
```

## Custom Inputs

To provide custom inputs, follow these steps:
- Change the matrix dimensions as needed.
- Enter the matrix row by row.
- Change the window size to experiment with different window sizes.

For example, to compute with a matrix size of `5x5` and a window size of `3`, you would enter:

```
Enter the size of matrix: 5
2 1 3 4 5
3 4 6 8 2
1 4 9 7 2
3 6 5 4 1
7 2 1 9 4
Enter the window size: 3
```

## Findings

The optimized implementation performs significantly faster than the naive approach. The optimized approach uses a **deque** data structure to maintain the maximums within the sliding window efficiently, reducing unnecessary recalculations and achieving a runtime of \(O(n \cdot m)\), where \(n\) is the size of the matrix, and \(m\) is the sliding window size.

- **Naive Approach**: The naive approach involves iterating over all elements of each window and recomputing the maximum every time, resulting in a time complexity of $(O(n^2 \cdot k^2))$, where (n) is the matrix size and (k) is the window size.
- **Optimized Approach**: The optimized approach, using deques, reduces the complexity to ($O(n^2)$), as it processes each element only once per window.

### Performance Comparison

You can observe the performance by comparing the time taken for both implementations, which is printed as part of the output. For larger matrices and window sizes, the performance difference becomes more evident.

## Big O Complexity

1. **Naive Approach**:
   - Time Complexity: $(O(n^2 \cdot k^2))$, – For each of the (nXn) possible starting positions of the window, we compute the maximum over all (kXk) elements in the window.
   - Space Complexity: (O(1)) – The space complexity is constant, as no additional data structures are required apart from the input and output matrices.

2. **Optimized Approach**:
   - Time Complexity: \(O(n^2)\) – Each element in the matrix is processed at most twice due to the deque structure, resulting in linear time relative to the number of elements.
   - Space Complexity: \(O(k)\) – The deque can hold at most \(k\) elements at any time, where \(k\) is the window size.

### Verification of Performance

To verify performance improvements, you can run the code on large matrices (e.g., (100x100)) and compare the time taken by both implementations. You will notice a significant speedup using the optimized approach.

### Conclusion

The optimized sliding window approach is a clear improvement over the naive solution in terms of performance, especially for large matrices and large window sizes. The deque-based approach minimizes redundant calculations by leveraging the window's structure, leading to faster execution times and a more scalable solution.


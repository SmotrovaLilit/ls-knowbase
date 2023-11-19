# Dynamic Programming

## DP problems properties:
- **Optimal substructure**:  if problem's optimal solution for an input of size `n` can be expressed as a combination of the optimal solutions for smaller inputs of size `m<n`  it means that the problem has an optimal structure. For example, Fibonacci(n) 
- **Overlapping subproblems**: problem has overlapping subproblems if some subproblems are solved more than once. For example, Fibonacci(n) 
## Memoization (Top-Down DP)
_**Memoization = Recursion + Caching**_
Examples:
- Fibonacci
- Get maximal square in a rectangle
## Bottom-Up
iteratively populating the entire cache
Examples:
- Get maximal square in a rectangle

## References
1. [https://www.tryexponent.com/courses/software-engineering/data-structures/dynamic-programming](https://www.tryexponent.com/courses/software-engineering/data-structures/dynamic-programming)
2. 
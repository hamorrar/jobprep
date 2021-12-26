------------------
Competitive Programmer's Handbook
Chapter 2 - Time Complexity
------------------

# Time Complexity
Efficiency is important. It is easy to make an algorithm that solves the problem slowly, but it is much harder solve it quickly. Time complexity is a way to estimate how much time an algorithm will take for a given input size.

---

# Calulation Rules
Usually denoted with Big-O Notation to estimate worst-case time as a function of ``n``, the input size.

## Loops
- If there are ``k``-nested loops that iterate over the input, then the time complexity is ``O(n^k)``.

## Order of Magnitude
- Time complexity does not tell the exact number of times a loop is executed, only the order of magnitude. Constants are not included, so ``O(n) == O(2n) == O((2n+5)/2)``.

## Phases
- If the algorithm has various loops or parts to the it that do different things, then the time complexity is the slowest one since it is the bottleneck. For example:
```c++
for (int i = 1; i <= n; i++) {
    // code O(n)
}

for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= n; j++) {
        // code O(n^2)
    }
}

for (int i = 1; i <= n; i++) {
    // code O(n)
}
```

## Multiple Variables
- Sometimes time complexity can depend on some variables in this example:
```c++
for (int i = 1; i <= n; i++) {
    for (int j = 1; j <= m; j++) {
        // code
    }
}
```

## Recursion
- The time complexity of a recursive function depends on the number of times it is called and the time complexity of each call. For example:
```c++
void f(int n) {
    if (n == 1) return;
    f(n-1);
}
```
``f(n)`` is called ``n`` times and the time complexity of each call is ``O(1)`` so the total time complexity is ``O(n)``.

---

# Complexity Classes
Listed in order from best to worst time complexity.

| Time Complexity | Class | Description|
| ----------- | ----------- | ----------- |
| ``O(1)`` | Constant time | Does not depend on input size, direct forumla that results in the answer.|
| ``O(log n)`` | Logarithmic time | Often halves the input size at each step. ``log_2 n`` is the number of times ``n`` must be divided by 2 to get 1.|
| ``O(n)`` | Linear time | Iterates through the input a constant number of times. This is usually the best time complexity since it is usually necessary to access each input element at least once.|
| ``O(n log n)`` | No name | Often means the algorithm sorts the input or uses a data structure with ``O(log n)`` time. |
| ``O(n^2)`` | Quadratic time | Often contains two nested loops to go through all pairs of input elements. |
| ``O(2^n)`` | No name | Indicates that the algorithm iterates through all subsets of the input elements. |
| ``O(n!)`` | No name | Indicates that the algorithm iterates through all permutations of the input elements. |

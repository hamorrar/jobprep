------------------
Competitive Programmer's Handbook
Chapter 7 - Dynamic Programming
------------------

# Dynamic Programming
This is a technique that combines the correctness of complete search and the efficiency of greedy algorithms. It can be applied to problems that can be divided into overlapping subproblems that can be solved independently. Dynamic Programming is used to find an optimal solution and count the number of possible solutions.

## Example: Coin Problem
- Given a set of coins and their values, sum up the coins to a specified value ``n``.
- In Chapter 6, the greedy algorithm works with euro coins but doesn't always make an optimal solution.

### Recursive Formulation
- The main idea is to think of the problem recursively so the overall solution can be formed from the solutions to the smaller subproblems.
- In the Coin Problem, the recursive problem is: what is the smallest number of coins to form sum ``x``?
- ``solve(x)`` will be a function that tells the minimum number of coins to make up a sum ``x``. This function's values can be recursively calculated from its smaller values. Namely, if the target sum is 10 and the first coin picked is 1, the next subproblem of the original problem is figure out how many coins to make up the remaining 9 in the sum.
- The recursive formula becomes: ``solve(x) = min(solve(x-1)+1, solve(x-3)+1, solve(x-4)+1)`` for a coin set of values ``{1, 3, 4}``. The base case is ``solve(0) = 0`` because 0 coins are needed to sum to 0.
- The general form of this formula is ``solve(x) = min over all coin values of (solve(x-c)+1)`` for ``x > 0``, ``INF`` for ``x < 0``, and ``0`` if ``x = 0``.
- This is the code for the solution so far:
```c++
int solve(int x) {
    if (x < 0) return INF;
    if (x == 0) return 0;
    int best = INF;
    for (auto c : coins) {
        best = min(best, solve(x-c)+1);
    }
    return best;
}
```

### Memoization
- The solution above works but is not efficient because there can be an exponential number of ways to find a solution.
- Memoization is a technique that stores values of the function to an array so eahc subproblem has to be solved only once.
- Make a boolean array to store whether or not the value of ``solve(x)`` has be calculated before and an array of integers to store the values of ``solve(x)``.
- The code for the improved solution is:
```c++
int solve(int x) {
    if (x < 0) return INF;
    if (x == 0) return 0;
    if (ready[x]) return value[x];
    int best = INF;
    for (auto c : coins) {
        best = min(best, solve(x-c)+1);
    }
    value[x] = best;
    ready[x] = true;
    return best;
}
```
------------------
Competitive Programmer's Handbook
Chapter 5 - Complete Search
------------------

# Complete Search
The general idea is to generate all possible solution to the problem with brute force, then pick the best solution or count the number of solutions.

## Generating Subsets
The problem is to generate all subsets of a set of ``n`` elements from ``{0, 1, 2, ..., n-1}``.

### Method 1
- Use recursion to make a tree: left branch is that the element ``k`` in the recursive step is not included in the set and right branch is that ``k`` is included in the set. Example code:
```c++
void search(int k) {
    if (k == n) {
        // process subset
    } else {
        search(k+1);
        subset.push_back(k);
        search(k+1);
        subset.pop_back();
    }
}
```

---

## Generating Permutations
The problem is to generate all permutations of a set of ``n`` elements from ``{0, 1, 2, ..., n-1}``.

### Method 1
- Use recursion again to add elements one at a time to the permutation set. Maintain an array to know which elements have been chosen for the permuation or not. Example code:
```c++
void search() {
    if (permutation.size() == n) {
        // process permutation
    } else {
        for (int i = 0; i < n; i++) {
            if (chosen[i]) continue;
            chosen[i] = true;
            permutation.push_back(i);
            search();
            chosen[i] = false;
            permutation.pop_back();
        }
    }
}
```

---

## Backtracking
A backtracking algorithm begins with an empty solution and builds the solution one step at a time, recursively going through all the possible way to create a solutions.

### Example: N-Queens
- Place a Queen on the chess board one row at a time such that no Queen can attack any other Queen on the board at that step.

## Pruning the Search
Oftentimes, the search space is really big and has too many possibilities that do not lead to a valid solution. You can optimize the search algorithm by adding "intelligence" so the algorithm can catch these dead-ends before it goes too deep.

### Example: Creating a path that visits all squares on a chess board from the top lef to the lower right
- Basic: All possible paths
- Optimization 1: Path are symmetric across the diagonal, so pick down or right and multiply the number of solutions by two.
- Optimization 2: Terminate early if the search does not visit all the squares.
- Optimization 3+4: Terminate early if the search can only make a left or right move because it would have split the board in two parts and cannot reach both sides.
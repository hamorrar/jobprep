# [53. Maxiumum Subarray](https://leetcode.com/problems/maximum-subarray/)
- Discussed in [CP Handbook](https://cses.fi/book/book.pdf).
- ``O(n^3)`` time solution: three nested loops. outer loop is the start index, middle loop is the end index, inner loop counts the sum between the start and end index.
- ``O(n^2)`` time solution: remove one loop. outer loop is the start index, inner loop is the end index and adds to a sum variable and takes the max of the current sum and best subarray.
- ``O(n)`` time solution: remove another loop. main idea is to the calculate the maximum subarray that ends at the current position. Code: 
```c++
int best = 0, sum = 0;
for (int k = 0; k < n; k++) {
    sum = max(array[k],sum+array[k]);
    best = max(best,sum);
}
cout << best << "\n";
```
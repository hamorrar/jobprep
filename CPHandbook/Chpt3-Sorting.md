------------------
Competitive Programmer's Handbook
Chapter 3 - Sorting
------------------

# Sorting
It's a fundamental algorithm design problem. Efficient sorting algorithms work in ``O(n log n)`` time.

## Bubble Sort
- ``O(n^2)`` time. Consists of ``n`` rounds where when two consecutive elements are not in the correct order, they get swapped. After ``k`` iterations, the ``k`` largest elements are in the correct positions. No inversions/swaps needed if array is sorted. Need ``O(n^2)`` inversions if array in reverse order.

## Merge Sort
- ``O(n log n)`` time. Recusion based, not limited to swapping consecutive elements. General idea is to recursively sort the left half and the right half of the array and then merge them. This is efficient because it halves the array size at each step. There are ``O(log n)`` levels and ``O(n)`` time for each level.

---

# Binary Search
A general method for searching for an element in an array is to iterate over all array elements, which is at best ``O(n)`` time if unsorted. But if the array is sorted, binary search can do it in ``O(log n)`` time.

## 1 Possible Implementation
- Maintain an active search region, then half the size of the region at each step. The algorithm checks the middle element then focuses on the left or right if the element is ``<`` or ``>`` then the middle element. If the middle is equal to the element, then the element is found and search stops. Example code:
```c++
int a = 0, b = n-1;
while (a <= b) {
    int k = (a+b)/2;
    if (array[k] == x) {
        // x found at index k
    }
    if (array[k] > x){
        b = k-1;
    } else a = k+1;
}
```

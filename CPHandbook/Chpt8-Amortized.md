------------------
Competitive Programmer's Handbook
Chapter 8 - Amortized Analysis
------------------

# Amortized Analysis
This is a technique used when the time complexity of operations in an algorithm can vary, so it is hard to get a good idea of the efficiency of the algorithm. The idea is to focus on the overall algorithm, instead of individual operations.

## Two Pointers Method
- Two pointers are used to iterate through an array.
- The left pointer usually has the start of the array and the right pointers are the end of the array. Each pointer can only move in one direction: left pointer moves right and right pointer moves left.

## Nearest Smaller Element
- Problem is to find the first smaller element that comes after the element in an array.
- Maintain a stack of array values. Push to the stack when the array value is bigger than the top of the stack. Pop when the array value is smaller than the top of the stack. Move left to right in the array.

## Sliding Window Minimum
- Sliding window is a constant size subarray that moves from left to right in an array where we need to calculate something about the values in the subarray.
- Problem is to find the minimum value in a given window.
- Maintain a queue of array values. To move the window, remove the oldest value in the queue (leftmost value in the array that is in the queue) and add the next array value on the right of the window.
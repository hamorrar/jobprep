------------------
Competitive Programmer's Handbook
Chapter 4 - Data Structures
------------------

# Data Structures
A way to store data. Important to choose the appropriate structure for a problem because each structure has its own pros and cons.

## Dynamic Arrays
- An array whose size can be changed during the execution of the program. Average time complexity is ``O(1)`` for adding elements in to a ``vector`` in C++ because it allocated a bigger array and moves everything over, but this does not happen often.

## Set Structures
- Maintains a collection of elements with basic operations to add, search, and remove elements. Usually, elements have to be distinct/no repeats.

## Map structures
- A generalized array that holds key-value pairs. Keys can be of any data type and do not have to consecutive.

## Stack
- Adds an element to the top and removes elements from the top. Last In First Out. ``O(1)`` time.

## Queue
- Adds an element to the end and removes elements from the top. First In, First Out. ``O(1)`` time.

---

# Comparison To Sorting Example Problem
Given 2 arrays, ``A`` and ``B``, find the elements that are in both arrays.

## Algorithm 1
- Make a set of the elements in ``A`` and iterate through ``B`` to see if anything matches. Using the set structure, this is ``O(n log n)`` time.

## Algorithm 2
- Don't need to make an ordered set, so the set structure can be unordered, which makes the time ``O(n)`` since on the underlying data structure changes.

## Algorithm 3
- Sort arrays ``A`` and ``B`` then iterate through both to find the common elements. Time complexity of sorting is ``O(n log n)`` and the rest of the algorithm is ``O(n)``, so total time is ``O(n log n)``.

## Comparing the Algorithms
- Algorithms 1 and 2 are the same except different data structures. Algorithm 3 is the best because it sorts both arrays once in the beginning, which is a simple procedure, then iterates through both in linear time. This is better than the other algorithms because they need to maintain complex data structures.

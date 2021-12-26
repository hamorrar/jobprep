------------------
Competitive Programmer's Handbook
Chapter 1 - Introduction
------------------

# Introduction
Competitive programming has two topics: the design of algorthms and the implementation of algorithms.

## Design of Algorithms
- Problem solving and mathematical thinking. Need skills to analyze a problem and creatively solve them. The solution needs to be correct and efficient.

## Implementation of Algorithms
- Requires good programming skills. The algorithm and implementation have to be correct since things are autograded. Need to be straightforward and concise.

---

# Programming Languages
C++, Java, and Python are the most popular languages used in competitive programming. There isn't a single best language, so it is best to master several languages and understand when one language is advantageous over another.

---

# Working with Numbers

## Integers
- The most used integer in competitive programming is ``int``. If ``int`` is not big enough, then a ``long long`` is used.
- Be careful of data types when doing arithmetic with variables of potentially different types.

## Modular Arithmetic
- This operation results in the remainder when dividing two numbers. For example, ``17 % 5 = 2`` because ``17 = (3 * 5) + 2``.
- If the remainder is negative, calculate it as normal and add ``m`` for ``x % m < 0``.

## Floating Point Numbers
- Used for precise calculations, but still have rounding errors. Can specify how many decimals to output in the ``printf()`` call.
- Due to these precision errors, it is better to compare if two floating point numbers are within ``ε`` of each other, not ``==``.

---

# Shortening Code
Short code is ideal because it can be written fast, so short variable names are preferably in competitive programming.

## Type Names
- In C++, data types with long names can be shorten with a ``typedef long long ll`` so a programmer only has to type ``ll`` to make a new ``long long`` variable.

---

# Mathematics
It is important. See my [Discrete Math Guide](https://hilalmorrar.com/ucsc-guide/docs/majorguides/computerscience/discretemath/) for most of the information in this section.

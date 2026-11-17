# Unit 5 Discussion: Search Algorithms

## Overview

This assignment compares linear search and binary search.

## Learning Objectives

- Implement linear search
- Implement binary search
- Compare performance
- Analyze algorithm efficiency

## Requirements

1. Test both algorithms on a small dataset.
2. Test both algorithms on a large dataset.
3. Demonstrate edge cases.
4. Analyze performance.
5. Create a real-world search scenario.

# Unit 5 Discussion: Search Algorithms (Linear vs. Binary)

## Overview
In this assignment, I implemented, tested, and analyzed both linear search and binary search algorithms in Python. I evaluated how each algorithm behaves across varying dataset sizes, boundary conditions, and a real-world lookup scenario.

## Implementation Summary
* Linear Search (`linear_search`): I implemented a sequential scan that iterates through the list from index `0` to `n - 1`. I documented why this approach carries an **$O(n)$** time complexity, as the algorithm must examine every element in the worst-case scenario.
* Binary Search (`binary_search`): I implemented an iterative divide-and-conquer algorithm using `low`, `high`, and `mid` pointers on a pre-sorted list. I added comments explaining how each comparison eliminates half of the remaining search space, resulting in **$O(\log n)$** time complexity.

## Experiments & Findings
1. Small Dataset Test: I tested both algorithms on a sorted 10-element list for an existing value (`57`) and a non-existent value (`50`). Both algorithms returned identical, accurate indices (`6` and `-1`), with no perceptible speed difference due to the tiny input size.
2. Large Dataset Test & Performance Analysis: I generated a sorted dataset of 1,000,000 integers and timed 100 worst-case lookups. Binary search outperformed linear search by orders of magnitude because it required at most 20 comparisons ($\log_2(1,000,000) \approx 20$), whereas linear search scanned all 1,000,000 elements per query.
3. Edge Cases: I verified algorithm stability against an empty list (`[]`), a single-element list (`[42]`), and targets positioned at the first and last indices. Both functions handled empty and single-item inputs without index errors.
4. Real-World Scenario: I simulated an employee badge verification system containing 50,000 sorted badge IDs. Binary search demonstrated how pre-sorted enterprise databases achieve near-instantaneous record validation.

Reflection
1. While working on this task, I understood the influence of algorithm design on scalability and runtime by means of Big O time complexity. Designing algorithms for linear search and binary search allowed me to see the difference between O(n) time complexity of a sequential scan and O(logn) time complexity of a divide and conquer approach when dealing with lists of ten items to one million items.

2. The biggest hurdle for me during the implementation was ensuring the pointer boundaries while implementing the binary search algorithm without running into off-by-one errors or an endless loop. The problem I had at first was when I was not subtracting or adding 1 to my mid value while updating the values of low and high. I overcame this hurdle by manually checking my pointers.

3. Linear search would be very useful for small and/or unsorted datasets as it does not require any overhead costs before searching the dataset. On the other hand, binary search would be much better to use for big and often searched datasets, such as order tracking databases or user databases.

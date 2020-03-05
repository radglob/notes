# Chapter 2 - Getting Started

## 2.1 Insertion Sort

This algorithm is one solution to the sorting problem.
* Inputs: A sequence of numbers (a<sub>1</sub> ... a<sub>n</sub>.)
* Output: An ascending reordering of the input sequence.

Insertion sort is efficient for sorting a small number of elements. It is an
in-place sorting algorithm.

```
INSERTION-SORT(A)
for j = 2 to A.length
    key = A[j]
    // Insert A[j] into the sorted sequence A[1..j-1]/
    i = j - 1
    while i > 0 and A[i] > key
        A[i + 1] = A[i]
        i = i - 1
    A[i + 1] = key
```

Loop invariants are useful in designing algorithms. We need to show three
things:
* Initialization: true prior to first iteration of the loop.
* Maintenance: if true before an iteration, true during the next iteration.
* Termination: when the loop terminates, the invariant gives us a property that
    helps show that the algorithm is correct.

## 2.2 Analyzing Algorithms

Analyzing an algorithm means predicting the resources an algorithm requires. In
general, we are concerned with computational time, as it is one of the few
things that we can keep consistent across several different machines.

Taking the example of insertion sort, we can determine the running time by
looking at the number of primitive steps required. Insertion sort is a quadratic
function; that is, it takes n<sup>2</sup> time, where n is the number of elements in the
array being sorted.

What we're typically concerned about is the worst-case running time of an
algorithm. This provides us with an upper bound on the running time with any
input.

## 2.3 Designing Algorithms

There are multiple ways of designing algorithms:
* divide and conquer: break the problem up into the smallest pieces possible,
    solve for those and combine. These algorithms tend to be recursive. ex. merge sort
* incremental approach: start with a small part, solve, add another piece. ex.
    insertion sort.

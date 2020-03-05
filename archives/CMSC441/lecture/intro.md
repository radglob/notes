# CMSC 441 - Introduction - 08/28/2014

## TODOS:
* ~~Put dates for quizzes, exams into calendar.~~
* ~~Read chapters 1.1 - 3.2, review proof by induction.~~
* HW1 due 09/04/2014
* ~~Create graph drawings, post and link.~~

## How do you prove correctness in algorithms?
* Proof by induction.
    * [Merge sort](http://en.wikipedia.org/wiki/Merge_Sort): if it works on an array of a certain size (1), then it will
        work on an array of size 2, 3, ...
    * Also useful for non-recursive algorithms, like [insertion sort](http://en.wikipedia.org/wiki/Insertion_Sort).
* Loop invariant: a statement that you want to be true at the top of a loop.
    After every iteration, you still want it to be true.
    * `A[1, j-1]` is the original `A[1, j-1]` in sorted order.

## Induction for Problem Solving
Pirates Succession: Pirates go to a beach and find 63 pieces of gold. There are
seven pirates. At any time, they can stage a munity, which requires a majority
vote. If you're the captain, how much gold should each pirate get to prevent
them from mutinying?

         | 2  | 3  | 4  | 5  | 6  | 7
---------|----|----|----|----|----|---
Captain  |    |    |    |    |    | 60
1st Mate |    |    |    |    | 61 |  0
2nd Mate |    |    |    | 62 |  0 |  1
3rd Mate |    |    | 62 |  0 |  1 |  0
4th Mate |    | 62 |  0 |  1 |  0 |  1
5th Mate | 63 |  0 |  1 |  0 |  1 |  0
6th Mate | 0  |  1 |  0 |  1 |  0 |  1

NOTE: Generate an induction hypothesis, and work your way up.

## Tournament Graphs
Assume a round robin tournament with no ties.

Claim: There is always a spanning chain.

Induction hypothesis - P(n): Every tournament graph with `n` vertices has a spanning
chain.

P(n) => P(n+1): Given a tournament graph with `n+1` vertices, ...

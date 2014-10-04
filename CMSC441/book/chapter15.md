# Chapter 15 - Dynamic Programming

Dynamic programming, similar to divide-and-conquer, solves problems by combining
the solutions of subproblems. In divide-and-conquer, we partition the problem
into disjoint subproblems. In dynamic programming, we focus on overlapping
subproblems.

We apply dynamic programming to **optimization problems**, where there can be
multiple optimal solutions. As such, when solving such problems, it is
important to note that the solution is *an* optimal solution, not necessarily
*the* optimal solution.

In dynamic programming, we follow a sequence of four steps:

1. Characterize the structure of an optimal solution.
2. Recursively define the value of an optimal solution.
3. Compute the value of an optimal solution, typically in a bottom-up fashion.
4. Construct an optimal solution from computed information.

# 15.1 Rod cutting

A simple example of dynamic programming is the **rod-cutting problem**. It is as
follows:

Given a rod of length *n* inches and a table of prices *p<sub>i</sub>* for *i* =
1, 2, ... *n*, determine the maximum revenue *r<sub>n</sub>* obtainable by
cutting up the rod and selling the pieces.

|      length *i*       | 1 | 2 | 3 | 4 | 5  | 6  | 7  |  8 | 9  | 10 |
| price *p<sub>i</sub>* | 1 | 5 | 8 | 9 | 10 | 17 | 17 | 20 | 24 | 30 |

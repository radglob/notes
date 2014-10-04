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

We solve these problems by decomposing the original problem into smaller
versions of the same problem. Optimal solutions are derived by incorporating
optimal solutions from subproblems.

The problem can be described in a recursive top-down manner:
```
Cut-Rod(p, n)
if n == 0
  return 0
q = -infinity
for i = 1 to n
  q = max(q, p[i] + Cut-Rod(p, n-i))
return q
```

One issue with this implementation is that it solves the same subproblems over
and over again. As such, the amount of work grows rapidly as *n* grows.

Using dynamic programming, we can define a much more efficient implementation.
There are two ways we do this: **top-down with memoization** and **bottom-up**.

In the former, we solve in the same recursive manner, but modify the algorithm
to save the result of each subproblem. In the latter, we sort our subproblems by
size and solve them smallest to largest.

```
Memoized-Cut-Rod(p, n)
let r[0..n] = []
for i = 0 to n
  r[i] = -infinity
return Memoized-Cut-Rod-Aux(p, n, r)

Memoized-Cut-Rod-Aux(p, n, r)
if r[n] >= 0
  return r[n]
if n == 0
  q = 0
else q = -infinity
  for i = 1 to n
    q = max(q, p[i] + Memoized-Cut-Rod-Aux(p, n-i, r))
r[n] = q
return q

Bottom-Up-Cut-Rod(p, n)
let r[0..n] = []
r[0] = 0
for j = 1 t n
  q = -infinity
  for i = 1 to j
    q = max(q, p[i] + r[j-i])
  r[j] = q
return r[n]
```



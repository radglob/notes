# Chapter 3 - Growth of Functions

The order of growth gives a simple characterization of the algorithm's
efficiency and shows relative performance to alternatives. For example, with
sufficiently large input sizes, merge sort (O(n lg n)) outperforms insertion
sort (O(n^2)).

## Asymptotic notation

We can declare a function Theta(g(n)) for any function f(n). This means that the
function has an upper bound and lower bound of g(n).

Big Oh notation (O(f(n)) is the upper bound of a function.
Big Omega notation is the lower bound of a function.

Big Oh may or may not be asymptotically tight, so we use little-oh to denote an
upper bound that is not asymptotically tight. The equivalent for Big Omega is
little omega.

Based on certain asymptotic qualities of functions, we can compare functions to
one another. See pgs. 51 - 52

## Standard Notations and Common Functions

* Monotonicity: a function f(n) is monotonically increasing if m &le; n implies
    f(m) &le; f(n). A function can also be monotonically decreasing, strictly
    (&lt; or &gt;, not &le; or &ge;) increasing and strictly decreasing

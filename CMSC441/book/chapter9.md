# Chapter 9 - Median and Order Statistics

* *i*th order statistic: the *i*th smallest element in a set of *n* elements.
    * For the minimum, *i* = 1; for the maximum, *i* = *n*
* The median is informally referred to as the halfway point in the set. If *n* is
    odd, the median is unique. If *n* is even. then there are two medians at *i*
    = *n* / 2 and *i* = *n* / 2 + 1

## 9.1 Minimum and maxiumum:
How many comparisons are needed to determine the minimum of a set? O(n-1) = O(n)

```
Minimum(A)
min = A[1]
for i = 2 to A.length
  if min > A[i]
    min = A[i]
return min
```

Finding the maximum in a set is very similar, with the same upper bound. The
only difference is how we compare (is max > A[i]).

### Simultaneous minimum and maximum
There are some applications where we need to calculate the minimum and maximum
in a set simultaneously. Intuitively, we can do this in n - 1 comparisons each,
with a total of 2n - 2 comparisons. However, we can actually do this in at most
3(n/2) comparisons. We can do this by maintaining the min and max we've
encountered so far.

How we set up the initial values depends on if the set is odd or even. If *n* is
odd, we set both the min and max to the first element, and process the rest of
the elements in pairs. If *n* is even, we set the first two elements to the min
and max and process the rest in pairs.

## 9.2 Selection in expected linear time
General selection is much more difficult than finding a minimum. However, the
asymptotic running time is still linear. The algorithm RANDOMIZED-SELECT is
modeled after quicksort, but only works on one side of the partition.

```
Partition(A, p, r) // from Chapter 7.1
x = A[r]
i = p - 1
for j = p to r - 1
  if A[j] <= x
    i = i + 1
    A[i], A[j] = A[j], A[i]
A[i+1], A[r] = A[r], A[i+1]
return i + 1

Randomized-Partition(A, p, r) // from Chapter 7.3
i = Random(p, r)
A[r], A[i] = A[i], A[r]
return Partition(A, p, r)

Randomized-Select(A, p, r, i)
if p == r
  return A[p]
q = Randomized-Partition(A, p, r)
k = q - p + 1
if i == k // The pivot value is the answer.
  return A[q]
elseif i < k
  return Randomized-Select(A, p, q-1, i)
else return Randomized-Select(A, q+1, r, i-k)
```

## 9.3 Selection in worst case linear time
The worst case of Randomized-Select is O(n<sup>2</sup>). We can do better. The
Select algorithm functions similarly to Randomized-Select, but we guarantee a
good split upon partitioning. It uses a deterministic partition, but modified to
take the element to partition around as an input parameter.

Deterministic Select:
1. Divide the *n* elements of the input array into *n*/5 groups of 5 elements each
and at most one group of *n* mod 5 elements.
2. Find the median of each *n*/5 group by first insertion sorting the elements
of each group (this takes constant time), and then picking the median from the
sorted list of grouped elements.
3. Use Select recursively to find the median *x* of the n/5 medians found. If
there are an even number of medians, then *x* is the lower median.
4. Partition the input array around the median-of-medians *x* by using the
modified version of Partition. Let *k* be one more than the number of elements
in the low side of the partition, so that *x* is the *k*th smallest element and
there are *n*-*k* elements on the high side.
5. If *i* = *k*, then return *x*. Otherwise, use Select recursively to find the
*i*th smallest element on the low side if *i* < *k*, or the (*i*-*k*)th smallest
element on the high side if *i* > *k*.

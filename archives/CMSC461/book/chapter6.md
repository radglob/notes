# Chapter 6 - Formal Relational Query Languages

## 6.1 The Relational Algebra

The relational algebra is a procedural query language. Fundamental operations
include select, project, union, set difference, Cartesian product, and rename.
Additional operations are set intersection, natural join and assignment.

* select: selects a tuple that satisfies a given predicate.
* project: unary operation that returns the argument relation with certain
    attributes left out.
* union: join the tables.
* set difference: return tuples that are in at most one relation.
* Cartesian product: combines attributes from both tables into one.
* rename: assigns a handle to tuples.
* natural join: combines values in both tuples and removes duplicates.
* theta join: combines natural join and Cartesian product into one operation.
* outer join: extension of join that deals with missing data.

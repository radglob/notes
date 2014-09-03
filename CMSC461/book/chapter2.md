# Chapter 2 - Introduction to the Relational Model

The relational model is the primary data model in commercial applications today..

## 2.1 Structure of Relational Databases

Relational databases are collections of tables, each with a unique name. Tables
are referred to as relations, rows as tuples, and the column of a table as
attributes.

Attributes have a set of permitted values, called the domain of the attribute. A
domain is atomic if elements of the domain are considered indivisible elements.

## 2.2 Database Schema

A database schema is the logical design of a database, whereas a database
instance is a snapshot of the data in the database at a given instant in time.

## 2.3 Keys

A superkey is a set of one or more attributes that allow us to uniquely
identify a tuple. Candidate keys are minimal superkeys.

The primary key is a key chosen by the designer to serve as a principal means of
identifying tuples in a relation.

A foreign key is a key from another relation that allows it to be identified in
relation to the second item.

## 2.5 Relational Query Languages

A query language allows the user to request information from the database. In
procedural language, the user instructs the system to perform a set of
operations. In non-procedural languages, the user describes the information
without specific procedures being defined.

## 2.6 Relational Operations

* join: combining two relations by merging pairs of tuples into a single tuple.
* Cartesian product: combines tuples from two relations, resulting in all pairs
    from the two relations, regardless of whether their attributes match.
* union: set union of two similarly structured tables.
* intersection: set difference of two tables.

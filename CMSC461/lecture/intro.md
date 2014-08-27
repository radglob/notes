# CMSC 461 - Introduction - 08/27/2014

Professor Name: Jennifer Sleeman
Email: jsleem1@umbc.edu
Website: [here](http://www.csee.umbc.edu/~jsleem1/courses/461)

## TODOS:
* Read the syllabus.
* Read chapter 1, 2, 6.1 by Wednesday, 09/03/2014.
* Read about Oracle data dictionary.

## Databases are changing...
* Key-value based.
* Document based.
* Graph based.

## Databases are challenging...
* More and more data (terabytes, petabytes, exobytes..)
* Big data problems
* Harder problems to solve.
* Interoperability - how to map between incompatible schemas.

## What does this mean?
* Job opportunities.
* Cool research problems.

## What is a database?
* A collection of interrelated, organized data.

## What is a DBMS?
* A database and applications to acces it.
* Define, store and retrieve data, conveniently and efficiently.
* Provides security, reliability, concurrency and handling large volumes of
    information.
* What is wrong with the file system approach?
    * If you lose power in the middle of a "transaction", what happens?
    * Most data would be added on line at a time.
    * tl;dr Data redundancy, inconsistency, difficulty, isolation, integrity
        issues, atomicity issues.
* Capabilities:
    * supports concurrency, persistent data
    * handles large volumes of data efficiently

## Definitions:
* Instance: a collection of information stored at some point in time.
* Schema: the overall design of the database, partitioned according to
    abstraction level.
* Physical data independence: ability to change physical schema without
    affecting logical schema.
* Logical data independence: ... logical ... physical

## Data Models:

## What is a table?
* A table (also called a relation) is a set of rows (tuple) and columns for
    organizing data.
* A relational model is a set of tables (record based).
* An entity-relation model maps entities by their relations.
    * An entity is a row in a table. A collection of rows is an entity set.
    * A relation is a mapping between entities. A collection of relations is a
        relation set.

## Languages:
* data definition language creates tables.
* ex:
```sql
create table instructor
ID      char(5)
name    varchar(20)
...
```
* A data dictionary tracks integrity, keys, permissions, etc.
* data manipulation languages (query languages) have two types: procedural and
    non-procedural. SQL is non-procedural.
* ex. Find name of instructor.
```sql
select name from instructor where instructor.ID = '22222';
```

## SQL - Structured Query Language
* Application programs generally access databases through:
    * language extensions to allow embedded SQL.
    * APIS (e.g JDBC) which allow queries to be sent to a database.

## Database design:
* Mainly focised on database schema.
    * Models enterprise.
* Conceptual design phase:
    * Translate requirements to data model.
* How do you decide which attributes should be captured, and how do you group
    them?
    * Business decisions
    * Entity-relationship model
    * Normalization
* Logical Design Phase: high level concept to implementation.
* Physical design phase

## Normalization
* Meant to reduce redundancy and optimize for efficiency.

## Storage Manager
* Provides an interface between low-level data and application programs and
    queries.
* Responsible for interaction with the file manager.
* Translates DML statements into low level file commands.
* Authorization, integrity, transaction, file management.

## Query Processing
* DDL interpreter
* DML compiler
* Query evaluation engine

## Transaction Management
* a transaction is a collection of operations that performs a single logical
    function in a database application.
* recovery manager, failure recovery, concurrency-control manager.

## Database Architecture:

## Users:
* naive
* application developer
* ...
* DBA

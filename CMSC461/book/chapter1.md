# Chapter 1: Introduction

## Definitions:
* database-management system (DBMS): a collection of interrelated data and a set
    of programs to access that data. Designed to be **convenient** and
    **efficient**.
* database: a collection of data.
* instance: a collection of information stored in a database at a particular
    moment.
* schema: the overall design and organization of a database.
    * physical schema: how data is organized at the physical level.
    * logical schema: how data is described at the logical level.
* subschema: schemas existing at the view level, defining different views of the
    data.
* physical data independence: a quality of the logical level where it doesn't
    need to know about the complexity of the physical level.
* data model: the underlying structure of a database; collection of conceptual
    tools for describing data, relationships, semantics, and consistency
    constraints.
* data-manipulation language (DML): a language that enables users to access and
    manipulate data. Users can retrieve data, insert new information, delete
    information, or update information.
    * procedural DML: requires a user to specify **what** data and **how** to
        get it.
    * declarative (non-procedural) DML: requires a user to specify **what**
        information **without** describing **how** to get it. 
* query: a statement requesting the retrieval of information.
* query language: portion of the DML involving making queries.

## 1.1 Database-System Applications
Databases can be used for a variety of applications. These include:
* Enterprise information: sales, accounting, human resources, etc.
* Banking and Finance: banking, credit card information, finance
* Universities: student information, courses, grades.
* Airlines: reservations, schedule information. NOTE: airlines were one of the
    first entities to use databases in a geographically distributed manner.
* Telecommunications

Databases are considered an essential part of most modern enterprises.

## 1.2 Purpose
Database arose to provide a more better way to store large volumes of
information. They solve certain issues in file-processing systems:
* data redundancy and inconsistency.
* difficulty accessing data.
* data isolation
* integrity problems
* atomicity problems
* concurrent-access anomalies
* security problems

## 1.3 View of Data
### 1.3.1 Data Abstraction
In databases, there are typically three layers of abstraction.
1. Physical level: the lowest level of abstraction, dealing with **how** data is stored.
2. Logical level: middle layer of abstraction concerning **what** data is stored
    in the system, and what relationships exist between data. This layer is has
    **physical data independence**.
3. View level: the highest level of abstraction that exists to simplify
    interaction with the database. There may be many views of the same database
    depending on who is accessing it and how.

Take the following record:
```sql
type instructor = record
                    ID: char(5);
                    name: char(20);
                    dept_nam: char(20);
                    salary: numeric(8,2);
                  end;
```
This code defines a new record type **instructor** with four fields. Each field
has a type associated with it.

At the physical level, any record can be described as a block of consecutive
storage locations. Programmers will not be aware of this, but DBAs may need to
be.

At the logical level, each record is described by a type
definition, and the interrelatonship between record types are also recorded.
Programmers using a programming language work at this level, as do DBAs.

At the view level, computer users see a set of applications that hide details of
types. Several views may be defined, with a user seeing some or all of them.
There are also security mechanisms to prevent users from accessing certain parts
of the database.

### 1.3.2 Instances and Schemas
Databases change over time as information is stored and removed. While instances
change by nature, schemas rarely do, if ever. NOTE: a properly designed schema
will likely never need to change. But they can be difficult to design.

### 1.3.3 Data Models
A data model provides a way to describe the design of a database at each
abstraction level. There are a number of different data models:
* relational model: collection of tables with relationships connecting them.
* entity-relationship model: collection of objects connected by relationships.
* object-based data model: extension of e-r model with encapsulation, methods
    and object identity.
* semistructured data model: flexible model where data items of the same type
    can have different types of attributes.
    [XML](http://en.wikipedia.org/wiki/XML) is a good example of this.
* the network data model and hierarchical data model preceded the relational
    model. They complicated data design and are now rarely used outside of
    legacy systems.

## 1.4 Database Languages:
A database system provides a **data-definition language** to specify schema and
a **data-manipulation language** to express queries and updates.

### 1.4.1 Data-Manipulation Language
These are used to access information in various ways. There are two types:
procedural and declarative DMLs. Part of the language is designed for accessing
information.

### 1.4.2 Data-Definition Language
These are used to specify the structure and access methods of a database.
* **data storage and definition** languages are used to specify structure and
    access methods.

Data values stored in a databass must satisfy **consistency restraints**, which
include:
* domain constraints: domain of possible values associated with each attribute.
    Most elementary consistency restraint.
* referential integrity: ensuring that a relationship has the correct value that
    it should.
* assertions: any condition the database must always satisfy. Domain constraints
    and referential integrity are special types of assertions.
* authorization: access levels for users - read authorization, insert
    authorization, update authorization, delete authorization.

## 1.5 Relational Databases
A relational database is based on a relational model and uses a collection of
tables to represent data and relationships between data. This is an example of a
record-based model.

### 1.5.1 Tables
Each table has multiple columns and each column has a unique name.

### 1.5.2 Data-Manipulation Language
The SQL query language is nonprocedural. It takes several tables as inputs and
returns a single table.

### 1.5.3 Data-Definition Language
SQL provides a rich DDL for defining tables, integrity constraints, assertions,
etc. The following statement is an example.

```sql
create table department
    (dept_name  char(20),
     building   char(15),
     budget     numeric(12,2));
```

### 1.5.4 Database Access from Application Programs
SQL is not Turing complete. It also does not support input from users, outputs
to displays, or communication over the network. Applications are used to
interact with a database in these ways. Examples include:
* APIs that send DML and DDL statements to a database and return the results.
* The Open Database Connectivity (ODBC) standard is an API that uses C. The Java
    Database Connectivity (JDBC) standard is similar, but uses Java.

## 1.6 Database Design
Database design involves the design of database schema. Modeling a database for
the needs of an enterprise requires attention to a broad set of issues.

### 1.6.1 Design Process
This step involves *what* attributes we wish to capture in the database, and
*how* to group the data to form tables.

Two ways to tackle the problem:
* Use an entity-relationship model.
* Employ normalization that takes the set of all attributes and generates a set
    of tables.

A fully developed conceptual schema indicates the functional requirements of the
enterprise. These describe kinds of operations (transactions). The process of
moving from an abstract data model to implementation is called the
**logical-design phase**. Physical features are implemented in the **physical design phase**.

### 1.6.3 The Entity-Relationship Model
The E-R data model uses a collection of simple objects (*entities*) and
*relationships* among these objects to describe the data. Entities have
attributes. A relationship is an association among several entities. A set of
all entities is an *entity set* and a set of all relationships is called a
*relationship set*. Overall logical design can be expressed using the 
**Unified Modeling Language** (UML).

### 1.6.4 Normalization
Another method of designing a relational database is normalization. This process
generates a set of relation schemas that allow storage without unnecessary
redundancy.



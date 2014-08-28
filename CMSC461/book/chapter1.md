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

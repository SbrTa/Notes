# Database



#### ✅ How many types of database languages are?
There are four types of database languages:
  - **Data Definition Language (DDL)**: CREATE, ALTER, DROP, TRUNCATE, RENAME, etc. All these commands are used for updating the data that?s why they are known as Data Definition Language.
  - **Data Manipulation Language (DML)**: SELECT, UPDATE, INSERT, DELETE, etc. These commands are used for the manipulation of already updated data that's why they are the part of Data Manipulation Language.
  - **DATA Control Language (DCL)**: GRANT and REVOKE. These commands are used for giving and removing the user access on the database. So, they are the part of Data Control Language.
  - **Transaction Control Language (TCL)**: COMMIT, ROLLBACK, and SAVEPOINT. These are the commands used for managing transactions in the database. TCL is used for managing the changes made by DML.


#### ✅ Database normalization
Normalization is a process of analysing the given relation schemas according to their functional dependencies. It is used to minimize redundancy and also used to minimize insertion, deletion and update distractions. Normalization is considered as an essential process as it is used to avoid data redundancy, insertion anomaly, updation anomaly, deletion anomaly.

There most commonly used normal forms are:
  - **First Normal Form (1NF):**
    - Every column must have single value
    - No duplicate columns
    - Create separate tables for each group of related data
  - **Second Normal Form (2NF)**
    - 1NF
    - Has no partial dependency. All non-key attributes are fully dependent on a primary key.
  - **Third Normal Form (3NF)**
    - 2NF
    - No transitive dependencies.
  - **Boyce & Codd Normal Form (BCNF)**
    - 3NF
    - For each functional dependency ( X → Y ), X should be a Super Key.
  - **Fourth Normal Form (4NF)**
    - BCNF
    - Tables cannot have multi-valued dependencies on a Primary Key.
  - **Fifth Normal Form (5NF)**
    - 4NF
    - A composite key shouldn't have any cyclic dependencies.

#### ✅ Partial Dependency?
When a table has a primary key that is made up of two or more columns, then all the columns(not included in the primary key) in that table should depend on the entire primary key and not on a part of it. If any column(which is not in the primary key) depends on a part of the primary key then we say we have Partial dependency in the table.

#### ✅ What is Transitive Dependency?
In a table we have some column that acts as the primary key and other columns depends on this column. But what if a column that is not the primary key depends on another column that is also not a primary key or part of it? Then we have Transitive dependency in our table.

#### ✅ What is Multi-valued Dependency?
If For a dependency A → B, if for a single value of A, multiple value of B exists, then the table may have multi-valued dependency.


#### ✅ Explain ACID properties
ACID properties are some basic rules, which has to be satisfied by every transaction to preserve the integrity. These properties and rules are:

**ATOMICITY**: The entire transaction takes place at once or doesn’t happen at all. There is no midway i.e. transactions do not occur partially. Each transaction is considered as one unit and either runs to completion or is not executed at all. It involves the following two operations. 
  - Abort: If a transaction aborts, changes made to the database are not visible. 
  - Commit: If a transaction commits, changes made are visible. 

Atomicity is also known as the ‘All or nothing rule’. 

**CONSISTENCY**: Integrity constraints must be maintained so that the database is consistent before and after the transaction. It refers to the correctness of a database.

**ISOLATION**: Multiple transactions can occur concurrently without leading to the inconsistency of the database state. Transactions occur independently without interference. Changes occurring in a particular transaction will not be visible to any other transaction until that particular change in that transaction is written to memory or has been committed. This property ensures that the execution of transactions concurrently will result in a state that is equivalent to a state achieved these were executed serially in some order. 

**DURABILITY**: Once the transaction has completed execution, the updates and modifications to the database are stored in and written to disk and they persist even if a system failure occurs. These updates now become permanent and are stored in non-volatile memory. The effects of the transaction, thus, are never lost. 


#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 
#### ✅ 

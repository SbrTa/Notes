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


#### ✅ Keys is database.
**Candidate Key**: The minimal set of attributes that can uniquely identify a tuple is known as a candidate key.
  - It is a minimal super key.
  - It is a super key with no repeated data is called a candidate key.
  - The minimal set of attributes that can uniquely identify a record.
  - It must contain unique values.
  - It can contain NULL values.
  - Every table must have at least a single candidate key.
  - A table can have multiple candidate keys but only one primary key.
  - The value of the Candidate Key is unique and may be null for a tuple.
  - There can be more than one candidate key in a relationship. 

**Super Key**: The set of attributes that can uniquely identify a tuple is known as Super Key.
  - Adding zero or more attributes to the candidate key generates the super key.
  - A candidate key is a super key but vice versa is not true.
  - Super Key values may also be NULL.

**Primary Key**: There can be more than one candidate key in relation out of which one can be chosen as the primary key.
  - It is a unique key.
  - It can identify only one tuple (a record) at a time.
  - It has no duplicate values, it has unique values.
  - It cannot be NULL.
  - Primary keys are not necessarily to be a single column; more than one column can also be a primary key for a table.

![image](https://github.com/SbrTa/Notes/assets/8649145/bfd8eab1-c3be-4e55-9717-439b7e01f582)

**Alternate Key**: The candidate key other than the primary key is called an alternate key.
  - All the keys which are not primary keys are called alternate keys.
  - It is a secondary key.
  - It contains two or more fields to identify two or more records.
  - These values are repeated.

**Composite Key**: Sometimes, a table might not have a single column/attribute that uniquely identifies all the records of a table. To uniquely identify rows of a table, a combination of two or more columns/attributes can be used.  It still can give duplicate values in rare cases. So, we need to find the optimal set of attributes that can uniquely identify rows in a table.
  - It acts as a primary key if there is no primary key in a table
  - Two or more attributes are used together to make a composite key.
  - Different combinations of attributes may give different accuracy in terms of identifying the rows uniquely.

**Foreign key**: The Foreign key is a primary key from one table, which has a relationship with another table. It acts as a cross-reference between tables.

![image](https://github.com/SbrTa/Notes/assets/8649145/71a9614d-beea-4f05-92b2-91c87755f800)


#### ✅ What is Data Warehousing?
The process of collecting, extracting, transforming, and loading data from multiple sources and storing them in one database is known as data warehousing. A data warehouse can be considered as a central repository where data flows from transactional systems and other relational databases and is used for data analytics. A data warehouse comprises a wide variety of an organization’s historical data that supports the decision-making process in an organization.

![image](https://github.com/SbrTa/Notes/assets/8649145/e63d1340-57e6-4e63-b5a0-375c5a12bfaa)


#### ✅ What is a lock. Explain the major difference between a shared lock and an exclusive lock during a transaction in a database.
A database lock is a mechanism to protect a shared piece of data from getting updated by two or more database users at the same time. When a single database user or session has acquired a lock then no other database user or session can modify that data until the lock is released.

**Exclusive locks**: The exclusive locks are useful in DML operations like INSERT, UPDATE, or DELETE statements. This lock, when imposed on a transaction, prevents other persons from accessing the locked resources. It means that an exclusive lock can hold only one transaction on a resource at the same time. The user of this lock is known as a writer. This lock is imposed when the transaction wants to modify the page or row data. It can only be held by the page or row when there is no other shared or exclusive lock hold on the target.

**Shared Locks**: Once the shared locks are applied on the page or row, they will be reserved for reading-only purposes. It implies that no other transaction can alter the locked resource as long as the lock is active. As the name implies, several transactions can hold this lock on the same resource simultaneously. The user of this lock is known as a reader. In addition, this lock will also allow write operations, but no DDL changes will be permitted.

#### ✅ SQL join
A JOIN clause is used to combine rows from two or more tables, based on a related column between them.

Here are the different types of the JOINs in SQL:
  - **(INNER) JOIN**: Returns records that have matching values in both tables
  - **LEFT (OUTER) JOIN**: Returns all records from the left table, and the matched records from the right table
  - **RIGHT (OUTER) JOIN**: Returns all records from the right table, and the matched records from the left table
  - **FULL (OUTER) JOIN**: Returns all records when there is a match in either left or right table

More on - https://www.geeksforgeeks.org/sql-join-set-1-inner-left-right-and-full-joins/


#### ✅ Explain database transaction isolation levels.
Database transaction isolation levels define the degree to which one transaction must be isolated from the effects of other concurrent transactions. These levels ensure the consistency and integrity of the database during concurrent access.

Transaction isolation level is defined by the following phenomena
  - **Data Lose** 
  - **Dirty Reads**
    - A transaction reads data written by a concurrent uncommitted transaction.
    - For example, Let’s say transaction 1 updates a row and leaves it uncommitted, meanwhile, Transaction 2 reads the updated row. If transaction 1 rolls back the change, transaction 2 will have read data that is considered never to have existed.
  - **Non-Repeatable Reads, and Read Skew**
    - A transaction re-reads data it has previously read and finds that data has been modified by another transaction.
    - For example, suppose transaction T1 reads data. Due to concurrency, another transaction T2 updates the same data and commit, Now if transaction T1 rereads the same data, it will retrieve a different value.
  - **Phantom Reads**
    - A transaction re-executes a query returning a set of rows that satisfy a search condition and finds that the set of rows satisfying the condition has changed due to another recently-committed transaction.
    - For example, suppose transaction T1 retrieves a set of rows that satisfy some search criteria. Now, Transaction T2 generates some new rows that match the search criteria for transaction T1. If transaction T1 re-executes the statement that reads the rows, it gets a different set of rows this time.



Based on these phenomena, There are four SQL standard isolation levels:
  - **Read Uncommitted** – Read Uncommitted is the lowest isolation level. At this level, makes sure no transaction can update a database row if another transaction has already updated it and not committed. This protects against lost updates, but won’t stand in a way of dirty reads
  - **Read Committed** – This isolation level does not allow any other transaction to write or read a row to which another transaction has written to but not yet committed. Thus it does not allows dirty read. The transaction holds a read or write lock on the current row, and thus prevents other transactions from reading, updating, or deleting it.
  - **Repeatable Read** – This isolation level makes sure any transaction that reads data from a row blocks any other writing transactions from accessing the same row. This is the most restrictive isolation level that holds read locks on all rows it references and writes locks on all rows it inserts, updates, or deletes. Since other transactions cannot read, update or delete these rows, consequently it avoids non-repeatable read.
  - **Serializable** – This isolation level is the highest isolation level. serializable isolation level requires a lot more than restricting access to a single row. Typically this isolation mode would lock the whole table, to prevent any other transactions from inserting or reading data from it. Serializable execution is defined to be an execution of operations in which concurrently executing transactions appears to be serially executing.

**SNAPSHOT**: SQL Server introduced extensions to the SQL-92 standard isolation levels with the introduction of the SNAPSHOT isolation level.

SNAPSHOT isolation specifies that data read within a transaction will never reflect changes made by other simultaneous transactions. The transaction uses the data row versions that exist when the transaction begins. No locks are placed on the data when it is read, so SNAPSHOT transactions do not block other transactions from writing data. Transactions that write data do not block snapshot transactions from reading data. You need to enable snapshot isolation by setting the ALLOW_SNAPSHOT_ISOLATION database option in order to use it.

![image](https://github.com/SbrTa/Notes/assets/8649145/3f1a1bc1-ca00-4d81-a9cf-207510006d67)

#### ✅ What is deadlock in database and how it can be resolved?
Deadlock occurs when two or more transactions are waiting for each other to release resources, such as locks on database objects, that they need to complete their operations. As a result, none of the transactions can proceed, leading to a situation where they are stuck or “deadlocked.”

Resolution of Deadlocks:
  - **Timeouts**: Set a timeout for transactions. If a transaction cannot acquire all the necessary locks within a specified time, it will be rolled back. This approach helps to break deadlocks, but it may also lead to the loss of work.
  - **Lock Hierarchy**: Establish a hierarchy for acquiring locks. If transactions follow a predefined order when acquiring locks, the likelihood of deadlocks can be reduced.
  - **Two-Phase Locking Protocol**: Enforce a two-phase locking protocol where a transaction must acquire all the locks it needs before it can release any. This helps to prevent circular wait conditions, a common cause of deadlocks.
  - **Avoidance**: Use a method to determine whether a transaction should wait for a lock based on an analysis of the potential for a deadlock. This requires careful planning and understanding of transaction requirements.
  - **Deadlock Detection and Resolution**: Periodically check for deadlocks and, if detected, choose one or more transactions to be rolled back. The decision on which transaction to roll back may involve factors like the transaction's priority or the amount of work done.
  - **Resource Allocation Graph**: Use a resource allocation graph to represent the relationships between transactions and resources. Periodically check the graph for cycles, which indicate deadlocks, and take appropriate action.

#### ✅ Optimistic and Pessimistic locking
**Optimistic locking**:
The optimistic locking model, also referred to as optimistic concurrency control, is a concurrency control method used in relational databases that does not use record locking. Optimistic locking allows multiple users to attempt to update the same record without informing the users that others are also attempting to update the record. The record changes are validated only when the record is committed. If one user successfully updates the record, the other users attempting to commit their concurrent updates are informed that a conflict exists.

An advantage of the optimistic locking model is that it avoids the overhead of locking a record for the duration of the action. If there are no simultaneous updates, then this model provides fast updates.

Optimistic locking is a useful approach when concurrent record updates are expected to be infrequent or the locking overhead is high. In the Rational ClearQuest implementation of optimistic locking, when multiple users edit a record concurrently, after one user's changes are committed, the other users' changes are rejected and data conflicts must be saved and manually merged.

**Pessimistic locking**:
The pessimistic locking model prevents simultaneous updates to records. As soon as one user starts to update a record, a lock is placed on it. Other users who attempt to update this record are informed that another user has an update in progress. The other users must wait until the first user has finished committing their changes, thereby releasing the record lock. Only then can another user make changes based on the previous user's changes.

An advantage of the pessimistic locking model is that it avoids the issue of conflict resolution by preventing conflicts. Updates are serialized and each subsequent update starts with the committed record changes from the previous user.

Pessimistic locking is a useful approach when subsequent updates can be delayed until a previous update is completed. This usually implies that updates occur in a short time interval.

#### ✅ How does a database ensures consistency during concurrent transaction?

A database ensures consistency during concurrent transactions through various mechanisms and isolation levels that control the interactions between transactions. The goal is to maintain the ACID properties (Atomicity, Consistency, Isolation, Durability) even when multiple transactions are executing simultaneously. Here's how a database achieves consistency during concurrent transactions:

**Transactions:**
A transaction is a unit of work that represents a sequence of one or more operations. Transactions are executed atomically, meaning they are either completed in their entirety or not at all. This ensures that the database remains in a consistent state.

**Isolation Levels:**
Isolation levels define the degree to which one transaction must be isolated from the effects of other concurrent transactions. The different isolation levels (Read Uncommitted, Read Committed, Repeatable Read, Serializable) provide varying levels of consistency and isolation.

**Locking Mechanisms:**
Databases use locking mechanisms to control access to data and prevent conflicts. When a transaction wants to read or modify a piece of data, it must acquire a lock on that data. This ensures that only one transaction at a time can modify a particular data item.

**Concurrency Control:**
Concurrency control mechanisms ensure that transactions can execute concurrently without compromising data consistency. Two commonly used concurrency control techniques are optimistic concurrency control and pessimistic concurrency control.
  - Optimistic Concurrency Control
  - Pessimistic Concurrency Control

**Transaction Isolation:**
  - The isolation property of transactions ensures that the intermediate state of a transaction is not visible to other transactions until the transaction is committed. This prevents uncommitted changes from affecting other transactions and maintains a consistent view of the database.

**Serializability:**
  - Serializability is a key concept in database consistency. It ensures that the execution of a set of concurrent transactions is equivalent to some serial execution of those transactions. In other words, even though transactions may execute concurrently, the end result is as if they were executed one after the other.

**Rollback and Undo Mechanisms:**
  - If a transaction encounters an error or if a conflict arises during execution, the database can roll back the transaction to its previous state. Undo mechanisms are used to reverse the effects of partially completed transactions.


#### ✅ What is a savepoint in a database transaction?
A savepoint is a named entity that represents the state of data and schemas at a particular point within a unit of work. You can create savepoints within a transaction. If the transaction rolls back, changes are undone to the specified savepoint, rather than to the beginning of the transaction.


#### ✅ What is an Aggregate Function in SQL?
An aggregate function in SQL returns one value after calculating multiple values of a column. We often use aggregate functions with the GROUP BY and HAVING clauses of the SELECT statement.

There are 5 types of SQL aggregate functions:
- Count()
- Sum()
- Avg()
- Min()
- Max()

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

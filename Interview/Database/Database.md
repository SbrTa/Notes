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

#### ✅ Partial Dependency?
When a table has a primary key that is made up of two or more columns, then all the columns(not included in the primary key) in that table should depend on the entire primary key and not on a part of it. If any column(which is not in the primary key) depends on a part of the primary key then we say we have Partial dependency in the table.

#### ✅ What is Transitive Dependency?
In a table we have some column that acts as the primary key and other columns depends on this column. But what if a column that is not the primary key depends on another column that is also not a primary key or part of it? Then we have Transitive dependency in our table.


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
#### ✅ 
#### ✅ 

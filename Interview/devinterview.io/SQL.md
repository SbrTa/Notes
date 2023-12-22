# SQL Fundamentals

#### ✅ 1. What is SQL and what is it used for?
Answer: SQL (Structured Query Language) is a domain-specific language used to manage and manipulate relational databases. It is employed for tasks such as querying data, updating records, inserting new data, and controlling database access.

#### ✅ 2. Describe the difference between SQL and NoSQL databases.
Answer: SQL databases are relational databases that use a structured schema, while NoSQL databases are non-relational and typically do not require a fixed schema. SQL databases use SQL for querying, whereas NoSQL databases use various query languages.

#### ✅ 3. What are the different types of SQL commands?
Answer: SQL commands can be categorized into Data Query Language (DQL), Data Definition Language (DDL), Data Manipulation Language (DML), and Data Control Language (DCL).

#### ✅ 4. Explain the purpose of the SELECT statement.
Answer: The SELECT statement is used to retrieve data from one or more tables in a database. It allows you to specify the columns you want to retrieve and apply conditions to filter the results.

#### ✅ 5. What is the difference between WHERE and HAVING clauses?
Answer: The WHERE clause is used in a SELECT statement to filter rows before grouping or aggregating. The HAVING clause is used with GROUP BY to filter the results after grouping.

#### ✅ 6. Define what a JOIN is in SQL and list its types.
Answer: JOIN is used to combine rows from two or more tables based on a related column. Types of JOIN include INNER JOIN, LEFT JOIN, RIGHT JOIN, and FULL JOIN.

#### ✅ 7. What is a primary key in a database?
Answer: A primary key is a unique identifier for a record in a table. It ensures each row can be uniquely identified and is used to establish relationships between tables.

#### ✅ 8. Explain what a foreign key is and how it is used.
Answer: A foreign key is a column that establishes a link between data in two tables. It enforces referential integrity, ensuring that values in the foreign key column correspond to values in the primary key of another table.

#### ✅ 9. How can you prevent SQL injections?
Answer: To prevent SQL injections, use parameterized queries, input validation, and prepared statements. Avoid concatenating user inputs directly into SQL queries.

#### ✅ 10. What is normalization? Explain with examples.
Answer: Normalization is the process of organizing data to reduce redundancy and improve data integrity. For example, breaking a table with customer information into separate tables for customers and orders.

#### ✅ 11. Describe the concept of denormalization and when you would use it.
Answer: Denormalization involves intentionally introducing redundancy to a database to improve query performance. It is used when there is a need for faster read operations and data integrity can be sacrificed to some extent.

#### ✅ 12. What are indexes and how can they improve query performance?
Answer: Indexes are data structures that provide a quick lookup of rows in a table based on the values in one or more columns. They improve query performance by allowing the database engine to locate and retrieve data more efficiently.

#### ✅ 13. Explain the purpose of the GROUP BY clause.
Answer: The GROUP BY clause is used to group rows returned by a query based on the values of one or more columns. It is often used with aggregate functions to perform operations on each group.

#### ✅ 14. What is a subquery, and when would you use one?
Answer: A subquery is a query nested within another query. It is used to retrieve data that will be used by the main query. Subqueries can be used in SELECT, FROM, WHERE, and HAVING clauses.

#### ✅ 15. Describe the functions of the ORDER BY clause.
Answer: The ORDER BY clause is used to sort the result set of a query based on one or more columns, either in ascending (ASC) or descending (DESC) order.

#### ✅ 16. What are aggregate functions in SQL?
Answer: Aggregate functions perform a calculation on a set of values and return a single value. Examples include COUNT, SUM, AVG, MIN, and MAX.

#### ✅ 17. Elucidate the differences between INNER JOIN, LEFT JOIN, RIGHT JOIN, and FULL JOIN.
Answer: INNER JOIN returns only the matched rows between two tables. LEFT JOIN returns all rows from the left table and the matched rows from the right table. RIGHT JOIN returns all rows from the right table and the matched rows from the left table. FULL JOIN returns all rows when there is a match in either the left or right table.

#### ✅ 18. How do you insert a new row into a database table?
Answer: To insert a new row, use the INSERT INTO statement followed by the table name and values for each column.

#### ✅ 19. Explain how to update records in a database table.
Answer: To update records, use the UPDATE statement with the SET clause to specify the new values, and use the WHERE clause to identify the records to be updated.

#### ✅ 20. What is a SQL View and what are its advantages?
Answer: A SQL View is a virtual table based on the result of a SELECT query. It allows users to query the view as if it were a table. Advantages include simplifying complex queries, providing a layer of security, and encapsulating business logic.



# SQL Data Types and Operators

#### ✅ 21. List the different data types available in SQL.
Answer: Common data types in SQL include INTEGER, FLOAT, CHAR, VARCHAR, TEXT, DATE, TIME, DATETIME, BOOLEAN, and more, depending on the specific database system.

#### ✅ 22. What are the differences between CHAR, VARCHAR, and TEXT data types?
Answer: CHAR is a fixed-length character type, VARCHAR is a variable-length character type, and TEXT is used for large amounts of text data. CHAR pads values with spaces, while VARCHAR stores only the actual characters entered.

#### ✅ 23. How do you use the BETWEEN operator in SQL?
Answer: The BETWEEN operator is used to filter results within a specific range. For example: `SELECT * FROM table WHERE column BETWEEN value1 AND value2;`

#### ✅ 24. Describe the use of the IN operator.
Answer: The IN operator is used to filter results based on a list of specified values. For example: `SELECT * FROM table WHERE column IN (value1, value2, ...);`

#### ✅ 25. Explain the use of wildcard characters in SQL.
Answer: Wildcard characters like '%' and '_' are used in conjunction with the LIKE operator to perform pattern matching in SQL queries. '%' represents any sequence of characters, and '_' represents a single character.

#### ✅ 26. What is the purpose of the LIKE operator?
Answer: The LIKE operator is used to search for a specified pattern in a column. It is often used with wildcard characters for flexible pattern matching.

#### ✅ 27. How do you handle NULL values in SQL?
Answer: NULL values can be handled using the IS NULL or IS NOT NULL conditions in WHERE clauses. Additionally, functions like COALESCE and IFNULL can be used to provide default values for NULLs.

#### ✅ 28. What does the COALESCE function do?
Answer: The COALESCE function is used to return the first non-NULL expression among its arguments. It is often used to handle NULL values by providing a default value.

#### ✅ 29. What is the difference between UNION and UNION ALL?
Answer: UNION combines the result sets of two queries and removes duplicate rows, while UNION ALL combines the result sets without removing duplicates.

#### ✅ 30. Describe the use of arithmetic operators in SQL queries.
Answer: Arithmetic operators (+, -, *, /) are used to perform mathematical operations on numeric data in SQL queries. For example: `SELECT column1 + column2 FROM table;`



# SQL Advanced Queries

#### ✅ 31. Explain how to use the CASE statement in SQL.
Answer: The CASE statement is used to perform conditional logic in SQL queries. It can be used in SELECT, WHERE, and ORDER BY clauses to conditionally return values based on specified conditions.

#### ✅ 32. How would you perform a self JOIN?
Answer: A self JOIN is used to combine rows from the same table. You need to use an alias to differentiate between the two instances of the same table. For example: `SELECT a.column, b.column FROM table a JOIN table b ON a.id = b.related_id;`

#### ✅ 33. What is a cross JOIN and when would you use it?
Answer: A cross JOIN returns the Cartesian product of two tables, meaning it combines each row from the first table with every row from the second table. It is used when you want to combine all rows from both tables.

#### ✅ 34. How to implement pagination in SQL queries?
Answer: Pagination can be achieved using the LIMIT and OFFSET clauses in SQL. For example: `SELECT * FROM table LIMIT 10 OFFSET 20;` retrieves the third page of 10 records.

#### ✅ 35. Explain the concept of Common Table Expressions (CTEs) and recursive CTES.
Answer: CTEs provide a way to define temporary result sets within a SELECT, INSERT, UPDATE, or DELETE statement. Recursive CTEs are used for queries that reference themselves, often used for hierarchical data.

#### ✅ 36. What are window functions and how are they used?
Answer: Window functions perform calculations across a set of table rows related to the current row. They are used with the OVER() clause and include functions like ROW_NUMBER(), RANK(), and SUM().

#### ✅ 37. How can you concatenate column values in SQL?
Answer: CONCAT() or the concatenation operator (||) can be used to concatenate column values. For example: `SELECT CONCAT(first_name, ' ', last_name) AS full_name FROM table;`

#### ✅ 38. What is the PIVOT operation and how would you apply it?
Answer: PIVOT is used to rotate rows into columns, aggregating data in the process. It involves specifying the values to be pivoted and the aggregation functions. For example: `SELECT * FROM table PIVOT (SUM(value) FOR category IN ('A', 'B', 'C'));`

#### ✅ 39. Explain the process of combining a query that uses a GROUP BY with one that uses ORDER BY.
Answer: You can combine a GROUP BY query with ORDER BY to sort the grouped results. For example: `SELECT column, COUNT(*) FROM table GROUP BY column ORDER BY COUNT(*) DESC;`

#### ✅ 40. How would you find duplicate records in a table?
Answer: To find duplicate records, you can use the GROUP BY clause along with the HAVING clause to filter groups with counts greater than one. For example: `SELECT column, COUNT(*) FROM table GROUP BY column HAVING COUNT(*) > 1;`



# Database Design & Architecture

#### ✅ 41. What is the Entity-Relationship Model?
Answer: The Entity-Relationship (ER) Model is a conceptual data model used to represent the relationships among entities in a database. It uses entities to represent real-world objects or concepts, attributes to describe properties of entities, and relationships to depict connections between entities. The model is often represented graphically using diagrams that illustrate the structure and associations within a database.

#### ✅ 42. Explain the different types of database schema.
Answer: Types of database schema include physical schema (describing the database structure), logical schema (describing data relationships), and schema-on-write or schema-on-read (determining when data structure is defined).

#### ✅ 43. What are Stored Procedures and how are they beneficial?
Answer: Stored Procedures are precompiled SQL statements stored in the database. They improve performance, code reusability, and security by encapsulating SQL code on the server side.

#### ✅ 44. What is a trigger in SQL and when should it be used?
Answer: A trigger is a set of instructions that automatically execute in response to a specific event on a particular table or view. Triggers are used to enforce business rules, integrity constraints, and automate actions.

#### ✅ 45. Describe the concept of ACID in databases.
Answer: ACID stands for Atomicity, Consistency, Isolation, and Durability. It is a set of properties ensuring database transactions are processed reliably. Atomicity ensures that transactions are treated as a single, indivisible unit; Consistency ensures data integrity; Isolation ensures transactions are independent; Durability ensures that committed transactions persist.

#### ✅ 46. What is database sharding?
Answer: Database sharding involves breaking a large database into smaller, more manageable parts called shards. Each shard is an independent database, allowing for improved scalability and performance.

#### ✅ 47. How do database indexes work and what types are there?
Answer: Indexes in databases are data structures that improve query performance by providing faster access to rows. Types include B-tree indexes, hash indexes, and bitmap indexes.

#### ✅ 48. Describe the process of data warehousing.
Answer: Data warehousing involves collecting, storing, and managing large volumes of data from various sources to support business intelligence and reporting. It often includes processes like ETL (Extract, Transform, Load).

#### ✅ 49. Explain the difference between OLTP and OLAP systems.
Answer: OLTP (Online Transaction Processing) systems are designed for transactional processing, handling day-to-day operations. OLAP (Online Analytical Processing) systems are designed for complex queries and data analysis, providing a multidimensional view of the data.

#### ✅ 50. What are materialized views and how do they differ from standard views?
Answer: Materialized views are precomputed views stored as physical objects, while standard views are virtual and dynamically generated. Materialized views improve query performance by storing the results of complex queries, reducing the need to recompute them.



# SQL Optimization and Performance

#### ✅ 51. How do you identify and optimize slow-running queries?
Answer: To identify slow-running queries, monitor database performance using tools like database profiling or monitoring tools. Optimize slow queries by analyzing execution plans, adding indexes, rewriting queries, and ensuring database statistics are up-to-date.

#### ✅ 52. What is a query execution plan in SQL?
Answer: A query execution plan is a set of steps that the database engine follows to execute a SQL query. It details how the database will retrieve data, join tables, and apply filters. Understanding and analyzing the execution plan is crucial for optimizing query performance.

#### ✅ 53. Explain how to use EXPLAIN or EXPLAIN ANALYZE.
Answer: EXPLAIN is used to display the execution plan of a SQL query without actually executing it. EXPLAIN ANALYZE goes further and executes the query, providing both the plan and actual runtime statistics. These tools help in optimizing queries by revealing how the database engine processes them.

#### ✅ 54. How can indexing affect performance both positively and negatively?
Answer: Indexing can positively impact performance by speeding up data retrieval operations. However, excessive or inappropriate indexing can negatively affect performance by slowing down write operations, increasing storage requirements, and adding complexity to maintenance tasks.

#### ✅ 55. Describe how to measure the performance of SQL queries.
Answer: Performance can be measured using tools like database profilers, query execution plans, and monitoring tools. Metrics such as execution time, CPU usage, and I/O operations provide insights into query performance.

#### ✅ 56. How would you rewrite a query to improve its performance?
Answer: To improve query performance, consider optimizing the query structure, adding appropriate indexes, avoiding unnecessary joins, and optimizing WHERE clauses. It may also involve rewriting complex subqueries or using appropriate JOIN types.

#### ✅ 57. What are partitioned tables and how can they optimize performance?
Answer: Partitioned tables divide large tables into smaller, more manageable segments called partitions based on a specified column or set of columns. Partitioning can improve query performance by allowing the database to access only the relevant partitions, reducing the amount of data to scan.



# SQL Security

#### ✅ 58. How do you implement database encryption in SQL?
Answer: Database encryption in SQL can be implemented using Transparent Data Encryption (TDE) to encrypt the entire database at rest. Additionally, Always Encrypted can be used to encrypt specific columns containing sensitive data, ensuring encryption throughout the data lifecycle.

#### ✅ 59. What are roles and how do they manage database access?
Answer: Roles in SQL are named groups of related permissions assigned to users. They simplify the management of database access by allowing the assignment of permissions to roles, and users can then be added to roles. This simplifies access control and ensures consistent permissions across users.

#### ✅ 60. Explain the concept of row-level security.
Answer: Row-level security (RLS) is a feature that allows fine-grained control over access to rows in a database table based on user characteristics or roles. It ensures that users can only access the data that is relevant to their role or permissions, enhancing data security.

#### ✅ 61. Describe how to create and use user-defined functions (UDFs).
Answer: User-defined functions (UDFs) are custom functions created by users to encapsulate a specific logic or computation. They can be scalar, table-valued, or multi-statement functions. To create a UDF, use the CREATE FUNCTION statement, and to use it, call the function in SELECT, WHERE, or other clauses in a query.


# SQL Functions and Expressions

#### ✅ 62. Describe scalar-valued and table-valued functions.
Answer: 
- Scalar-valued functions return a single value, and they can be used in expressions or SELECT statements. Example: `CREATE FUNCTION dbo.GetTotalSales(@productId INT) RETURNS DECIMAL AS ...`

- Table-valued functions return a table as the result. They can be used in the FROM clause of a query. Example: `CREATE FUNCTION dbo.GetSalesByCategory(@categoryId INT) RETURNS TABLE AS ...`

#### ✅ 63. How would you define a stored procedure with input and output parameters?
Answer: 
To define a stored procedure with input and output parameters, use the CREATE PROCEDURE statement. For example:

```sql
CREATE PROCEDURE dbo.GetEmployeeName
    @employeeId INT,
    @firstName NVARCHAR(50) OUTPUT,
    @lastName NVARCHAR(50) OUTPUT
AS
BEGIN
    SELECT @firstName = FirstName, @lastName = LastName
    FROM Employees
    WHERE EmployeeID = @employeeId;
END;
```

#### ✅ 64. What is the difference between a function and a stored procedure?
Answer: 
- **Return Value:**
  - Functions return a value, which can be a scalar value or a table.
  - Stored procedures may return values using OUTPUT parameters, but they are not required to return a value.

- **Usage:**
  - Functions are designed for use in SELECT, WHERE, and other clauses.
  - Stored procedures are designed to perform an action, and they are typically called using the EXECUTE or EXEC keyword.

- **Use in SELECT Statement:**
  - Functions can be used directly in a SELECT statement.
  - Stored procedures cannot be used directly in a SELECT statement; they need to be executed using the EXECUTE keyword.

#### ✅ 65. How do you use the CAST and CONVERT functions?
Answer: 
Both CAST and CONVERT functions in SQL are used to change the data type of an expression or a value. For example:

Using CAST:
  ```sql
  SELECT CAST('2023-01-01' AS DATE);
  ```
This statement converts the string '2023-01-01' to a DATE data type.

Using CONVERT:
```sql
SELECT CONVERT(VARCHAR, GETDATE(), 120);
```
This statement converts the current date and time to a VARCHAR data type using the format style 120.
These functions are particularly useful when you need to change the data type for compatibility or formatting purposes.




# Transaction Control and Locking

66. What is a database transaction?
67. Explain the concept of locking and its types in SQL databases.
68. What are the properties of transactions?
69. How do you manage transaction isolation levels?
70. What does it mean to commit or roll back a transaction?


# SQL and Modern Data Ecosystems

71. How can SQL be integrated with big data technologies?
72. Discuss the interoperability of SQL with cloud-based data stores.
73. What is Data Lake and how can SQL interact with it?
74. Explain the interaction between SQL and NoSQL within the same application.
75. How does SQL work within a microservices architecture?


# SQL Best Practices and Standards

76. What are some common SQL coding practices you follow?
77. How can you ensure the portability of SQL scripts across different database systems?
78. What methods do you use for version controlling SQL scripts?
79. What are the benefits of using stored procedures instead of embedding SQL queries in code?
80. How do you document SQL code effectively?


# Analytical SQL Questions

81. How would you find the Nth highest salary from a table?
82. How do you count the number of occurrences of a specific value in a column?
83. How can you calculate running totals in SQL?
84. Explain how to reverse the contents of a column without using a reverse function.
85. What approach do you use for creating a calendar table, and what are its uses?


# Data Manipulation and ETL

86. What is the process of Extract, Transform, Load (ETL)?
87. How do you import/export data from/to a flat file using SQL?
88. Explain the steps for a basic ETL process in a data warehousing environment.
89. How do you cleanse and format data using SQL queries?
90. What tools do you use for automating data import/export routines?


# Domain-Specific SQL Scenarios

91. How would you model a many-to-many relationship in SQL?
92. Describe how to manage hierarchical data in SQL.
93. How would you approach writing SQL queries for a reporting application?
94. Explain how to handle temporal data and time zones in SQL.
95. How do you use SQL in financial applications for risk and portfolio analysis?


# Troubleshooting and Debugging

96. What steps do you take to troubleshoot a failed SQL query?
97. How can you recover data from a corrupt SQL database?
98. What methods do you employ to ensure data integrity?
99. How do you decipher and resolve deadlocks in SQL?


# Advanced Data Analysis in SQL

100. Explain how to use SQL for predictive analysis and machine learning purposes.

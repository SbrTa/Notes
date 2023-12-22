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

31. Explain how to use the CASE statement in SQL.
32. How would you perform a self JOIN?
33. What is a cross JOIN and when would you use it?
34. How to implement pagination in SQL queries?
35. Explain the concept of Common Table Expressions (CTEs) and recursive CTES.
36. What are window functions and how are they used?
37. How can you concatenate column values in SQL?
38. What is the PIVOT operation and how would you apply it?
39. Explain the process of combining a query that uses a GROUP BY with one that uses ORDER BY.
40. How would you find duplicate records in a table?


# Database Design & Architecture

41. What is the Entity-Relationship Model?
42. Explain the different types of database schema.
43. What are Stored Procedures and how are they beneficial?
44. What is a trigger in SQL and when should it be used?
45. Describe the concept of ACID in databases.
46. What is database sharding?
47. How do database indexes work and what types are there?
48. Describe the process of data warehousing.
49. Explain the difference between OLTP and OLAP systems.
50. What are materialized views and how do they differ from standard views?


# SQL Optimization and Performance

51. How do you identify and optimize slow-running queries?
52. What is query execution plan in SQL?
53. Explain how to use EXPLAIN or EXPLAIN ANALYZE.
54. How can indexing affect performance both positively and negatively?
55. Describe how to measure the performance of SQL queries.
56. How would you rewrite a query to improve its performance?
57. What are partitioned tables and how can they optimize performance?


# SQL Security

58. How do you implement database encryption in SQL?
59. What are roles and how do they manage database access?
60. Explain the concept of row-level security.
61. Describe how to create and use user-defined functions (UDFs).


# SQL Functions and Expressions

62. Describe scalar-valued and table-valued functions.
63. How would you define a stored procedure with input and output parameters?
64. What is the difference between a function and a stored procedure?
65. How do you use the CAST and CONVERT functions?


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

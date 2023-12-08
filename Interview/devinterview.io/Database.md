
# Database Fundamentals

#### ✅ 1. What is a database management system (DBMS), and can you name some examples?
**Answer:**
- **DBMS Definition:**
  - A Database Management System (DBMS) is software that facilitates the creation, organization, and management of databases. It provides an interface for interacting with databases, performing operations like data insertion, retrieval, modification, and deletion.
- **Examples of DBMS:**
  - SQL-based: MySQL, PostgreSQL, Oracle Database
  - NoSQL: MongoDB, Cassandra, Couchbase

#### ✅ 2. Explain the ACID properties in the context of databases.
**Answer:**
- **ACID Properties:**
  - **Atomicity:**
    - Ensures that database transactions are treated as a single, indivisible unit, either fully completed or fully rolled back in case of failure.
  - **Consistency:**
    - Guarantees that the database remains in a consistent state before and after the transaction, adhering to defined constraints.
  - **Isolation:**
    - Ensures that the execution of transactions is isolated from each other, preventing interference and maintaining the illusion that each transaction runs independently.
  - **Durability:**
    - Ensures that once a transaction is committed, its changes are permanent and survive any subsequent system failures.

#### ✅ 3. What are the differences between SQL and NoSQL databases?
**Answer:**
- **SQL Databases:**
  - Structured Query Language databases with a predefined schema.
  - Suitable for complex queries and transactions.
  - Examples: MySQL, PostgreSQL, Oracle.
- **NoSQL Databases:**
  - Schema-less databases, suitable for unstructured or semi-structured data.
  - Scalable and flexible.
  - Types: Document-oriented (MongoDB), Key-value (Redis), Column-family (Cassandra).

#### ✅ 4. Describe a relational database schema.
**Answer:**
- **Relational Database Schema:**
  - A relational database schema defines the structure of the database, including tables, fields, relationships, and constraints.
  - Components:
    - **Table:** Represents an entity.
    - **Column:** Represents an attribute of the entity.
    - **Primary Key:** Unique identifier for each record.
    - **Foreign Key:** Establishes relationships between tables.

#### ✅ 5. What is a primary key, and why is it important?
**Answer:**
- **Primary Key:**
  - A primary key is a unique identifier for each record in a database table.
  - Importance:
    - Ensures data integrity by preventing duplicate records.
    - Facilitates quick and efficient data retrieval.
    - Serves as a reference in establishing relationships between tables.

#### ✅ 6. Can you explain what a foreign key is and its role in the database?
**Answer:**
- **Foreign Key:**
  - A foreign key is a field in a database table that refers to the primary key in another table.
  - Role:
    - Establishes relationships between tables by linking data.
    - Enforces referential integrity, ensuring consistency between related tables.

#### ✅ 7. What is database normalization, and why do we use it?
**Answer:**
- **Database Normalization:**
  - Database normalization is the process of organizing data in a database to reduce redundancy and improve data integrity.
  - Reasons for Use:
    - Minimize data duplication.
    - Prevent update anomalies.
    - Simplify data maintenance.

#### ✅ 8. What is denormalization and when would you consider it?
**Answer:**
- **Denormalization:**
  - Denormalization is the process of intentionally introducing redundancy into a database by combining tables or adding redundant data.
  - Considerations:
    - Used to optimize read performance in situations where frequent and complex queries are performed.
    - Suitable for scenarios where data retrieval speed outweighs the cost of increased storage and potential update anomalies.

#### ✅ 9. Compare and contrast the DROP, DELETE, and TRUNCATE commands.
**Answer:**
- **DROP:**
  - Used to delete a table or a database.
- **DELETE:**
  - Used to delete specific rows from a table based on a condition.
  - Generates transaction logs.
- **TRUNCATE:**
  - Used to remove all rows from a table.
  - Faster than DELETE but doesn't generate transaction logs.

#### ✅ 10. What is the difference between a full join and an inner join?
**Answer:**
- **Inner Join:**
  - Returns rows where there is a match in both tables based on the specified condition.
- **Full Join (or Full Outer Join):**
  - Returns all rows when there is a match in either the left or right table.
  - Includes unmatched rows from both tables.



# SQL and Query Optimization

#### ✅ 11. How would you write an SQL query to fetch duplicate records from a table?
**Answer:**
```sql
SELECT column_name, COUNT(*)
FROM table_name
GROUP BY column_name
HAVING COUNT(*) > 1;
```

#### ✅ 12. What is a prepared statement, and why would you use one?
**Answer:**
- **Prepared Statement:**
  - A prepared statement is a feature in database systems that allows SQL queries to be precompiled before execution.
- **Reasons to Use:**
  - **Performance:** Reduces parsing overhead by reusing the execution plan.
  - **Security:** Helps prevent SQL injection attacks by automatically handling parameterization.

#### ✅ 13. What is the N+1 query problem and how can you solve it?
**Answer:**
- **N+1 Query Problem:**
  - Occurs when accessing a collection of entities results in N+1 individual queries to the database (N queries to retrieve the collection and 1 query for each related entity).
- **Solution:**
  - Use eager loading or fetching strategies, such as JOIN FETCH in JPA/Hibernate, to retrieve related entities along with the main query, reducing the need for additional queries.

#### ✅ 14. Explain the function of GROUP BY and HAVING clauses in SQL.
**Answer:**
- **GROUP BY Clause:**
  - Groups rows based on specified columns.
  - Used with aggregate functions like COUNT, SUM, AVG, etc.
- **HAVING Clause:**
  - Filters grouped rows based on specified conditions.
  - Applied after the GROUP BY clause to filter aggregated results.

#### ✅ 15. What are indexes and how do they work in databases?
**Answer:**
- **Indexes:**
  - Indexes are data structures that provide a quick lookup of rows in a table based on the values of one or more columns.
- **How They Work:**
  - Improve query performance by allowing the database engine to locate and retrieve specific rows more efficiently.
  - Types include B-tree, Hash, and Bitmap indexes.

#### ✅ 16. What impact do JOIN operations have on database performance?
**Answer:**
- **JOIN Impact on Performance:**
  - JOIN operations can impact performance by increasing the complexity and execution time of queries.
  - Efficient indexing, proper query design, and choosing the appropriate JOIN type (e.g., INNER JOIN, LEFT JOIN) help mitigate performance issues.

#### ✅ 17. Define what a subquery is and provide a use case for it.
**Answer:**
- **Subquery:**
  - A subquery is a query nested within another query, usually enclosed in parentheses.
- **Use Case:**
  - **Example: Find employees with salaries above the average salary.**
    ```sql
    SELECT employee_name
    FROM employees
    WHERE salary > (SELECT AVG(salary) FROM employees);
    ```


#### ✅ 18. What is a correlated subquery?
**Answer:**
- **Correlated Subquery:**
  - A correlated subquery is a subquery that depends on the outer query for its values. It references columns from the outer query, creating a dependency between the two.
- **Example: Find employees with salaries above their department's average.**
```sql
  SELECT employee_name
  FROM employees e1
  WHERE salary > (SELECT AVG(salary) FROM employees e2 WHERE e1.department_id = e2.department_id);
```

#### ✅ 19. Describe how you would optimize a slow SQL query.
**Answer:**
- **Optimizing a Slow SQL Query:**
  1. **Indexing:** Ensure relevant columns are indexed to speed up data retrieval.
  2. **Query Rewriting:** Rewrite the query to use efficient JOINs and WHERE clauses.
  3. **Limit Result Set:** Retrieve only necessary columns and rows.
  4. **Use Stored Procedures:** Precompiled and optimized for repeated execution.
  5. **Update Statistics:** Keep database statistics up-to-date for the query optimizer.
  6. **Partitioning:** If dealing with large tables, consider partitioning for better performance.

#### ✅ 20. Explain the EXPLAIN statement and how you use it in query optimization.
**Answer:**
- **EXPLAIN Statement:**
  - The EXPLAIN statement is used to obtain information about how a SELECT statement would be executed by the database engine.
- **Usage in Query Optimization:**
  - Provides insights into the query execution plan, including the order of table access, JOIN methods, and index usage.
  - Helps identify areas for optimization by understanding how the database engine processes the query.
  - Example:
    ```sql
    EXPLAIN SELECT * FROM employees WHERE department_id = 10;
    ```

# Data Modeling and Design

21. What is an Entity-Relationship (ER) model, and why is it useful?
22. Describe the process of converting an ER model into a relational database schema.
23. How do you design a scalable database schema for a high-traffic application?
24. What is database sharding, and what are its benefits and drawbacks?
25. Explain the term "data integrity" and how it's enforced in databases.

# Transactions and Concurrency Control

26. Can you explain the concept of transaction isolation levels?
27. What is a deadlock in databases, and how can it be resolved?
28. Describe optimistic vs. pessimistic locking.
29. How does a database ensure consistency during concurrent transactions?
30. What is a savepoint in a database transaction?

# Database Security

31. What is SQL injection, and how do you prevent it?
32. Explain the role of access control in database security.
33. What are the best practices for storing passwords in a database?
34. How do you secure data transmission to and from a database?
35. Describe the use of encryption within databases for data at rest.

# Backup and Recovery

36. What is a database snapshot, and when would you use one?
37. Explain the difference between logical and physical backups.
38. How would you restore a database from a backup file?
39. What are the common strategies for database disaster recovery?
40. How does point-in-time recovery work in databases?

# Performance Tuning and Scaling

41. How would you handle a scenario where your database's read load significantly increases?
42. What strategies exist for scaling writes in a high-volume database system?
43. Describe how connection pooling benefits database performance.
44. How do you monitor and identify database performance bottlenecks?
45. What is horizontal and vertical scaling in databases?

# NOSQL Databases

46. Explain what a document store is and give an example of where it's appropriate to use.
47. What is a graph database, and what are its typical use cases?
48. Describe the key-value store model and its typical applications.
49. How do you choose between consistency and availability in a NoSQL database, referencing the CAP theorem?
50. What is eventual consistency, and in what scenarios is it used?

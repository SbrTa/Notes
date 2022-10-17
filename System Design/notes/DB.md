# Database

Performance is extremely important in many consumer products like e-commerce, payment systems, gaming, transportation apps, and so on. Although databases are internally optimised through multiple mechanisms to meet their performance requirements in the modern world, a lot depends on the application developer as well — after all, only a developer knows what queries the application has to perform.



## Index
Developers who deal with relational databases have used or at least heard about indexing, and it’s a very common concept in the database world. However, the most important part is to understand what to index & how the indexing is going to boost the query response time. For doing that you need to understand how you are going to query your database tables. A proper index can be created only when you know exactly what your query & data access patterns look like.
  - Index is basically storage-time trade off
  - a data structure (B Tree) on top of actual table
  - more storage
  - faster read query, slower write/update query
  - Precalculate data (have to study)

```
explain analyse select * from person;

create index person_first_name on person(first_name);

explain analyse select * from person where first_name = 'Ali';

explain analyse select * from person where last_name = 'Adams';

explain analyse select * from person where first_name = 'Ali' and last_name = 'Adams';

explain analyse select * from person where first_name = 'Ali' or last_name = 'Adams';

create index person_full_name on person(first_name,last_name);

select pg_table_size('person')

select pg_table_size('person_first_name')

select pg_table_size('person_full_name')

```

Type of scan -
- Index scan
- Bitmap index scan https://pganalyze.com/docs/explain/scan-nodes/bitmap-index-scan
- Bitmap heap scan
- Sequential scan

TANSTAAFL - "There ain't no such thing as a free lunch"
- Storage (Disk & RAM)
- Insert and update query

Workaround
- Partial index

Postgres supports-
- b tree : balanced binary tree
- hash table
- generalised inverse index
- block range index

Source:
- https://www.youtube.com/watch?v=clrtT_4WBAw
- https://www.youtube.com/watch?v=-qNSXK7s7_w
- https://www.youtube.com/watch?v=fsG1XaZEa78




## Replication
- Fault taularance 
- Eliminates single point of failure
- Synchronous vs Asynchronous replication - tradeoff between performane and consistency
- One directional replication
- Bi directional replication 
- Streaming replication
- Logical replication
- Statement based replication


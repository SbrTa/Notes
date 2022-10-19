# Database

Performance is extremely important in many consumer products like e-commerce, payment systems, gaming, transportation apps, and so on. Although databases are internally optimised through multiple mechanisms to meet their performance requirements in the modern world, a lot depends on the application developer as well — after all, only a developer knows what queries the application has to perform.



# Index
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


# Partitioning
- breaking up a large data set into smaller subsets
- One schema to multiple schema. ie - separate contact and address from user.
- 1000 user to 2 user table with 500 row each

### Type of partition
  - Vertical partitioning
    - devides column
    - An ideal scenario for this type of partition is when you don’t need all the information about the customer in your query. IE- basic info, address, contact...
  - Horizontal partitioning 
    - range based partitioning
    - put different rows into different tables
    - all table has same structure
    - same or multiple server
    - known as **sharding**

### Why partition
- Huga data. or rapidly growing data
- **Improve scalability**. When you scale up a single database system, it will eventually reach a physical hardware limit. If you divide data across multiple partitions, each hosted on a separate server, you can scale out the system almost indefinitely.
- **Improve performance**. Data access operations on each partition take place over a smaller volume of data. Correctly done, partitioning can make your system more efficient. Operations that affect more than one partition can run in parallel.
- **Improve security**. In some cases, you can separate sensitive and nonsensitive data into different partitions and apply different security controls to the sensitive data.
- **Provide operational flexibility**. Partitioning offers many opportunities for fine-tuning operations, maximizing administrative efficiency, and minimizing cost. For example, you can define different strategies for management, monitoring, backup and restore, and other administrative tasks based on the importance of the data in each partition.
- **Match the data store to the pattern of use**. Partitioning allows each partition to be deployed on a different type of data store, based on cost and the built-in features that data store offers. For example, large binary data can be stored in blob storage, while more structured data can be held in a document database. See Choose the right data store.
- **Improve availability**. Separating data across multiple servers avoids a single point of failure. If one instance fails, only the data in that partition is unavailable. Operations on other partitions can continue. For managed PaaS data stores, this consideration is less relevant, because these services are designed with built-in redundancy.

### What to consider
- how will the data be distributed across shards?
- what types of queries will be routed across shards?
- how will these shards be maintained?

### Sharding strategies
##### Range based sharding
  - assigns rows to partitions based on column values falling within a given range.
  - 1st 1k in shard 1, 2nd 1k in shard 2 etc
##### Algorithmic / hashing / Key Based partioning
  - Write a has function
  - pass the key
  - hash function selects shard based on the key
  - lets, you have service in 2 countries. so based on countries you split data into 2 shards
  - what if you start service in another country?
  - you have to rewrite the hash
  - One solution is consistent hashing
##### Lookup strategy / Entity Groups
Many databases have more expressive querying and manipulation capabilities. Traditional RDBMS features such as joins, indexes and transactions reduce complexity for an application. The concept of entity groups is very simple. Store related entities in the same partition to provide additional capabilities within a single partition. Specifically:
  - Queries within a single physical shard are efficient.
  - Stronger consistency semantics can be achieved within a shard.

This is a popular approach to shard a relational database. In a typical web application data is naturally isolated per user. Partitioning by user gives scalability of sharding while retaining most of its flexibility.

### Drawbacks
 - Additional programming and operational complexity
 - **Rebalancing Data**: you have two shards of a database. One shard store the name of the customers begins with letter A through M. Another shard store the name of the customer begins with the letters N through Z. If there are so many users with the letter L then shard one will have more data than shard two. This will affect the performance (slow down) of the application and it will stall out for a significant portion of your users. The A-M shard will become unbalance and it will be known as database hotspot. To overcome this problem and to rebalance the data you need to do re-sharding for even data distribution. Moving data from one shard to another shard is not a good idea because it requires a lot of downtimes.
 - **Joining Data From Multiple Shards is Expensive**: in sharded architecture, you need to pull the data from different shards and you need to perform joins across multiple networked servers You can’t submit a single query to get the data from various shards. You need to submit multiple queries for each one of the shards, pull out the data, and join the data across the network. This is going to be a very expensive and time-consuming process. It adds latency to your system.

### Do you need database sharding?
Database sharding, as with any distributed architecture, does not come for free. There is overhead and complexity in setting up shards, maintaining the data on each shard, and properly routing requests across those shards. Before you begin sharding, consider if one of the following alternative solutions will work for you.
- query optimization
- indexing
- Vertical scaling (server)
- Specialized services or databases
  - blob or file storage can be moved directly to a cloud provider such as Amazon S3.
  - Analytics or full-text search can be handled by specialized services or a data warehouse.
- Replication
- Caching

Resources-
- https://medium.com/must-know-computer-science/system-design-sharding-data-partitioning-b7201596aafa
- https://learn.microsoft.com/en-us/azure/architecture/best-practices/data-partitioning
- https://www.enjoyalgorithms.com/blog/data-partitioning-system-design-concept

# Replication
- Fault taularance 
- Eliminates single point of failure
- Synchronous vs Asynchronous replication - tradeoff between performane and consistency
- One directional replication
- Bi directional replication 
- Streaming replication
- Logical replication
- Statement based replication


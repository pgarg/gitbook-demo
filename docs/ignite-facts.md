---
id: "ignite-facts"
title: "Ignite Facts"
excerpt: ""
---
## Is Ignite a persistent or memory-only storage?
**Both**. Native persistence in Ignite can be turned on and off. This allows Ignite to store data sets bigger than can fit in the available memory. Essentially, smaller operational data sets can be stored in-memory only, and larger data sets that do not fit in memory can be stored on disk, using memory as a caching layer for better performance.

[Read More](doc:distributed-persistent-store)


## Is Ignite an in-memory database (IMDB)?
**Yes**. Even though Ignite *durable memory* works well in-memory and on-disk, the disk persistence can be disabled and Ignite can act as a *distributed in-memory database*, with support for SQL and distributed joins. 

[Read More](doc:distributed-sql) 

## Is Ignite an in-memory data grid (IMDG)?
**Yes**. Ignite is a full-featured data grid, which can be used either in memory-only mode or with Ignite native persistence. It can also automatically integrate with any 3rd party databases, including any RDBMS or NoSQL store.

[Read More](doc:data-grid) 

## Is Ignite a distributed cache?
**Yes**. When native persistence is disabled, Ignite becomes a distributed cache. Ignite implements JCache specification (JSR 107) and provides a lot more functionality than required by the specification, including partitioned and replicated distribution modes, distributed ACID transactions, SQL queries, native persistence, and more. 

[Read More](doc:jcache)

## Is Ignite a distributed database?
**Yes**. Data in Ignite is either *partitioned* or *replicated* across a cluster of multiple nodes. This provides scalability and adds resilience to the system. Ignite automatically controls how data is partitioned, however, users can plug in their own distribution (affinity) functions and collocate various pieces of data together for efficiency.

[Read More](doc:distributed-sql) 

## Is Ignite an SQL database?
**Not fully**. Although Ignite aims to behave like any other relational SQL database, there are differences in how Ignite handles constraints and indexes. Ignite supports *primary* and *secondary* indexes, however, the *uniqueness* can only be enforced for the *primary* indexes. Ignite also does not support *foreign key* constraints. 

Essentially, Ignite purposely does not support any constraints that would entail a cluster broadcast message for each update and significantly hurt performance and scalability of the system.

[Read More](doc:indexes) 

## Is Ignite a NoSQL database?
**Not exactly**. Just like other NoSQL databases, Ignite is highly available and horizontally scalable. However, unlike other NoSQL databases, Ignite supports SQL and ACID transactions. 

## Is Ignite a transactional database?
**Not fully**. ACID Transactions are supported, but only at *key-value* API level. Ignite also supports *cross-partition* transactions, which means that transactions can span keys residing in different partitions on different servers.

At *SQL* level Ignite supports *atomic*, but not yet *transactional* consistency. Ignite community plans to implement SQL transactions in version 2.4.

[Read More](doc:sql-queries#known-limitations)

## Is Ignite a multi-model database?
**Yes**. Ignite supports both, key-value and SQL for modelling and accessing data. In addition, Ignite provides strong processing APIs for computing on distributed data. 

## Is Ignite a key-value store?
**Yes**. Ignite provides a feature rich key-value API, that is JCache (JSR-107) compliant and supports Java, C++, and .NET.

[Read More](doc:data-grid) 

## What is durable memory?
Ignite *durable memory* architecture allows Ignite to extend in-memory computing to disk. It is based on a paged-based off-heap memory allocator which becomes durable by persisting to the *write-ahead-log (WAL)* and, then, to main Ignite persistent storage. When persistence is disabled, durable memory acts like a pure in-memory storage.

[Read More](doc:durable-memory) 

## What is collocated processing?
Ignite is a distributed system and, therefore, it is important to be able to collocate data with data and compute with data to avoid distributed data noise. Data collocation becomes especially important when performing distributed SQL joins. Ignite also supports sending user logic (functions, lambdas, etc.) directly to the nodes where the data resides and computing on the data locally.

[Read More](doc:collocate-compute-and-data) 

## Book
Learn even more from [High-Performance in-memory computing with Apache Ignite](http://a.co/h4MBi1v) book.
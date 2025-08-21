[Cassandra vs MongoDB Comparison](https://www.mongodb.com/resources/compare/cassandra-vs-mongodb?)
Cassandra vs MongoDB: Use Cases
MongoDB is a general purpose document database. Therefore, it has a rich set of features and design patterns to cover almost all of today's modern applications. Many common modernizations to legacy SQL applications use MongoDB, as its flexible schema can be customized to transform existing data into the document model. Developers can also port over existing functionality from their SQL application, such as ACID transactions, secondary indexes on any field, and rich aggregation and query capabilities. In addition, it also supports horizontal scalability for big data as a core feature, as well as high availability and data segregation for meeting Service Level Agreements for latency and compliance needs.

Cassandra is mostly used for key-value columnar use cases. It is more suitable for very predictable reading and writing patterns, especially in write-heavy workloads—for example, a logging or tracking system where there are no or a very small number of in-place updates and not many secondary indexes in place.

With the release of Time Series Collections in MongoDB 5.0+, it is now just as easy and efficient to ingest, store, and query time series data as it is to work with any operational data in standard collections.

[NoSQL Comparison 2021: Couchbase Server, MongoDB, and Cassandra (DataStax)](https://www.altoros.com/blog/nosql-comparison-2021-couchbase-server-mongodb-and-cassandra-datastax/?utm_source)
- MongoDB and Couchbase are both document-oriented databases vs Cassandra which is a wide-column store. 
- Conclusion of paper: Cassandra is less suitable for a use case of an ecommerce website product catalogue because it is more optimized for high volume writes and not high volume reads.
- Between MongoDB and Couchbase, Couchbase performs better with bigger clusters and higher volumes of data --> MongoDB go to choice for most ecommerce website product catalogs and Couchbase for very big product catalog for big companies with large product catalog

[Cassandra vs MongoDB Comparison](https://www.mongodb.com/resources/compare/cassandra-vs-mongodb?)
- JSON-like document format (BSON) which is easy and flexible to use and modify 
- MongoDB is optimized for both reads and writes. In case of product catalogs, lots of reads will be performed vs Cassandra which is a wide-column store optimized database, very optimized for writes. 

Summary: 
- MongoDB & Couchbase: document-oriented data storage -> suite for most use cases like product catalog but Couchbase better for higher volumes 
- Cassandra: wide-column data storage optimized for **writes**, more suitable for log data for instance
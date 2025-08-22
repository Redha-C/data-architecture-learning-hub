[Apache Cassandra - Wikipedia](https://en.wikipedia.org/wiki/Apache_Cassandra?utm_source)
- Open-source database management system designed for large volumes of data accross multiple commodity servers
- Suite for high writes 
- Stores data with columns and has its own query language (Cassandra Query Language CQL)

[Les 7 bases de données à connaître pour pas passer pour un con](https://www.youtube.com/watch?v=080p5Y2_wpg)
2. Columnar BD
- Examples: Cassandra, BigQuery, RedShift
- Ideal for analytical purposes
- Highly performant for big queries
- Pros: 
    - Suited for analytical purposes 
    - Easy to split data accross multiples nodes as it is columnar based 
- Cons: 
    - Not suitable for requests read/write on back of websites as it would be too slow to gather information on a specific customer for instance
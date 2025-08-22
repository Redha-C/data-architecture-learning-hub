[Les 7 bases de données à connaître pour pas passer pour un con](https://www.youtube.com/watch?v=080p5Y2_wpg)
1. RDBMS: PostgreSQL, MySQL, SQLServer 
- Row-based databases -> easy to find information about customers for instance as it is row based and all data is present at the same location 
- DBs used when relations are present. For instance, a checkout is related to the payment, the order, the inventory and the shipping
- ACID properties (Atomicity, Consistency, Isolation, Durability) -> ideal for transaction-related tasks (payments, orders, shipping, checkouts)
- Pros: 
    - Relations between data easy so easy to query data 
    - Ideal for transactions (ACID properties)
    - Ideal as backend databases for websites, apps
- Cons:
    - vertical scaling -> low performance for high data volumes
    - not suitable for analytics (calculation of aggregations, sums, ...)
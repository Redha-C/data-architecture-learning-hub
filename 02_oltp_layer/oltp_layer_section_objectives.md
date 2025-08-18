# Section Purpose

The purpose of this second section, ***02_oltp_layer***, is to explain what **Online Transactional Processing (OLTP)** stands for, what it involves, which types of databases can be used, and how to choose between them.

The main goal is to finish this section with a clear understanding of:
- What OLTP is
- Why it matters
- How to choose one database architecture over another depending on your use case

This section is divided into several subsections to keep everything logical and digestible:

### 1. `01_user_journey`
In this subsection, I'll reuse the fictional **Sportify** e-commerce use case introduced in ***01_case_overview***. The goal is to explain OLTP concepts using a concrete, operational example.

### 2. `02_relational_db_vs_nosql`
Here, I’ll explain the key differences between relational and NoSQL databases, and when to choose one over the other depending on technical needs.

### 3. `03_relational_db`
This subsection dives deep into relational databases — what they are, why they are useful, and the types of problems they solve. I’ll also briefly cover the most widely used relational databases: **MySQL**, **PostgreSQL**, **Oracle**, and **SQL Server**.

### 4. `04_nosql_db`
In this part, I’ll explore NoSQL databases — their purpose, use cases, and how they complement or differ from relational systems. I’ll also introduce popular NoSQL databases such as **MongoDB**, **Cassandra**, and **Couchbase**.

### 5. `05_columnar_database`
I’ll wrap up this section by covering **columnar databases**, which differ significantly from traditional row-based systems (both relational and NoSQL). I’ll explain why columnar databases are not typically used for OLTP systems — for example, as the backend of a transactional website.

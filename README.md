# 50 Important Databases Interview Questions

<div>
<p align="center">
<a href="https://devinterview.io/questions/software-architecture-and-system-design/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fsoftware-architecture-and-system-design-github-img.jpg?alt=media&token=521fd2a9-0d56-49c0-a723-9bd6ca081893" alt="software-architecture-and-system-design" width="100%">
</a>
</p>

#### You can also find all 50 answers here 👉 [Devinterview.io - Databases](https://devinterview.io/questions/software-architecture-and-system-design/databases-interview-questions)

<br>

## 1. What is a _database management system (DBMS)_, and can you name some examples?

A **Database Management System (DBMS)** serves as an intermediary between users and the database. It facilitates data maintenance, retrieval, and ongoing management, using a structured mechanism to ensure **data integrity, security, and efficiency**.

### Key Features

- **Data Modeling**: Organizes data into logically structured tables and relationships.
- **Data Manipulation**: Allows for CRUD operations (Create, Read, Update, Delete), usually via a query language.
- **Data Integrity**: Enforces referential integrity and ensures consistent data.
- **Security & Access Control**: Regulates user permissions to the data.
- **Data Concurrency**: Manages simultaneous data access by multiple users to avoid conflicts.
- **Backup & Recovery**: Provides mechanisms for data restoration in case of loss or corruption.
- **Data Analysis & Reporting**: Often includes tools for query optimization and report generation.

### Types of DBMS

1. **Relational DBMS (RDBMS)**: Organizes data into tables with predefined structures defined by a schema. SQL (Structured Query Language) is typically used for data operations. Common examples include MySQL, PostgreSQL, and Microsoft SQL Server.

2. **NoSQL DBMS**: Evolved as a response to the limitations of RDBMS, designed for unstructured or semi-structured data and horizontal scalability. Examples include MongoDB for document-oriented storage and Redis for key-value stores.

3. **Cloud-Based DBMS**: Hosted on cloud platforms, these systems provide flexibility and scalability, requiring minimal maintenance from users. Notable examples are Amazon RDS, Google Cloud Bigtable, and Azure Cosmos DB.

4. **NewSQL DBMS**: Combines the benefits of traditional RDBMS with modern needs like scalability. These systems often offer improved performance, designed for big data scenarios. Examples include Google Cloud Spanner and NuoDB.

5. **Object-Oriented DBMS (OODBMS)**: Designed for managing complex, object-based data models. They provide persistence for objects, disentangling the object structure from a relational schema. ODBMS are less popular in current times, but examples include db4o and ObjectStore.

6. **In-memory DBMS**: Maintains data in the system’s memory, enabling rapid access and processing. Examples include Oracle TimesTen and Redis.

7. **Multimodel DBMS**: Can handle multiple kinds of databases, such as key-value stores, document stores, and graph databases. This offers a variety of data models in a single system. ArangoDB is an example of such a system.

8. **Graph DBMS**: Specialized for dealing with interconnected data elements. They are optimized for operations like traversals and pathfinding. Neo4j is a well-known example of this type of DBMS.
<br>

## 2. Explain the _ACID properties_ in the context of databases.

In database management, **ACID** ensures that transactions are processed in a reliable, standardized manner.

### ACID Properties

#### Atomicity

_**Atomicity**_ ensures that all tasks in a transaction are completed or none are. Databases use **transaction logs** to manage atomicity. If a task fails, the transaction log allows the system to recognize the incomplete state and restore to the last known consistent state.

Consider a banking transfer: if the debit is successful but the credit fails, atomicity ensures that the debit is also rolled back.

#### Consistency

_**Consistency**_ requires that a transaction takes the database from one consistent state to another consistent state. It ensures that data integrity rules are not violated. For example, after a transfer, the sum of account balances should remain the same.

#### Isolation

_**Isolation**_ ensures that the operations within concurrent transactions are invisible to each other until they are completed, to protect against potential conflicts and inconsistencies.

Different isolation levels, like **read uncommitted**, **read committed**, **repeatable read**, and **serialize**, define the extent to which transactions are isolated from one another.

#### Durability

_**Durability**_ guarantees that once a transaction is committed, its changes persist, even in the event of a system failure. This is typically achieved through mechanisms such as write-ahead logging and buffer management, which ensure changes are written to disk.

### ACID in Practical Scenarios

1. **Banking Applications**: ACID ensures that monetary transactions are secure and reliable.

2. **Inventory Management**: When goods are purchased, inventory levels are updated consistently, without corruption or errors.

3. **Scheduling Systems**: Activities, such as booking appointments, either take place entirely or not at all, avoiding messy partial bookings.

4. **E-commerce Order Processing**: The entire cycle, from a customer placing an order to its fulfilment, is a cohesive and consistent unit of work.

5. **Messaging Services**: For example, ensuring that a message is sent only after it is completely composed, not mid-way.
<br>

## 3. What are the differences between _SQL_ and _NoSQL_ databases?

**SQL** and **NoSQL** databases vary in several key aspects. Here, I will elaborate on five of them.

### Key Distinctions

- **Data Structure**: SQL databases are table-based, whereas NoSQL databases can be document, key-value, wide-column, or graph-oriented.

- **Schema**: SQL databases are schema-based. They necessitate database schema, and any deviation requires schema modifications. NoSQL databases are either ad-hoc, making each document consistent with one another, or schema-on-read.

- **Querying**: SQL databases employ Structured Query Language to execute queries. NoSQL databases use methods specific to their data model.

- **Scalability**: SQL databases historically have employed vertical scaling or "scaling up" by increasing CPU power, memory, and storage on a single node. However, recent trends show support for horizontal scaling or "scaling out" across multiple nodes. NoSQL databases, by nature, support horizontal scaling more readily, making them "scale-out" architectures.

- **ACID**: Traditional SQL databases often guarantee ACID (Atomicity, Consistency, Isolation, and Durability) compliance. NoSQL databases, especially in eventual consistency models, might trade off immediate consistency for performance and availability.

### Evolution and Adaptation

- **Consistency Models**: SQL often indicates immediate or strict consistency. NoSQL provides a range of consistency models, from eventual consistency to strong consistency.

- **Data Relationships and Transactions**: SQL databases typically enforce data relationships using methods such as foreign keys and support more complex transactional behavior. NoSQL databases might sacrifice some of these features for greater performance.

- **Use Cases and Popularity**: SQL databases are time-tested, especially in cases that need strict consistency or have clear data relationships. NoSQL databases are popular for their flexibility, particularly in rapidly changing or expansive data needs, and within the realm of big data and other modern computing paradigms.

### Domain Adherence

- **Relational Integrity**: SQL databases pride themselves on ensuring referential integrity in relational data.

- **Efficiency in Certain Query Workloads**: SQL databases are frequently favored in scenarios that involve complex querying or multi-table joins because of their optimizer capabilities. NoSQL excels in certain types of queries, like key-value lookups, due to their data models.

- **Ease of Horizontal Scaling**: NoSQL is often the preferred choice in setups requiring high availability and distributed data.
<br>

## 4. Describe a _relational database schema_.

A **Relational Database Schema** is a set of rules that define the structure, constraints, and relationships of data tables in a **Relational Database Management System (RDBMS)**.

### Core Components

1. **Tables**: Central data containers often referred to as "relations."
   - Defined by column names and data types.
2. **Columns**: Attributes or fields, defined by their name, type, and optional constraints.
   - Each column should have a unique name within the table.
   - Common data types include integers, strings, dates, and more.
3. **Rows**: Individual data records, consisting of data based on the table's defined columns.
   - Each row should have a unique identifier, often referred to as a "primary key".

### Key Types

1. **Primary Key (PK)**: A unique identifier for each record within a table. It's often an auto-incrementing integer. Each table should have precisely one primary key. This is Essential designated as “E” in databases.
2. **Foreign Key (FK)**: A field or a group of fields in a table that uniquely identifies a row in another table. Commonly a primary key from another table, these help establish relationships between tables. This term is derived as “F” from Candidate Key in databases

### Relationship Types

1. **One-to-One**: Each record in the first table is related to one and only one record in the second table, and vice versa.
2. **One-to-Many**: A record in the first table can be related to one or more records in the second table, but a record in the second table is related to only one record in the first table.
3. **Many-to-Many**: Records in both tables can be related to multiple records in the other table. This relationship requires a linking table.

### Common Constraints

- **NOT NULL**: Specifying that a column must have a value and cannot be left empty. This is Essential designated as “E” in databases.
- **UNIQUE**: Requires all entries in a column or set of columns to be distinct.
- **CHECK**: Allows for conditional checks to be applied to column data.
- **DEFAULT**: Automatically provides a predetermined value when a new column is created.
- **INDEX**: Optimizes data retrieval by creating an index on the column(s), speeding up relevant queries.

### Code Example: Schema for University Database

Here is the SQL code:

```sql
-- Table for students
CREATE TABLE Students (
  StudentID INTEGER PRIMARY KEY,
  Name TEXT NOT NULL,
  Age INTEGER CHECK (Age >= 18),  
  MajorID INTEGER,
  FOREIGN KEY (MajorID) REFERENCES Majors(MajorID)
);

-- Table for courses
CREATE TABLE Courses (
  CourseID INTEGER PRIMARY KEY,
  Title TEXT NOT NULL,
  Credits INTEGER CHECK (Credits >= 0)
);

-- The table that maps the many-to-many relationship between Students and Courses
CREATE TABLE Enrollments (
  StudentID INTEGER,
  CourseID INTEGER,
  EnrollmentDate DATE DEFAULT CURRENT_DATE,
  PRIMARY KEY (StudentID, CourseID),
  FOREIGN KEY (StudentID) REFERENCES Students(StudentID),
  FOREIGN KEY (CourseID) REFERENCES Courses(CourseID)
);

-- The table that holds the list of possible majors
CREATE TABLE Majors (
  MajorID INTEGER PRIMARY KEY,
  Name TEXT NOT NULL UNIQUE
);
```
<br>

## 5. What is a _primary key_, and why is it important?

A **primary key** is a unique identifier for a table. It ensures each data record in a table is distinct and can be efficiently referenced.

### Core Features

- **Uniqueness**: Every record in a table must have a unique primary key.
- **Non-Null Value**: A primary key field cannot contain null or undefined values.
- **Stability**: Changes to primary key values should be rare, ensuring its reliability as an identifier.

### Benefits

- **Data Integrity**: Ensures accuracy and consistency within the dataset.
- **Data Retrieval**: Helps in efficient data retrieval and can easily reference related data tables through Foreign Keys.
- **Data Normalization**: Aids in organizing data across multiple tables, reducing redundancy and improving data integrity.
- **Table Relationships**: Serves as a basis for establishing multiple types of relationships with other tables (one-to-one, one-to-many, many-to-many).

### RDBMS Requirements


#### MySQL

- **Character Limit**: 1000 characters in total across all the columns defined for a primary key.
- **Restrictions**: Text and blob columns are not permitted in primary keys.
- **Supported Types**: Can use most column types, including integers, strings, and dates.

#### PostgreSQL

- **Character Limit**: 32 characters for the name of the primary key constraint, which defaults to `table_name_pkey`.
- **Supported Types**: Most column types can be defined as primary keys, including UUID.

#### SQL Server

- **Character Limit**: 900 bytes.
- **Restrictions**: Text and image columns are forbidden in primary keys.
- **Supported Types**: The uniqueidentifier data type is commonly used as a primary key.

#### SQLite

- **Character Limit**: No fixed-length requirement.
- **Supported Types**: Most column types, including integers, can be used for primary keys.

#### Oracle Database

- **Character Limit**: The PRIMARY KEY constraint name, combined with the schema name, cannot exceed 30 characters.
- **Supported Types**: Most column data types can be used, including LOB columns.
<br>

## 6. Can you explain what a _foreign key_ is and its role in the database?

A **foreign key** (FK) establishes a relationship between two tables in a relational database.

### Key Attributes

- **Column Type**: The FK column in the child table must have the same data type as the primary key column in the parent table.
- **Referential Integrity**: The FK ensures data consistency by either rejecting the change, setting it to NULL, or cascading the changes.
- **Joining Tables**: Utilizing the foreign key in SQL queries helps combine related data from multiple tables.

**JOIN** statement is the SQL command central to integrating tables through foreign keys:

### Join Types

- **Inner Join**: Matches only the records having related entries in both tables.
- **Outer Join**: Includes records from one table even if there are no related entries in the other table.

### Examples and Code Explanation

Here is the SQL code:

```sql
-- 1. Parent Table Creation
CREATE TABLE authors (
    author_id INT PRIMARY KEY,
    author_name VARCHAR(100)
);

-- 2. Child Table Creation with Foreign Key
CREATE TABLE books (
    book_id INT PRIMARY KEY,
    book_name VARCHAR(255),
    author_id INT,
    FOREIGN KEY (author_id) REFERENCES authors(author_id)
);

-- 3. Data Insertion
INSERT INTO authors (author_id, author_name) VALUES (1, 'J.K. Rowling');

INSERT INTO books (book_id, book_name, author_id) VALUES (1, 'Harry Potter', 1);

-- 4. Select Query for Data Retrieval
SELECT book_name, author_name FROM books 
JOIN authors ON books.author_id = authors.author_id;
```

In this code, `author_id` in the `books` table is a foreign key pointing to the `author_id` in the `authors` table. The `SELECT` statement employs a **JOIN** to unify the related `book` and `author` data.

### Verifying Key Relationships

- **SYS.TYPE_CATALOG** uses system views for all three types of keys: primary, foreign, and unique. It displays tables with their corresponding keys.
- **INFORMATION_SCHEMA.KEY_COLUMN_USAGE** furnishes comprehensive key information, such as the table containing the keys, as well as the cardinality.

For instance, using SQL SERVER:

```sql
SELECT
  TABLE_NAME, 
  COLUMN_NAME, 
  CONSTRAINT_NAME
FROM 
  INFORMATION_SCHEMA.KEY_COLUMN_USAGE 
WHERE 
  TABLE_NAME = 'books';
```
<br>

## 7. What is _database normalization_, and why do we use it?

**Database normalization** is a set of practices that ensure **data integrity** by minimizing redundancy and dependency within a relational database.

### Advantages of Normalization

1. **Data Consistency**: Reduction in redundancy decreases the risk of inconsistent data.
2. **Improved Maintainability**: With a more structured database, maintenance becomes more straightforward.
3. **Easier Updates**: Normalization usually means fewer records to update.

### Normalization Levels

There are generally six levels of normalization, from 0 to 5 or "BCNF".

#### First Normal Form (1NF)

1. **Unique Primary Keys**: A table should have a unique primary key for each record.
2. **Atomic Values**: Each cell in a table should hold a single value, eliminating multi-valued attributes.

#### Second Normal Form (2NF)

- All requirements of the previous form, as well as:
- Removal of **Partial Dependencies**: Non-primary key columns should depend on the entire primary key.

#### Third Normal Form (3NF)

- All requirements of 2NF, as well as:
- Elimination of **Transitive Dependencies**: Non-primary key columns should not be dependent on other non-primary key columns.

#### Boyce-Codd Normal Form (BCNF)

- A stricter version of 3NF that ensures each determinant is a candidate key.

#### Fourth Normal Form (4NF)

- Deals with multi-valued dependencies.

#### Fifth Normal Form (5NF)

- Also called "Projection-Join Normal Form" and deals with join dependencies.

### Normal Forms and Use-Cases

Most relational databases aim for 3NF, as it typically strikes a good balance between performance and data integrity.

However, it's essential to understand the specific **requirements** of your database and decide on an optimal normalization level accordingly. For instance, reporting databases might not be heavily normalized to improve query performance.
<br>

## 8. What is _denormalization_ and when would you consider it?

**Denormalization** is the process of **reducing normalization** (typically for performance reasons) by introducing **redundant data** into one or more tables. While normalization ensures data integrity, **denormalization** mainly focuses on **improving query performance** by eliminating complex JOIN operations.

### Benefits and Drawbacks

- **CTEs**: With multiple **Common Table Expressions**, maintaining benefits of a normalized schema can be achieved in a denormalized setup, potentially eliminating the drawbacks.
- **Maintainability**: Denormalization can make data harder to manage and keep consistent. 
- **Query Performance**: Queries may become more efficient, as data required from different normalized tables is now available in a single denormalized table.
- **Storage Efficiency**: Queries that access multiple smaller tables require less disk I/O and can fit into the memory more easily than queries accessing a few larger tables.
- **Data Integrity**: Redundant data can lead to inconsistencies if not managed properly.

### Case-by-Case Considerations

**Lookup Tables**: Tables with relatively static data (like Status types or Location information) that are frequently joined with other tables in your system, are strong candidates for denormalization. This can make **frequent lookups** faster.

**Reporting and Analytics**: Systems that are skewed towards **read operations** over write operations benefit from denormalization. When designing systems for reporting or analytics, it's common practice to have dedicated read replicas that are denormalized for improved read performance.

**Partitioning**: In large systems, denormalization can be used to **partition** data across different tables or clusters to distribute load. For example, customer data can be segregated into one cluster, and order data into another, linked via denormalization.

### Code Example: Denormalization and Normalization

Here is the SQL code:

```sql
-- Example of Normalized Tables
Customer Table: 
| ID | Name  | StatusID |
| 1  | John  | 2        |
| 2  | Jane  | 1        |

Status Table:
| StatusID | Description |
| 1        | Pending     |
| 2        | Active      |


-- Querying the Status using JOIN
SELECT c.Name, s.Description AS Status FROM Customer c
JOIN Status s ON c.StatusID = s.StatusID;


-- Denormalized Table
Customer Table (Denormalized):
| ID | Name  | Status   |
| 1  | John  | Active   |
| 2  | Jane  | Pending  |


-- Eliminating JOINs in the Query
SELECT Name, Status FROM Customer;
```
<br>

## 9. Compare and contrast the _DROP_, _DELETE_, and _TRUNCATE_ commands.

Let's look at the three commands - **`DROP`**, **`DELETE`** and **`TRUNCATE`** in terms of their function, operation, speed and recovery.

### DROP Table

The **`DROP TABLE`** statement deletes an **entire table and its structure** from the database.

#### SQL Syntax
```sql
DROP TABLE table_name;
```

#### Transaction Control
- Implicit Commit: The action is immediately committed, and its effects are irreversible.

#### Considerations
- **Irreversible**: Drops the table as a whole; it doesn't delete records row by row.
- **Data Loss**: Any data in the table is permanently removed.

### DELETE from Table

The **`DELETE`** statement operates on individual rows in the table and is reversible.

#### SQL Syntax
```sql
DELETE FROM table_name WHERE condition;
```

#### Transaction Control
- Needs a Transaction: Works within a transaction and needs to be explicitly committed to become permanent.

#### Considerations
- **Precision**: Removes specific rows based on the provided condition.
- **Recoverability**: Data can be undeleted or restored during the transaction if not committed.

### TRUNCATE Table

The **`TRUNCATE TABLE`** statement quickly **removes all rows** from a table, providing both speed and simplicity. It doesn't, however, release allocated storage like `DELETE` does.

#### SQL Syntax
```sql
TRUNCATE TABLE table_name;
```

#### Transaction Control
- Requires Commit: Like `DELETE`, this statement operates within a transaction and requires explicit commitment to finalize its actions.

#### Considerations
- **Efficiency**: Processes significantly faster compared to `DELETE`. Ideal for removing all records and resetting table states in certain applications.
- **No Selective Deletion**: Unlike `DELETE`, it clears all records in the table without regard for specific conditions.
- **Transaction and Recovery**: Upon execution, the data removal can usually be undone or rolled back until a final commit or termination of the transaction. 

### Code Example: Table Cleanup Operations

Here is the PostgreSQL code:

```sql
-- Create a sample table
CREATE TABLE employees (
  id SERIAL PRIMARY KEY,
  name VARCHAR(50),
  age INT
);

-- Insert sample data
INSERT INTO employees (name, age) VALUES ('Alice', 25), ('Bob', 30), ('Charlie', 28);

-- Display initial content
SELECT * FROM employees;

-- Use DELETE to remove specific rows
DELETE FROM employees WHERE age > 29;
-- Changes not yet applied
SELECT * FROM employees;

-- Use TRUNCATE to remove all rows
TRUNCATE TABLE employees;
-- Changes not yet applied
SELECT * FROM employees;

-- Final commitment to make changes permanent
COMMIT;
-- Now, the table is empty
SELECT * FROM employees;
```
<br>

## 10. What is the difference between a _full join_ and an _inner join_?

**Full joins** and **inner joins** serve different purposes in database management systems and exhibit distinct behavior patterns.

### Inner Join

An inner join finds and combines matching records from both the parent and child tables, based on a specified join condition. Records that don't have a match in either table are excluded from the result.

#### SQL Syntax

```sql
SELECT column_name(s)
FROM table1
INNER JOIN table2 ON table1.column_name = table2.column_name;
```

### Full Join

A full join, also known as a **full outer join**, returns all records from both tables and fills in **NULL** values where no match is found in the corresponding table. This type of join is less frequently used compared to the others, as it can potentially generate very large result sets.


#### SQL Syntax

```sql
SELECT column_name(s)
FROM table1
FULL OUTER JOIN table2 ON table1.column_name = table2.column_name;
```

#### Visual Representation

![SQL Joins](https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/databases%2Fjoins.png?alt=media&token=98b9e74b-2b4e-45b5-81f6-97e7fe97713b)
<br>

## 11. How would you write an _SQL query_ to fetch duplicate records from a table?

Let's look at two common methods for identifying and handling duplicate records in SQL.

### 1. Standard SQL

```sql
SELECT column1, column2, ..., columnN, COUNT(*)
FROM mytable
GROUP BY column1, column2, ..., columnN
HAVING COUNT(*) > 1;
```

### 2. Using **ROW_NUMBER()**

This method can be particularly useful in cases where you also want to keep track of the "duplicate" IDs.

```sql
WITH duplicates AS (
  SELECT *,
         ROW_NUMBER() OVER (PARTITION BY column1, column2, ..., columnN ORDER BY ID) AS rnum
  FROM mytable
)
SELECT * 
FROM duplicates 
WHERE rnum > 1;
```

In both of these methods, `column1, column2, ..., columnN` refer to the column or set of columns you're using to identify duplicates.

### Code Example: Standard SQL

```sql
SELECT name, age, COUNT(*)
FROM mytable
GROUP BY name, age
HAVING COUNT(*) > 1;
```

In this example, we're looking for **duplicate records** based on the "name" and "age" columns from the "mytable".

### Code Example: ROW_NUMBER()

```sql
WITH duplicates AS (
  SELECT *,
         ROW_NUMBER() OVER (PARTITION BY name, age ORDER BY ID) AS rnum
  FROM mytable
)
SELECT * 
FROM duplicates 
WHERE rnum > 1;
```

In this example, we're using **ROW_NUMBER()** to identify records with the same "name" and "age" and keeping track of the **unique** row number for each.
<br>

## 12. What is a _prepared statement_, and why would you use one?

**Prepared Statements** reduce the risk of SQL injection by separating SQL data and commands. They also optimize query execution by allowing **repetitive parameter bindings**.

### Key Advantages

- **Security**: They defend against SQL injection by distinguishing between SQL code and input values.
- **Performance**: Prepared statements can be faster when used repeatedly, as they are parsed and executed in discrete steps.
- **Readability and Maintainability**: Separating the SQL code from the parameters makes it more readable. It can make the code easier to understand, review, and maintain.

### When to Use Prepared Statements

- **Input from Untrusted Sources**: When SQL queries are constructed with data from untrusted sources, prepared statements ensure the data is treated as literal values, preventing SQL injection.
  
- **Repeated Executions**: For queries executed multiple times, using a prepared statement can be more efficient than constructing and executing a new query each time. This is especially relevant in loops or high-volume operations.
<br>

## 13. What is the _N+1 query problem_ and how can you solve it?

**N+1 Query Problem** arises when an object graph is retrieved using a query that results in unnecessary database hits.

For instance, consider a **one-to-many relationship** where each "Order" has many "LineItems". If you fetch all "Orders" and then individually fetch their "LineItems," it leads to multiple query rounds. These excessive queries are inefficient, especially when the number of related items is high.

Let's say, in a more specific case, you fetch:
1. All Orders.
2. Then for each Order, fetch its LineItems.

This corresponds to:

1. **Primary Query**: `SELECT * FROM Orders`.
2. **Secondary Query**: `SELECT * FROM LineItems WHERE order_id = :order_id` (Potentially executed several times based on order count).

Here you have an **N+1 scenario** because the second query is executed "N" times, once for each Order, hence N+1.

### Solutions

#### Use a JOIN Query

By employing a JOIN, you can retrieve related entities in a single query.

- **SQL**
    ```sql
    SELECT o.*, li.*
    FROM Orders o
    JOIN LineItems li ON o.id = li.order_id;
    ```
    
- **ORM**
    ORM tools, like Hibernate, can handle this for you. You might not even know under the hood whether the ORM uses JOIN.

#### Leverage Lazy Loading

Some ORMs are configured to execute extra queries only when a related object is accessed for the first time. This is known as **lazy loading**. It reduces the initial query size, improving efficiency but might lead to an N+1 problem if multiple related entities are accessed.

#### Use Explicit Eager Loading

Modern ORMs often provide mechanisms for **explicitly defining** which related entities to fetch eagerly. This way, you can still benefit from lazy loading while strategically opting for immediate access when needed. In Entity Framework (EF) and Java Persistence API (JPA), for example, you can use annotations like `@ManyToOne` and `@OneToMany` to control lazy/eager loading behavior.

#### Use Data Projection

Instead of loading entire entities, you can **select specific fields** needed for immediate operations. This can be beneficial when you aren't interested in all the entity's properties.

- **SQL**
  ```sql
  SELECT id, name FROM Orders;
  ```

- **ORM**
  With JPA, you can use constructor expressions in JPQL to achieve this:
  ```java
  TypedQuery<OrderSummary> query = em.createQuery(
      "SELECT NEW OrderSummary(o.id, o.name) FROM Order o", OrderSummary.class
  );
  ```

  And in Entity Framework, you can utilize LINQ projections:
  ```csharp
  var orderSummaries = from order in context.Orders
                      select new OrderSummary { Id = order.Id, Name = order.Name };
  ```

#### Implement Paging

When dealing with a **large dataset**, it's often more reasonable to employ **paging** rather than fetching everything at once. A SELECT query can be modified with `OFFSET` and `LIMIT` (in SQL Server and PostgreSQL) or the `ROW_NUMBER()` function (in SQL Server and Oracle) to achieve this neatly.

- **SQL Server and PostgreSQL**
  ```sql
  SELECT * FROM Orders
  ORDER BY id
  OFFSET 0 ROWS
  FETCH NEXT 5 ROWS ONLY;
  ```
<br>

## 14. Explain the function of _GROUP BY_ and _HAVING_ clauses in SQL.

**GROUP BY** and **HAVING** transform, filter, and work together with aggregate functions to enable more complex and nuanced result sets.

### Functions of GROUP BY

- **Aggregation**: Identifies groups and computes aggregate functions (e.g., COUNT, SUM) for each group.
- **Redundancy Reduction**: Collapses redundant data based on the grouped columns to provide a leaner dataset.
- **Column Constraint**: Allows queries to select only aggregated columns, and from the source columns, all non-aggregated ones need to be in the `GROUP BY`, ensuring consistent data representation.

### Functions of HAVING 

- **Group-Wise Filtering**: Applies conditional checks to grouped data.
- **Post-Group Filtering**: Allows filtering based on the results of aggregate functions.
- **Aggregation Assertion**: Validates aggregated values against specific conditions.
- **Comparison with WHERE**: Enables more advanced, aggregate-aware filtering compared to the global, pre-aggregation filtering provided by `WHERE`.

### Code Example: GROUP BY & HAVING

Consider the following relational schema:

```plaintext
EMPLOYEE (ID, Name, DeptID, Salary)
DEPARTMENT (ID, Name)
```

To retrieve department IDs where the average salary is over a certain threshold:

#### SQL Query

```sql
SELECT DeptID
FROM EMPLOYEE
GROUP BY DeptID
HAVING AVG(Salary) > 50000;
```
<br>

## 15. What are _indexes_ and how do they work in databases?

An **index** serves as a data structure in a database system. It enhances the efficiency and speed of data lookup operations by logically ordering the indexed data.

### Index Types

- **B-Tree (Balanced Tree)**: Suited for ranges and equality operations, such as using `WHERE` clauses in SQL.
- **Hash**: Ideal for exact-match lookups, like primary keys.
- **Full-text**: Specifically designed for text searches, often seen in search engines.
- **Bitmap**: Efficient for low-cardinality columns, where there are few distinct values, like gender.

### Data Lookup Using Indexes

- **Ordered Scans**: Possible through B-Tree indexes where data is sorted, aiding range queries.
- **Exact-Match Sequencing**: For Hash and tree-based indexes, this ensures swift exact-value matches.
- **Range Searches**: Supported by B-Trees, they enable operations like finding numbers within a range.

### Best Practices

- **Consider Index Maintenance Overhead**: While indexes speed up reads, they might slow down data modifications like `INSERT`, `UPDATE`, and `DELETE`.
- **Index Tailing**: Place more selective columns first, and follow them with less-discriminatory columns for best results.
- **Index Coverage**: Aim to cover frequently queried columns, but don't go overboard, leading to index bloat.

### Code Example: Index Types in PostgreSQL

Here is the SQL code:

  ```sql
  -- B-Tree Index
  CREATE INDEX idx_btree ON table_name (column_name);

  -- Hash Index
  CREATE INDEX idx_hash ON table_name USING HASH (column_name);
  ```

<br>



#### Explore all 50 answers here 👉 [Devinterview.io - Databases](https://devinterview.io/questions/software-architecture-and-system-design/databases-interview-questions)

<br>

<a href="https://devinterview.io/questions/software-architecture-and-system-design/">
<img src="https://firebasestorage.googleapis.com/v0/b/dev-stack-app.appspot.com/o/github-blog-img%2Fsoftware-architecture-and-system-design-github-img.jpg?alt=media&token=521fd2a9-0d56-49c0-a723-9bd6ca081893" alt="software-architecture-and-system-design" width="100%">
</a>
</p>


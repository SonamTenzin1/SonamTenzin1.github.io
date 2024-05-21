---
Title: DBS101 Flipped Class 8
categories: [DBS101, Flipped_Class]
tags: [DBS101]
---

### Topic: Bitmap Indexing in DBMS

**Bitmap Indexing** is a data indexing technique used in database management systems (DBMS) to improve the performance of read-only queries that involve large datasets. It involves creating a bitmap index, which is a data structure that represents the presence or absence of data values in a table or column.

In a bitmap index, each distinct value in a column is assigned a bit vector that represents the presence or absence of that value in each row of the table. The bit vector contains one bit for each row in the table, where a set bit indicates the presence of the corresponding value in the row, and a cleared bit indicates the absence of the value.

**Bitmap Index Structure**

A bitmap is the combination of two words: bit and map. A bit can be termed as the smallest unit of data in a computer and a map can be termed as a way of organizing things.

**Bit:** A bit is a basic unit of information used in computing that can have only one of two values either 0 or 1. The two values of a binary digit can also be interpreted as logical values true/false or Yes/No.

Bitmap Indexing is a special type of database indexing that uses bitmaps. This technique is used for huge databases when the column is of low cardinality and these columns are most frequently used in the query. 

Bitmap indexing is a data structure used in database management systems (DBMS) to efficiently represent and query large datasets with many attributes (columns). Bitmap indexes use a compact binary representation to store the occurrence of each value or combination of values in each attribute, allowing for fast, set-based operations.

**Features of Bitmap Indexing in DBMS**

**Space efficiency:** Bitmap indexes are highly space-efficient because they use a compact binary representation to store the occurrence of each value or combination of values in each attribute. This makes them especially useful for large datasets with many attributes.

**Fast query processing:** Bitmap indexes can be used to quickly answer complex queries involving multiple attributes using set-based operations such as AND, OR, and NOT. This allows for fast query processing and reduces the need for full table scans.

**Low maintenance overhead:** Bitmap indexes require relatively low maintenance overhead because they can be updated incrementally as data changes. This makes them especially useful for applications where the data is frequently updated.

**Flexibility:** Bitmap indexes can be used for both numerical and categorical data types, and can also be used to index text data using techniques such as term frequency-inverse document frequency (TF-IDF).

**Reduced I/O overhead:** Bitmap indexes can be used to avoid expensive I/O operations by using a compressed representation of the data. This reduces the amount of data that needs to be read from the disk, improving query performance.

**Ideal Choice:** Bitmap indexing is a powerful technique for efficiently querying large datasets with many attributes. It’s compact representation and set-based operations make it an ideal choice for data warehousing and other applications where fast query processing is critical.

**Applications of Bitmap Indexing in DBMS**

**Fast queries on large datasets:** Bitmap indexing is particularly useful for fast queries on large datasets. When querying a table with a bitmap index, the database engine can quickly determine which rows satisfy the query by performing a bitwise operation on the corresponding bitmaps. This can greatly reduce query execution time, especially for queries that involve multiple columns or complex conditions.

**Efficient range queries:** Bitmap indexing can also be used for efficient range queries on numeric or date columns. The bitmap for a range of values can be constructed by performing bitwise operations on the bitmaps for individual values. This allows the database engine to quickly identify all rows that fall within a given range.

**Space efficiency:** Bitmap indexing can be more space-efficient than other indexing techniques, especially for columns with a small number of distinct values. For example, a column with only two distinct values (such as gender) can be represented using a single bitmap, while other indexing techniques would require multiple index entries.

**Multi-dimensional indexing:** Bitmap indexing can be used for multi-dimensional indexing by creating a bitmap for each dimension. The bitmaps can then be combined using bitwise operations to identify rows that satisfy a query with multiple conditions.

**Data warehousing applications:** Bitmap indexing is commonly used in data warehousing applications where the focus is on fast query performance. In these applications, tables often have large numbers of columns with a relatively small number of distinct values, making bitmap indexing a particularly effective technique.

**What is the Need for Bitmap Indexing?**

The need for Bitmap Indexing will be clear through the below-given example:

For example, Let us say that a company holds an employee table with entries like EmpNo, EmpName, Job, New_Emp, and salary. Let us assume that the employees are hired once a year, therefore the table will be updated very less and will remain static most of the time. But the columns will be frequently used in queries to retrieve data like: number of female employees in the company etc. In this case, we need a file organization method that should be fast enough to give quick results. But any of the traditional file organization methods are not that fast, therefore we switch to a better method of storing and retrieving data known as Bitmap Indexing. 

Bitmap indexing can be used to improve the performance of queries that involve complex logical operations, such as AND, OR, and NOT. The logical operations are performed on the bit vectors, which can be efficiently combined using bitwise operators.

Bitmap indexing is particularly useful for datasets with low cardinality columns, where each value appears in a large number of rows. It is also useful for read-only queries that involve aggregations, such as counting or summing values, as the bit vectors can be quickly scanned to retrieve the required data.

**Bitmap Indexing in SQL**

The syntax for creating a bitmap index in SQL is given below.

**CREATE BITMAP INDEX Index_Name**

**ON Table_Name (Column_Name);**

**Advantages of Bitmap Indexing**

- Efficiency in terms of insertion deletion and updation.

- Faster retrieval of records

**Disadvantages of Bitmap Indexing**

- Only suitable for large tables

- Bitmap Indexing is time-consuming
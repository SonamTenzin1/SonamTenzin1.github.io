---
Title: DBS101 Flipped Class 6
categories: [DBS101, Flipped_Class]
tags: [DBS101]
---

### Topic: NoSQL database
---

### Sub-topic: document based database
---
A document-based database is a type of nonrelational database that stores data in documents rather than rows and columns. These documents are typically in JSON, BSON, or XML. Documents in this type of database can be easily stored and retrieved in a way that closely resembles the data objects used in applications, reducing the need for data translation. 

Key features of document databases include:
- flexible schema, making it easy to store documents with varying structures
- faster creation and maintenance due to minimal schema requirements
- lack of foreign keys, as there are no dynamic relationships between documents 
- and the use of open formats like XML and JSON for document construction.

### Sub-topic: key-value store
---
A key-value store is a type of nonrelational database, representing the simplest form of NoSQL databases. In this database, data elements are stored as key-value pairs, with each element having a unique key for retrieval. Values can range from simple data types like strings and numbers to complex objects. Key-value stores resemble relational databases with just two columns: one for the key and one for the corresponding value.

Key features of key-value stores include:
- simplicity in design and usage, 
- scalability to handle large amounts of data and traffic, 
- and high speed in data retrieval and storage operations.

### Sub-topic: graph based database
---
The graph based database focuses on the relationship between the elements. The data in this database is stored in the form of nodes. Updating data in this database is easy, since adding node or edge is straight forward and it does not require significant schema changes. This can be used in fraud detection.

Key features of this  database include:
- easy to identify the relationship between the nodes by using link.
- gives real-time results.

### Sub-topic: Vector database
---
Data in this database is stored in the form of vector. The data in this database are turned into special kind of code that a computer can understand. This database can be used to deal with comlex data with lots of dimensions, finding similarities, can handle huge amount of data and does real-time analysis. However, it is complex to set up and it is not recommended for all types of data.

### Sub-topic: Time-series database
---
Time-series data is simply data with a timestamp collected with the intent of tracking changes over time. A time-series database is a database system designed to store and retrieve such data for each point in time. Timestamped data can include data generated at regular intervals as well as data generated at unpredictable intervals.It can be used for monitoring the software systems and bare-metal hardware systems


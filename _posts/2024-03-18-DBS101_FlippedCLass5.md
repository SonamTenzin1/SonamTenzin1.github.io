---
Title: DBS101 Flipped Class 5
categories: [DBS101, Flipped_Class]
tags: [DBS101]
---

### Topic: Third Normal Form
---

Normalization in DBMS is a technique using which you can organize the data in the database tables so that:

- There is less repetition of data,

- A large set of data is structured into a bunch of smaller tables,

- and the tables have a proper relationship between them.

DBMS Normalization is a systematic approach to decompose (break down) tables to eliminate data redundancy(repetition) and undesirable characteristics like Insertion anomaly in DBMS, Update anomaly in DBMS, and Delete anomaly in DBMS. Out of the 6 normalization techniques, to say that a database is in a third normal form, a database:

- should fulfill all the criteria of first and second normal form

- should not have transitive dependencies

So what is a transitive dependency?
In a table we have primary key and the columns depending on the primary key which is normal but sometimes, we have instances like a column depending on another column which is not a primary key which is called a transitive dependency.

|exam_type_id|exam_type|total_marks|exam_duration|
|------------|---------|-----------|-------------|
|1           |practical|80         |50mins       |
|2           |theory   |100        |120mins      |

In this table we can see that the primary key of this table is thhe exam_type_id and all the other columns in this table is dependent on the primary key. However, we can see that total_marks depends on the exam_type which is not a primary key and the exam_duration depends on total_marks which is also not a primary key. In this table exam_type -> total marks, total_marks -> exam duration and exam_type ->-> exam_duration.

--
We were divided into 4 groups with 6 members in each. Then we were assigned a topic and the topic that my group got was Third Normal Form. We were given 20 mins to discuss wihtin the group and after the time was over, one of our group member presented about it.

Even though it was fairly simple to understand, it wasn't as interactive as expected during the presentation.
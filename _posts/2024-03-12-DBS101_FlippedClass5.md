---
Title: DBS101 Flipped Class 5
categories: [DBS101, Flipped_Class]
tags: [DBS101]
---

### Topic: Windows Function
---

Windows function is a method of calculating calculations accross a set of related rows without grouping them in a single row.It can compare, calculate totals and average, min or max within a group, assigning scores/rank abnd comparing values to their neighbor. This method maintains the individual identities of a row. When using window function, it conatins a function, over(), Patition BY, ORDER BY and SELECT. For examplr:

SELECT column_name;
Function (column_name) OVER(
    PARTITION BY (column_name)
    ORDER BY column_name
    RANGE between...and...
)
FROM table_name;

SELECT sales_date;
sum(total_sales) OVER(
    PARTITION BY sales_region
    ORDER BY sales_date
    RANGE between 1 and 7
)
FROM sales_table;

For instance, this window function calculates total sales for each sales region where the total sales are summed over a window defined by the past days for each date and it is done within sales table.

We were divided into 6 groups with 4 members in each. Then we were assigned a topic and the topic that my group got was the Window Function. We were given 20 mins to discuss wihtin the group and we had to do a presentation and then the presentation helped us understand better.

The flipped was very fun and interactive and the question-answer session made it even more enjoyable. The session made the theories that we were taught clearer and and we had a better understanding of the concepts.
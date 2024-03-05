---
Title: DBS101 Flipped Class 1
categories: [DBS101, Flipped_Class]
tags: [DBS101]
---

### Topic: NULL Values and Set Operators
---
In SQL, NULL values represent missing or unknown data in a table's fields. These values can arise due to various reasons such as unavailable information during data entry. SQL treats NULL as a special value to denote attributes with unknown or inapplicable data for a tuple. For instance, an Apartment_number attribute might only apply to certain types of addresses. Understanding the importance of NULL values is crucial. Unlike zero, NULL signifies a missing value, with interpretations ranging from unknown, unavailable, to not applicable. SQL doesn't differentiate between these meanings, leading to a lack of distinction among them. Principles regarding NULL values include using them when the actual value is unknown or meaningless and acknowledging that NULL is not equivalent to zero or spaces based on data types. NULL values can be inserted into columns of any data type and evaluate as NULL in expressions. SQL constraints like UNIQUE, FOREIGN key, and CHECK are disregarded if a column contains NULL. Comparisons involving NULL result in UNKNOWN, contributing to SQL's three-valued logic (True, False, Unknown). When using logical connectives like AND, OR, and NOT, defining the outcomes of expressions involving NULL is necessary. To test for NULL values in SQL, operators like IS NULL and IS NOT NULL are used instead of = or <> due to SQL's consideration of each NULL value as distinct. 
---

1.Union 
The Union operator in SQL is used to combine the results of two SELECT statements into a single result set. It works by appending the rows of the second SELECT statement to the end of the rows retrieved by the first SELECT statement. Union automatically removes duplicate rows from the combined result set, making the repeated row appear only once in the final output.

2.Union All
Like the Union, Union All also combines the results of two SELECT statements into a single result set. However, unlike Union, Union All keeps all rows from both SELECT statements, including the duplicates since Union All does not perform any sorting or removal of duplicate rows.

3.Intersect 
The Intersect operator compares the results of two SELECT statements and returns only the rows that appear in both result sets. In other words, it computes the intersection of the two result sets. Intersect automatically removes duplicate rows from the final output and arranges the data in ascending order by default. This operation is particularly handy when you need to find common rows between two sets of data, effectively filtering out any non-matching rows.

4.Minus 
The Minus operator is used to subtract the result set of one SELECT statement from the result set of another SELECT statement. It takes the rows returned by the first SELECT statement and removes any rows that also appear in the result set of the second SELECT statement. Similar to Intersect, Minus automatically eliminates duplicate rows and arranges the data. This operation is useful when you need to identify rows that exist in one set but not in another, effectively performing a set difference between the two result sets.
---

We were divided into 4 groups with 6 members in each. Then we were assigned a topic which was either NULL values or Set Operators. My group was assigned with NULL values and all of took our turn sharing what we had learnt about NULL values. Then again we were divided into groups that had members who learnt about NULL values and Set Operators. 
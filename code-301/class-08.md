# Read 08 - Notes: SQL

## [Complete SQLBolt (Intro, Lessons 1-4, 13-18)](http://sqlbolt.com/)

### Lessons 1 - 3 (SELECT, FROM, WHERE, AND/OR)
+ Select query for a specific columns
```
SELECT column, another_column, …
FROM mytable;
```
+ Select query for all columns
```
SELECT * 
FROM mytable;
```
+ In order to filter certain results from being returned, we need to use a **WHERE** clause in the query. The clause is applied to each row of data by checking specific column values to determine whether it should be included in the results or not.

+ More complex clauses can be constructed by joining numerous AND or OR logical keywords (ie. num_wheels >= 4 AND doors <= 2). 

+ Select query with constraints
```
SELECT column, another_column, …
FROM mytable
WHERE condition
    AND/OR another_condition
    AND/OR …;
```
+ Full-text search is best left to dedicated libraries like [Apache Lucene](http://lucene.apache.org/) or [Sphinx](http://sphinxsearch.com/). These libraries are designed specifically to do full text search, and as a result are more efficient and can support a wider variety of search features including internationalization and advanced queries.

### Lesson 4 (DISTINCT, ORDER BY, LIMIT, OFFSET)
+ SQL provides a convenient way to discard rows that have a duplicate column value by using the **DISTINCT** keyword.

+ Select query with unique results
```
SELECT DISTINCT column, another_column, …
FROM mytable
WHERE condition(s);
```
+ SQL provides a way to sort your results by a given column in ascending or descending order using the **ORDER BY** clause. When an ORDER BY clause is specified, each row is sorted alpha-numerically based on the specified column's value.

+ Select query with ordered results
```
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC;
```
+ Commonly used with the ORDER BY clause are the **LIMIT** and **OFFSET** clauses, which are a useful optimization to indicate to the database the subset of the results you care about. 

+ The LIMIT will reduce the number of rows to return, and the optional OFFSET will specify where to begin counting the number rows from.

+ Select query with limited rows
```
SELECT column, another_column, …
FROM mytable
WHERE condition(s)
ORDER BY column ASC/DESC
LIMIT num_limit OFFSET num_offset;
```

### Lesson 12 (ORDER OF OPERATION) - Optional
+ Complete SELECT query
```
SELECT DISTINCT column, AGG_FUNC(column_or_expression), …
FROM mytable
    JOIN another_table
      ON mytable.column = another_table.column
    WHERE constraint_expression
    GROUP BY column
    HAVING constraint_expression
    ORDER BY column ASC/DESC
    LIMIT count OFFSET COUNT;
```
+ Each query begins with finding the data that we need in a database, and then filtering that data down into something that can be processed and understood as quickly as possible. Each part of the query is executed sequentially.

+ Order of Operations:
  1. FROM and JOINs
  2. WHERE
  3. GROUP BY
  4. HAVING
  5. SELECT
  6. DISTINCT
  7. ORDER BY
  8. LIMIT/OFFSET



*****

## Additional Resources
+ Practice SQL on [W3 Schools](https://www.w3schools.com/sql/trysql.asp?filename=trysql_select_all) - This resource has sample databases you can use to practice writing SQL queries.
+ A Primer on SQL - Click the blue Download button - https://openlibra.com/en/book/a-primer-on-sql-3rd-edition
+ SQL Cheat Sheet - http://www.cheat-sheets.org/sites/sql.su/

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)




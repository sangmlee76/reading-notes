# Read 14a - Notes: DB Normalization

## [Essential: Database Normalization Explained in Simple English](https://www.essentialsql.com/get-ready-to-learn-sql-database-normalization-explained-in-simple-english/)

+ **Database normalization** is a process used to organize a database into tables and columns.

+ By limiting a table to one purpose you reduce the number of duplicate data contained within your database. This eliminates some issues stemming from database modifications.

+ 3 main reasons for normalization:
  - minimize duplicate data; reduces data storage requirement and increases performance
  - minimize or avoid data modification issues; reduce challenges of maintaining data changes
  - simplify queries

+ 3 modification anomalies:
  - __insert anomaly__: facts we cannot record until we know information for the entire row (e.g. primary key)
  - __update anomaly__: same information in several rows that require update of all rows when information changes
  - __deletion anomaly__: deletion of a single row that causes removal of more than one set of facts

+ Normalization makes it easier to search and sort your data. By putting data into a single purpose table, you avoid having to run queries that require multiple union (e.g. 'OR' statement) queries.

+ 3 common forms of database normalization:
  - __1st normal form__: The information is stored in a relational table with each column containing atomic values. There are no repeating groups of columns.
  - __2nd normal form__: The table is in first normal form and all the columns depend on the table’s primary key.
  - __3rd normal form__: the table is in second normal form and all of its columns are not transitively dependent on the primary key.

  - __Note__: The forms are progressive, meaning that to qualify for 3rd normal form a table must first satisfy the rules for 2nd normal form, etc.



## Additional Resources:
1. [What is a Database Table?](https://www.essentialsql.com/what-is-a-database-t)
2. [Additional Lessons](https://www.essentialsql.com/category/learn-sqlite/)

***
[<<< Back to Main](https://sangmlee76.github.io/reading-notes/)



# CHAPTER_1: SQL

- The 3 persepectives of SQL and relational database: 
1. Structure of the data (Entity-relationship diagram)
2. Data processing (dataflows)
3. SQL syntax

FOCUS: Extract information from data with SQL querying

- Data flow diagrams as a way to understand data information

- JOINs, GROUP BYs, Subqueries

- SQL -> Statistics -> Excel: Data storage-> Data interpretation -> Data visualization


## READING_NOTE:

- NULL is useful as a way to handle missing values but be very CAREFUL as it might cause inaccurate interpretation ('How does NULL work in SQL)

- RANK() vs DENSE_RANK() (Page 36, Table 1-2)

- EXIST/ NOT EXISTS over IN/NOT IN due to NULL (page 46)

- Good practice for formating SQL Queries (page 39): CamelBack, SELECT...FROM, FROM (new line subqueries), (CASE....), ... as....,..

- Example formating:

```SQL
WITH zc as(
       SELECT zc.*,
              (CASE WHEN totpop > 10000 THEN 1 ELSE 0
              END) as is_pop_10000,
              (CASE WHEN totpop > 1000 THEN 1 ELSE 0
              END) as is_pop_1000
       FROM ZipCensus zc
              )
SELECT zc.stab,
  SUM(is_pop_10000) as num_10000,
  SUM(is_pop_1000) as num_1000,
  SUM(is_pop_10000 * totpop) as pop_10000,
  SUM(is_pop_1000* totpop) as pop_1000
FROM zc
GROUP BY zc.stab
```

- How to copy formulas using only keyboard in Excel (Page 18)



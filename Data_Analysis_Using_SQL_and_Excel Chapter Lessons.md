CHAPTER_1: SQL

-- This chapter introduces SQL and relational database from several different persepectives (Which?) that are importantn for data mining and data analysis. The focus is exclusively on using databases to extract information from data (how?), rather than on the mechanics of building databases, the myriad options avaialble in designing them, or the sophisticated algorithms implemented by database engines.

-- One very importantn persepective is the data perspective - the tables themselves and the realtionships between them. Entity-relationship diagrams are good way of visualizing the structure of data in the database and the relationships among tables. Along with introducing entitiy- relationship diagrmas, the chapter also explains the vairous datasets used trhoughout this book.

-- Of course, tables and databases store data, but they dont't actually do anything. Queries extract information, transforming data into information. For some people, thinking in terms of data flow diagrams is simpler than undestanding complex SQL statements. Thsese diagrams show how various oeprations transform data. About one dozen oeprators suffice for the rich set of processing available in SQL. Dataflows are not only useful for explaining how SQL processes data; database engines generally use a form of dataflows for running SQL queries.

-- In the end, though,transforming data into formation requires SQL queries, whether simple or comples. The ofucs in this chapter, and throughout the book, is on SQL for querying. This chapter introduces the important functionaly of SQL and how it is expressed, with partifcular emphasis on JOINS, GROUP BYs, and subqueires, because these play an importantn role in dta analysis.

-- The 3 persepectives of SQL and relational database: 
1. Structure of the data (Entity-relationship diagram)
2. Data processing (dataflows)
3. SQL syntax
-- FOCUS: Extract information from data with SQL querying
-- Data flow diagrams as a way to understand data information
-- JOINs, GROUP BYs, Subqueries
-- SQL -> Statistics -> Excel: Data storage -> Data interpretation -> Data visualization


READING_NOTE:

-- NULL is useful as a way to handle missing values but be very CAREFUL as it might cause inaccurate interpretation ('How does NULL work in SQL)

--RANK() vs DENSE_RANK() (Page 36, Table 1-2)

-- EXIST/ NOT EXISTS over IN/NOT IN due to NULL (page 46)

-- Good practice for formating SQL Queries (page 39): CamelBack, SELECT...FROM, FROM (new line subqueries), (CASE....), ... as....,..

-- Example formating:
(
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
)


-- How to copy formulas using only keyboard in Excel (Page 18)



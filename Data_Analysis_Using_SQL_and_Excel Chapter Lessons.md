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

# CHAPTER_2: TABLE
- Databases are well suited to data exploration because databases are close to the data. Most relational databases are inherently parallel - meaning they can take advantage of multiple processors and multiple disks - so a database is often the best choice in terms of performance as well. Excel charting is a useful companion because it is familiar to busieness people and charts are a powerful way to communicate results. This chapter introduces several types of charts including column charts, ine charts, scatter plots, and sparklines.
- Data exploration starts by investigating the values stored in vairous columns in tables. Histograms are a good way to see distributions of values in particular columns, althrouhg numberic values often need to be grouped to see their distributions. There are various ways of grouping numeric values into ranges, including tiling - creating equal-sized groups such as quintles and deciles.
- Various other metrics are of interest in describing data in columns. The most common value is called the mode, which can be calculated in SQL.
- Ultimately, it is more efficient to investigate all columns at tonce rather than each column one at  a time. The chapter ends with a mechanism for creating a single query to summarize all cloumns at the same time. This method uses SQL or Excel to create a complex query, which is then run to get summaries for all the columns in a table. 
- The next chapter moves from just exploring and looking at the data to determining whether patterns in the data are, in fact, statistically significant.

## READING_NOTE
- When using Excel in conjunction with SQL, keep BOTH Query and the Result
- Copying data in to Excel: Use 'Text to Columns' tool/ Export data as File -> Import file into Excel
- Copy as picture for charts
- In-cell bar chart (page 58) using =REPT("g",....)
- 
- 


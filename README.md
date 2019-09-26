# SQL_for_data_analysis
A personal project that aims to equip myself with SQL knowledge for analyzing data

What's up world!

I would like to introduce to you my first personal project on Github: SQL for data analysis.The orginal purpose of this project is to show what I have learnt with SQL and apply the knowledge to some real data. 
The roadmap is as followed:

1. Learn SQL syntax through the course 'Master SQL for Data Science' by Imtiaz (https://www.udemy.com/share/1002rmAEEedVZVRHQ=/)
2. Figure out what can I do to with SQL for data in real life
3. Figure out how to mine data
4. Work on data sets and interpret the result using SQL


This is my first ever project so maybe it is late, it is never too late. 

[STEP 1]: 'Master SQL for Data Science' 20/09/2019 -- 24/09/2019

COURSE_REVIEW: 
The course provides very solid ground knowledge of SQL using PostgreSQL. My first impression about this course is it can be very structured with exercises from easy to advanced to strongly assist the progress of me. Imtiaz teaching style is something I find very enjoyable: he repeats concepts a lot and this immensely helps me in reminding the previous knowledge to be able to combine with new knowledge. All in all, a very good course and teacher. I would recommend this course to my friends if possible.



USEFUL SYNTAX: This part contains personally useful syntax and expressions I learnt or created from the course

1. COUNT()/SUM()/[...] OVER(PARTITION BY.... ORDER BY....RANGE...)

WHY_USEFUL? -- the reason this is expression is useful is because it is more efficient than a correlated subquery that I learnt earlier in the course. Moreover it is simpler to understand.

NOTE -- the default behavior of RANGE is 'between unbounded preceding and current row' or running_total. This can be replaced by expressions such as 'between 1/2/3/n preceding and current row'

2. RANK()/NTILE()/FIRST_VALUE/NTH_VALUE()

WHY_USEFUL? -- those expressions can be used to arrange and sort data which helps a lot in data analysis. For example, FIRST_VALUE can be used to find max/min in combination of ORDER BY: (first_value(salary) over(partition by department order by salary desc) first_value)
Moreover, the NTH_VALUE() expression is an extension of FIRST_VALUE and can be implemented when a specific rank is chosen. For example, in case the company wants to raise the salary for the 5th highest paid employee in each department, NTH_VALUE() will be used

3. LEAD()/LAG()

WHY_USEFUL? -- the same reason as 2. and these expressions can be used to figure out, for example, the closest highest salary of a department

4. GROUP BY GROUPING SETS/ ROLLUP/ CUBES

WHY_USEFUL? -- these expressions help sumarizing the data and are very useful when go with SUM/AVG/COUNT.

NOTE -- The difference between the 3 expressions of GROUP BY is their result combination. While GROUPING SETS only returns the result combined with the defined sets, ROLL UP returns the result grouped by EVERYTHING and EVERYTHING - 1 and so on; the last expression CUBE returns the results as if we have a C combination (mathematical term) of the the defined sets; that means if we group base on 3 sets, we will have the result of 6 different combinations of those 3 sets
-- when using GROUPING SETS, () means everything will be chosen

5. CREATE VIEW v_.......AS

WHY_USEFUL? -- THis expression saves a custom query for convenient later access

NOTE -- It is still a query so the data cannot be modified (ADD, DELETE,....)

6. FROM ..... INNER JOIN/ FULL OUTER JOIN/ LEFT OUTER JOIN/ RIGHT OUTER JOIN .... ON.....

WHY_USEFUL? These expressions provide a way to connect different tables

7. UNION/ UNION ALL/ CROSS JOIN

WHY_USEFUL? -- This can be used to stack results from 1 querry on another querry. This is particularly useful in breaking down a complicated querry into parts. For example, first querry is to find the max value UNION second querry is to find the min value

NOTE -- notice the difference between each expression

8. EXCEPT

WHY_USEFUL? -- AS A CHECKING TOOL. If we have 2 distinct querries that are supposed to return the same result, the result of those 2 querries combined by EXCEPT will be a querry with 0 row

9. FUNCTIONS: UPPER()/LOWER()/LENGTH()/TRIM()/SUBSTRING/REPLACE()/POSITION/COALESECE()/MIN()/MAX()/AVG()/SUM()/COUNT()

WHY_USEFUL? -- backbones of SQL

10. GROUP BY()/HAVING

WHY_USEFUL? -- Aggregated operations



GENERAL_THING_ABOUT_SQL:
1. EXECUTION_ORDER: FROM --> WHERE --> SELECT
2. -- SQL cares only about the data type. In other words, SQL can combine different columns as long as they are of the same data type. That is why meaning check is very important.


[STEP 2] SQL Application -  'Data Analysis using SQL and Excel' 26/09/2019 - Present

FIRST_IMPRESSION_MOTIVATION: -- Just finished the foreword of this textbook. This is a very promising book and I am excited about what I can mine from this book. The book promises to apply SQL and Excel in data mining, analysis. I do think this is very practical as on the basic level, Excel is widely used. Moreover, the data mining part comes as a plus so I may not need to look further for the same knowledge. It is exciting!
EXPECTATION_AFTER_FINISH
-- Implement SQL and Excel together
-- Able to mine data
-- Able to analyze data using various statistical methods
-- Find out what can SQL be used for the Supply Chain Industry
-- Others are just plus



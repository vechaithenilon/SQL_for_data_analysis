# Instruction

- In order to practice, the tables need to be imported to SQL. I use PostgreSQL
1. Create a blank table with columns
2. Convert .txt data to .csv using Excel
3. Import .csv data file

```SQL
CREATE TABLE orders (
	orderid integer, 
	customerid integer,
	campaignid integer,
	orderdate date,
	city char(100),
	state char(5),
	zipcode char(5),
	paymenttype char(5),
	totalprice integer,
	numorderlines integer,
	numunits integer,
PRIMARY KEY(orderid)
);
```

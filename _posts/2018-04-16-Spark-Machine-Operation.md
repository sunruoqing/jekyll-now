## SQL cheatsheet

Select

```sql

SELECT COUNT(DISTINCT Country) FROM Customers;

SELECT Count(*) AS DistinctCountries
FROM (SELECT DISTINCT Country FROM Customers);

```

OrderBy

```sql

SELECT column1, column2, ...
FROM table_name
ORDER BY column1, column2, ... ASC|DESC;

```

Insert

```sql

INSERT INTO table_name (column1, column2, column3, ...)
VALUES (value1, value2, value3, ...);

```

Update table

```sql

UPDATE Customers
SET ContactName = 'Alfred Schmidt', City= 'Frankfurt'
WHERE CustomerID = 1;

```
Delete Table

```sql
DELETE FROM Customers
WHERE CustomerName='Alfreds Futterkiste';
```

Select Top

```sql
SELECT * FROM Customers
WHERE Country='Germany'
LIMIT 3;

SELECT column_name(s)
FROM table_name
WHERE ROWNUM <= number;

SELECT TOP number|percent column_name(s)
FROM table_name
WHERE condition;
```

Min and Max
```sql
SELECT MIN(Price) AS SmallestPrice
FROM Products;
```

Like
```sql
SELECT column1, column2, ...
FROM table_name
WHERE columnN LIKE 'a_%_%';
```

## Operations on Spark

```bash
ssh lxhnl016
upyter notebook --ip 0.0.0.0 --port 1915
pyspark

https://lxhnl016:1915
```


```python
import findspark
findspark.init()
from pyspark.sql import SparkSession

spark = SparkSession.builder \
        .master('yarn') \
        .appName("Mandoline") \
        .config('spark.executor.memory', '10g') \
        .config('spark.executor.core', '1') \
        .config('spark.driver.memory', '10g') \
        .config('spark.yarn.executor.memoryOverhead', '10000') \
        .config("spark.jars", "/usr/hdp/current/hive-server2-hive2/lib/postgresql-9.4.1208.jre7.jar") \
        .enableHiveSupport().getOrCreate()
        
value_reporter = data_queries.value_reporter(spark, VR_DB, VR, START_DATE, END_DATE)
grid = data_queries.grid(spark, GRID_DB, GRID)

```

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



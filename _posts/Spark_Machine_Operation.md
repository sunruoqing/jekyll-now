```Bash

ssh lxhnl016
upyter notebook --ip 0.0.0.0 --port 1915
pyspark

https://lxhnl016:1915
```


```Python
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

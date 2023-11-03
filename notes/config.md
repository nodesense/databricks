Spark config

possible fix for mount error with s3 bucket

```
spark.driver.extraJavaOptions="-Dio.netty.tryReflectionSetAccessible=true"
spark.executor.extraJavaOptions="-Dio.netty.tryReflectionSetAccessible=true"
```

# DataBricks Cli

Download and install

### use DataBricks Cli to set secrects and scope

```
databricks secrets create-scope  gks_s3
 

databricks secrets  list-scopes


databricks secrets  list-secrets gks_s3

 
databricks secrets   put-secret gks_s3 s3_username
databricks secrets   put-secret gks_s3 s3_password
databricks secrets   put-secret gks_s3 s3_host


databricks secrets   list-secrets gks_s3


databricks secrets   delete-secret gks_s3 s3_host

databricks secrets   list-secrets gks_s3

```


# Use DB Utils to work with secret

```
dbutils.secrets.listScopes()

username = dbutils.secrets.get(scope = "gks_s3", key = "s3_username")
password = dbutils.secrets.get(scope = "gks_s3", key = "s3_password")

print (username)
print(password)

for char in username:
    print(char, end=" ")


for char in password:
    print(char, end=" ")
```

## Secret with environment variables

```
MY_USERNAME={{secrets/gks_s3/s3_username}}
MY_PASSWORD={{secrets/gks_s3/s3_password}}

```

```
import os
print(os.getenv('PYSPARK_PYTHON'))
print(os.getenv('MY_USERNAME'))
print(os.getenv('MY_PASSWORD'))


for char in os.getenv('MY_PASSWORD'):
    print(char, end=" ")
```




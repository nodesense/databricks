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

```

## Secret with environment variables

```


myusername={{secrets/gks_s3/s3_username}}
mypassword={{secrets/gks_s3/s3_password}}
```



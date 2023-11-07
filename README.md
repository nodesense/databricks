# Code share

https://demo.firepad.io/#RfDj1v1fi4



# databricks

https://github.com/nodesense/deloitte-pyspark-april-2022/blob/main/DataBricks-Notebooks/S021-MovieLens.py

AWS SCP Policy for organization account to disable access to specific regions

```
{
  "Version": "2012-10-17",
  "Statement": [
    {
      "Effect": "Deny",
      "Action": "*",
      "Resource": "*",
      "Condition": {
        "StringNotEquals": {
          "aws:RequestedRegion": "us-east-2"
        }
      }
    }
  ]
}
```

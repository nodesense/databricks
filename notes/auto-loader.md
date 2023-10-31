Reference Articles

https://learn.microsoft.com/en-us/azure/databricks/getting-started/etl-quick-start


```python
checkpoint_path = '/tmp/delta/population_data/_checkpoints'
# in the place of gks, use your s3 mount
write_path = '/mnt/gks/delta/population_data'

upload_path = "/mnt/gks/population"

# Set up the stream to begin reading incoming files from the
# upload_path location.
df = spark.readStream.format('cloudFiles') \
  .option('cloudFiles.format', 'csv') \
  .option('header', 'true') \
  .schema('city string, year int, population long') \
  .load(upload_path)

# Start the stream.
# Use the checkpoint_path location to keep a record of all files that
# have already been uploaded to the upload_path location.
# For those that have been uploaded since the last check,
# write the newly-uploaded files' data to the write_path location.
df.writeStream.format('delta') \
  .option('checkpointLocation', checkpoint_path) \
  .start(write_path)
```

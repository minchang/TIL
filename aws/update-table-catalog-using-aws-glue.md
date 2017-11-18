# Update table catalog using AWS Glue

If you created a table in AWS Glue using a Crawler that scans your S3 bucket, and new files flow into the S3 bucket continuesly, you need to keep the table catalog up to date by running Crawler periodically. Otherwise, you might get the same result whenever you re-query the table even though the data continues to grow. Keep in mind this if you use AWS Athena to query against a table defined in AWS Glue.

#Resolving "HIVE_CANNOT_OPEN_SPLIT" error from Athena

> If you use Amazon EMR along with EMRFS to upload encrypted Parquet files, you must disable multipart uploads (set fs.s3n.multipart.uploads.enabled to false); otherwise, Athena is unable to determine the Parquet file length and a HIVE_CANNOT_OPEN_SPLIT error occurs. For more information, see Configure Multipart Upload for Amazon S3 in the EMR Management Guide.

[http://docs.aws.amazon.com/athena/latest/ug/encryption.html](http://docs.aws.amazon.com/athena/latest/ug/encryption.html)

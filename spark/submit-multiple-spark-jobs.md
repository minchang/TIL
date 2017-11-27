# Submit multple spark jobs from one server

If you try to submit more than 17 Spark jobs simultaneously, jobs submitted after the 17th job may be failed with error messages below.

```
ERROR SparkUI: Failed to bind SparkUI java.net.BindException: Address already in use: Service 'SparkUI' failed after 16 retries!
```

This happens because Spark tries to bind your application to the Master UI via a port starting at 4040. If the port 4040 is in use, Spark tries to the next port, 4041, and retries up to 16 times until an available port is found. If Spark cannot find a port after 16 times of re-try, Spark discards the job submission. To avoid this, you can specify a port manually when you submit multple Spark jobs.

```
port=4040

for job in jobarray 
do
	/usr/bin/spark-submit --conf spark.ui.port=$port --class XXX ./job.jar --jobparam=$job
	port=$((port + 1))
done
```

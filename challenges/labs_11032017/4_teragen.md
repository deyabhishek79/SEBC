```
[reilly@ip-172-31-34-47 ~]$ time /usr/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapreduce.job.maps=12 -Ddfs.blocksize=33554432 -Dmapreduce.map.memory.mb=1024 65536000 /user/reilly/tgen
17/11/03 16:44:20 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-34-47.ec2.internal/172.31.34.47:8032
17/11/03 16:44:20 INFO terasort.TeraSort: Generating 65536000 using 12
17/11/03 16:44:20 INFO mapreduce.JobSubmitter: number of splits:12
17/11/03 16:44:20 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509741082613_0001
17/11/03 16:44:21 INFO impl.YarnClientImpl: Submitted application application_1509741082613_0001
17/11/03 16:44:21 INFO mapreduce.Job: The url to track the job: http://ip-172-31-34-47.ec2.internal:8088/proxy/application_1509741082613_0001/
17/11/03 16:44:21 INFO mapreduce.Job: Running job: job_1509741082613_0001
17/11/03 16:44:28 INFO mapreduce.Job: Job job_1509741082613_0001 running in uber mode : false
17/11/03 16:44:28 INFO mapreduce.Job:  map 0% reduce 0%
17/11/03 16:44:42 INFO mapreduce.Job:  map 9% reduce 0%
17/11/03 16:44:43 INFO mapreduce.Job:  map 19% reduce 0%
17/11/03 16:44:45 INFO mapreduce.Job:  map 22% reduce 0%
17/11/03 16:44:46 INFO mapreduce.Job:  map 28% reduce 0%
17/11/03 16:44:48 INFO mapreduce.Job:  map 31% reduce 0%
17/11/03 16:44:49 INFO mapreduce.Job:  map 34% reduce 0%
17/11/03 16:44:51 INFO mapreduce.Job:  map 35% reduce 0%
17/11/03 16:44:52 INFO mapreduce.Job:  map 38% reduce 0%
17/11/03 16:44:54 INFO mapreduce.Job:  map 40% reduce 0%
17/11/03 16:44:55 INFO mapreduce.Job:  map 42% reduce 0%
17/11/03 16:44:57 INFO mapreduce.Job:  map 44% reduce 0%
17/11/03 16:44:58 INFO mapreduce.Job:  map 47% reduce 0%
17/11/03 16:45:01 INFO mapreduce.Job:  map 49% reduce 0%
17/11/03 16:45:02 INFO mapreduce.Job:  map 52% reduce 0%
17/11/03 16:45:04 INFO mapreduce.Job:  map 54% reduce 0%
17/11/03 16:45:05 INFO mapreduce.Job:  map 57% reduce 0%
17/11/03 16:45:07 INFO mapreduce.Job:  map 59% reduce 0%
17/11/03 16:45:08 INFO mapreduce.Job:  map 61% reduce 0%
17/11/03 16:45:10 INFO mapreduce.Job:  map 63% reduce 0%
17/11/03 16:45:11 INFO mapreduce.Job:  map 65% reduce 0%
17/11/03 16:45:13 INFO mapreduce.Job:  map 67% reduce 0%
17/11/03 16:45:14 INFO mapreduce.Job:  map 70% reduce 0%
17/11/03 16:45:16 INFO mapreduce.Job:  map 71% reduce 0%
17/11/03 16:45:17 INFO mapreduce.Job:  map 74% reduce 0%
17/11/03 16:45:19 INFO mapreduce.Job:  map 75% reduce 0%
17/11/03 16:45:20 INFO mapreduce.Job:  map 79% reduce 0%
17/11/03 16:45:22 INFO mapreduce.Job:  map 80% reduce 0%
17/11/03 16:45:23 INFO mapreduce.Job:  map 84% reduce 0%
17/11/03 16:45:25 INFO mapreduce.Job:  map 85% reduce 0%
17/11/03 16:45:26 INFO mapreduce.Job:  map 88% reduce 0%
17/11/03 16:45:28 INFO mapreduce.Job:  map 90% reduce 0%
17/11/03 16:45:29 INFO mapreduce.Job:  map 94% reduce 0%
17/11/03 16:45:31 INFO mapreduce.Job:  map 95% reduce 0%
17/11/03 16:45:32 INFO mapreduce.Job:  map 98% reduce 0%
17/11/03 16:45:35 INFO mapreduce.Job:  map 99% reduce 0%
17/11/03 16:45:38 INFO mapreduce.Job:  map 100% reduce 0%
17/11/03 16:45:38 INFO mapreduce.Job: Job job_1509741082613_0001 completed successfully
17/11/03 16:45:38 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=1466150
		FILE: Number of read operations=0
			FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=1025
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=48
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=24
	Job Counters 
		Launched map tasks=12
		Other local map tasks=12
		Total time spent by all maps in occupied slots (ms)=739611
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=739611
		Total vcore-seconds taken by all map tasks=739611
		Total megabyte-seconds taken by all map tasks=757361664
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=1025
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=2194
		CPU time spent (ms)=157470
		Physical memory (bytes) snapshot=4341280768
		Virtual memory (bytes) snapshot=18935558144
		Total committed heap usage (bytes)=4631560192
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=6553600000

real	1m20.830s
user	0m6.021s
sys	0m0.286s

```
# Teragen Output

```

[reilly@ip-172-31-34-47 ~]$ hadoop fs -ls  /user/reilly/tgen
Found 13 items
-rw-r--r--   3 reilly supergroup          0 2017-11-03 16:45 /user/reilly/tgen/_SUCCESS
-rw-r--r--   3 reilly supergroup  546133400 2017-11-03 16:45 /user/reilly/tgen/part-m-00000
-rw-r--r--   3 reilly supergroup  546133300 2017-11-03 16:45 /user/reilly/tgen/part-m-00001
-rw-r--r--   3 reilly supergroup  546133300 2017-11-03 16:45 /user/reilly/tgen/part-m-00002
-rw-r--r--   3 reilly supergroup  546133400 2017-11-03 16:45 /user/reilly/tgen/part-m-00003
-rw-r--r--   3 reilly supergroup  546133300 2017-11-03 16:45 /user/reilly/tgen/part-m-00004
-rw-r--r--   3 reilly supergroup  546133300 2017-11-03 16:45 /user/reilly/tgen/part-m-00005
-rw-r--r--   3 reilly supergroup  546133400 2017-11-03 16:45 /user/reilly/tgen/part-m-00006
-rw-r--r--   3 reilly supergroup  546133300 2017-11-03 16:45 /user/reilly/tgen/part-m-00007
-rw-r--r--   3 reilly supergroup  546133300 2017-11-03 16:45 /user/reilly/tgen/part-m-00008
-rw-r--r--   3 reilly supergroup  546133400 2017-11-03 16:45 /user/reilly/tgen/part-m-00009
-rw-r--r--   3 reilly supergroup  546133300 2017-11-03 16:45 /user/reilly/tgen/part-m-00010
-rw-r--r--   3 reilly supergroup  546133300 2017-11-03 16:45 /user/reilly/tgen/part-m-00011

```

# FSCK

```

[reilly@ip-172-31-34-47 ~]$ hadoop fsck -blocks /user/reilly/tgen
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-34-47.ec2.internal:50070
FSCK started by reilly (auth:KERBEROS_SSL) from /172.31.34.47 for path /user/reilly/tgen at Fri Nov 03 17:22:07 EDT 2017
.............Status: HEALTHY
 Total size:	6553600000 B
 Total dirs:	1
 Total files:	13
 Total symlinks:		0
 Total blocks (validated):	204 (avg. block size 32125490 B)
 Minimally replicated blocks:	204 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Fri Nov 03 17:22:07 EDT 2017 in 14 milliseconds


The filesystem under path '/user/reilly/tgen' is HEALTHY

``` 

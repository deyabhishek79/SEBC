# Teragen command

```
[hdfs@ip-172-31-45-139 root]$ time /usr/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Dmapreduce.job.maps=8 -Ddfs.blocksize=67108864 -Dmapreduce.map.memory.mb=512 65536000  /user/jimenez/tgen
17/10/13 12:14:19 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-45-139.ec2.internal/172.31.45.139:8032
17/10/13 12:14:19 INFO terasort.TeraSort: Generating 65536000 using 8
17/10/13 12:14:19 INFO mapreduce.JobSubmitter: number of splits:8
17/10/13 12:14:20 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507909839182_0001
17/10/13 12:14:20 INFO impl.YarnClientImpl: Submitted application application_1507909839182_0001
17/10/13 12:14:20 INFO mapreduce.Job: The url to track the job: http://ip-172-31-45-139.ec2.internal:8088/proxy/application_1507909839182_0001/
17/10/13 12:14:20 INFO mapreduce.Job: Running job: job_1507909839182_0001
17/10/13 12:14:27 INFO mapreduce.Job: Job job_1507909839182_0001 running in uber mode : false
17/10/13 12:14:27 INFO mapreduce.Job:  map 0% reduce 0%
17/10/13 12:14:39 INFO mapreduce.Job:  map 5% reduce 0%
17/10/13 12:14:41 INFO mapreduce.Job:  map 11% reduce 0%
17/10/13 12:14:42 INFO mapreduce.Job:  map 22% reduce 0%
17/10/13 12:14:44 INFO mapreduce.Job:  map 25% reduce 0%
17/10/13 12:14:45 INFO mapreduce.Job:  map 28% reduce 0%
17/10/13 12:14:47 INFO mapreduce.Job:  map 29% reduce 0%
17/10/13 12:14:48 INFO mapreduce.Job:  map 31% reduce 0%
17/10/13 12:14:50 INFO mapreduce.Job:  map 32% reduce 0%
17/10/13 12:14:51 INFO mapreduce.Job:  map 35% reduce 0%
17/10/13 12:14:53 INFO mapreduce.Job:  map 36% reduce 0%
17/10/13 12:14:54 INFO mapreduce.Job:  map 39% reduce 0%
17/10/13 12:14:56 INFO mapreduce.Job:  map 41% reduce 0%
17/10/13 12:14:57 INFO mapreduce.Job:  map 44% reduce 0%
17/10/13 12:14:59 INFO mapreduce.Job:  map 45% reduce 0%
17/10/13 12:15:00 INFO mapreduce.Job:  map 48% reduce 0%
17/10/13 12:15:02 INFO mapreduce.Job:  map 49% reduce 0%
17/10/13 12:15:03 INFO mapreduce.Job:  map 52% reduce 0%
17/10/13 12:15:05 INFO mapreduce.Job:  map 54% reduce 0%
17/10/13 12:15:06 INFO mapreduce.Job:  map 57% reduce 0%
17/10/13 12:15:08 INFO mapreduce.Job:  map 59% reduce 0%
17/10/13 12:15:09 INFO mapreduce.Job:  map 62% reduce 0%
17/10/13 12:15:11 INFO mapreduce.Job:  map 63% reduce 0%
17/10/13 12:15:12 INFO mapreduce.Job:  map 66% reduce 0%
17/10/13 12:15:14 INFO mapreduce.Job:  map 67% reduce 0%
17/10/13 12:15:15 INFO mapreduce.Job:  map 70% reduce 0%
17/10/13 12:15:17 INFO mapreduce.Job:  map 71% reduce 0%
17/10/13 12:15:18 INFO mapreduce.Job:  map 74% reduce 0%
17/10/13 12:15:20 INFO mapreduce.Job:  map 76% reduce 0%
17/10/13 12:15:21 INFO mapreduce.Job:  map 79% reduce 0%
17/10/13 12:15:23 INFO mapreduce.Job:  map 83% reduce 0%
17/10/13 12:15:24 INFO mapreduce.Job:  map 85% reduce 0%
17/10/13 12:15:25 INFO mapreduce.Job:  map 86% reduce 0%
17/10/13 12:15:26 INFO mapreduce.Job:  map 87% reduce 0%
17/10/13 12:15:27 INFO mapreduce.Job:  map 89% reduce 0%
17/10/13 12:15:29 INFO mapreduce.Job:  map 91% reduce 0%
17/10/13 12:15:32 INFO mapreduce.Job:  map 94% reduce 0%
17/10/13 12:15:35 INFO mapreduce.Job:  map 97% reduce 0%
17/10/13 12:15:38 INFO mapreduce.Job:  map 100% reduce 0%
17/10/13 12:15:39 INFO mapreduce.Job: Job job_1507909839182_0001 completed successfully
17/10/13 12:15:39 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=977592
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=682
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=32
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters 
		Launched map tasks=8
		Other local map tasks=8
		Total time spent by all maps in occupied slots (ms)=402545
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=402545
		Total vcore-seconds taken by all map tasks=402545
		Total megabyte-seconds taken by all map tasks=412206080
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Input split bytes=682
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1578
		CPU time spent (ms)=133460
		Physical memory (bytes) snapshot=1429356544
		Virtual memory (bytes) snapshot=9107808256
		Total committed heap usage (bytes)=1791492096
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=140750829423462787
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=6553600000

real	1m22.947s
user	0m6.497s
sys	0m0.294s
[hdfs@ip-172-31-45-139 root]$ hadoop fsck -blocks /user/jimenez
DEPRECATED: Use of this script to execute hdfs command is deprecated.
Instead use the hdfs command for it.

Connecting to namenode via http://ip-172-31-45-139.ec2.internal:50070
FSCK started by hdfs (auth:SIMPLE) from /172.31.45.139 for path /user/jimenez at Fri Oct 13 12:16:15 EDT 2017
.........Status: HEALTHY
 Total size:	6553600000 B
 Total dirs:	2
 Total files:	9
 Total symlinks:		0
 Total blocks (validated):	104 (avg. block size 63015384 B)
 Minimally replicated blocks:	104 (100.0 %)
 Over-replicated blocks:	0 (0.0 %)
 Under-replicated blocks:	0 (0.0 %)
 Mis-replicated blocks:		0 (0.0 %)
 Default replication factor:	3
 Average block replication:	3.0
 Corrupt blocks:		0
 Missing replicas:		0 (0.0 %)
 Number of data-nodes:		4
 Number of racks:		1
FSCK ended at Fri Oct 13 12:16:15 EDT 2017 in 6 milliseconds


The filesystem under path '/user/jimenez' is HEALTHY
[hdfs@ip-172-31-45-139 root]$ hdfs dfs -ls /user/jimenez/tgen
Found 9 items
-rw-r--r--   3 hdfs supergroup          0 2017-10-13 12:15 /user/jimenez/tgen/_SUCCESS
-rw-r--r--   3 hdfs supergroup  819200000 2017-10-13 12:15 /user/jimenez/tgen/part-m-00000
-rw-r--r--   3 hdfs supergroup  819200000 2017-10-13 12:15 /user/jimenez/tgen/part-m-00001
-rw-r--r--   3 hdfs supergroup  819200000 2017-10-13 12:15 /user/jimenez/tgen/part-m-00002
-rw-r--r--   3 hdfs supergroup  819200000 2017-10-13 12:15 /user/jimenez/tgen/part-m-00003
-rw-r--r--   3 hdfs supergroup  819200000 2017-10-13 12:15 /user/jimenez/tgen/part-m-00004
-rw-r--r--   3 hdfs supergroup  819200000 2017-10-13 12:15 /user/jimenez/tgen/part-m-00005
-rw-r--r--   3 hdfs supergroup  819200000 2017-10-13 12:15 /user/jimenez/tgen/part-m-00006
-rw-r--r--   3 hdfs supergroup  819200000 2017-10-13 12:15 /user/jimenez/tgen/part-m-00007
```
Note that you've run the job as the superuser `hdfs`, not the test user `jimenez`

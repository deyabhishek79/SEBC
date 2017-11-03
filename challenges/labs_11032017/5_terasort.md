# Terasort

```

[reilly@ip-172-31-34-47 ~]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/reilly/teragen /user/reilly/tsort
17/11/03 18:07:57 INFO terasort.TeraSort: starting
17/11/03 18:07:58 INFO hdfs.DFSClient: Created token for reilly: HDFS_DELEGATION_TOKEN owner=reilly@DEYABHISHEK79.FNG, renewer=yarn, realUser=, issueDate=1509746878505, maxDate=1510351678505, sequenceNumber=7, masterKeyId=4 on 172.31.34.47:8020
17/11/03 18:07:58 INFO security.TokenCache: Got dt for hdfs://ip-172-31-34-47.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.34.47:8020, Ident: (token for reilly: HDFS_DELEGATION_TOKEN owner=reilly@DEYABHISHEK79.FNG, renewer=yarn, realUser=, issueDate=1509746878505, maxDate=1510351678505, sequenceNumber=7, masterKeyId=4)
17/11/03 18:07:58 ERROR terasort.TeraSort: Input path does not exist: hdfs://ip-172-31-34-47.ec2.internal:8020/user/reilly/teragen
[reilly@ip-172-31-34-47 ~]$ hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/reilly/tgen /user/reilly/tsort
17/11/03 18:08:14 INFO terasort.TeraSort: starting
17/11/03 18:08:16 INFO hdfs.DFSClient: Created token for reilly: HDFS_DELEGATION_TOKEN owner=reilly@DEYABHISHEK79.FNG, renewer=yarn, realUser=, issueDate=1509746896296, maxDate=1510351696296, sequenceNumber=8, masterKeyId=4 on 172.31.34.47:8020
17/11/03 18:08:16 INFO security.TokenCache: Got dt for hdfs://ip-172-31-34-47.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.34.47:8020, Ident: (token for reilly: HDFS_DELEGATION_TOKEN owner=reilly@DEYABHISHEK79.FNG, renewer=yarn, realUser=, issueDate=1509746896296, maxDate=1510351696296, sequenceNumber=8, masterKeyId=4)
17/11/03 18:08:16 INFO input.FileInputFormat: Total input paths to process : 12
Spent 355ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 361ms
Sampling 10 splits of 204
Making 8 from 100000 sampled records
Computing parititions took 874ms
Spent 1237ms computing partitions.
17/11/03 18:08:17 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-34-47.ec2.internal/172.31.34.47:8032
17/11/03 18:08:17 INFO mapreduce.JobSubmitter: number of splits:204
17/11/03 18:08:18 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509745615368_0001
17/11/03 18:08:18 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.34.47:8020, Ident: (token for reilly: HDFS_DELEGATION_TOKEN owner=reilly@DEYABHISHEK79.FNG, renewer=yarn, realUser=, issueDate=1509746896296, maxDate=1510351696296, sequenceNumber=8, masterKeyId=4)
17/11/03 18:08:19 INFO impl.YarnClientImpl: Submitted application application_1509745615368_0001
17/11/03 18:08:19 INFO mapreduce.Job: The url to track the job: http://ip-172-31-34-47.ec2.internal:8088/proxy/application_1509745615368_0001/
17/11/03 18:08:19 INFO mapreduce.Job: Running job: job_1509745615368_0001
17/11/03 18:08:28 INFO mapreduce.Job: Job job_1509745615368_0001 running in uber mode : false
17/11/03 18:08:28 INFO mapreduce.Job:  map 0% reduce 0%
17/11/03 18:08:40 INFO mapreduce.Job:  map 1% reduce 0%
17/11/03 18:08:49 INFO mapreduce.Job:  map 7% reduce 0%
17/11/03 18:08:50 INFO mapreduce.Job:  map 8% reduce 0%
17/11/03 18:08:51 INFO mapreduce.Job:  map 9% reduce 0%
17/11/03 18:09:00 INFO mapreduce.Job:  map 10% reduce 0%
17/11/03 18:09:01 INFO mapreduce.Job:  map 12% reduce 0%
17/11/03 18:09:02 INFO mapreduce.Job:  map 16% reduce 0%
17/11/03 18:09:10 INFO mapreduce.Job:  map 17% reduce 0%
17/11/03 18:09:11 INFO mapreduce.Job:  map 18% reduce 0%
17/11/03 18:09:13 INFO mapreduce.Job:  map 19% reduce 0%
17/11/03 18:09:14 INFO mapreduce.Job:  map 20% reduce 0%
17/11/03 18:09:15 INFO mapreduce.Job:  map 22% reduce 0%
17/11/03 18:09:16 INFO mapreduce.Job:  map 24% reduce 0%
17/11/03 18:09:20 INFO mapreduce.Job:  map 25% reduce 0%
17/11/03 18:09:25 INFO mapreduce.Job:  map 26% reduce 0%
17/11/03 18:09:26 INFO mapreduce.Job:  map 27% reduce 0%
17/11/03 18:09:28 INFO mapreduce.Job:  map 30% reduce 0%
17/11/03 18:09:29 INFO mapreduce.Job:  map 31% reduce 0%
17/11/03 18:09:30 INFO mapreduce.Job:  map 32% reduce 0%
17/11/03 18:09:36 INFO mapreduce.Job:  map 33% reduce 0%
17/11/03 18:09:37 INFO mapreduce.Job:  map 34% reduce 0%
17/11/03 18:09:40 INFO mapreduce.Job:  map 36% reduce 0%
17/11/03 18:09:41 INFO mapreduce.Job:  map 40% reduce 0%
17/11/03 18:09:49 INFO mapreduce.Job:  map 42% reduce 0%
17/11/03 18:09:50 INFO mapreduce.Job:  map 43% reduce 0%
17/11/03 18:09:52 INFO mapreduce.Job:  map 44% reduce 0%
17/11/03 18:09:54 INFO mapreduce.Job:  map 47% reduce 0%
17/11/03 18:10:00 INFO mapreduce.Job:  map 48% reduce 0%
17/11/03 18:10:01 INFO mapreduce.Job:  map 49% reduce 0%
17/11/03 18:10:02 INFO mapreduce.Job:  map 50% reduce 0%
17/11/03 18:10:04 INFO mapreduce.Job:  map 51% reduce 0%
17/11/03 18:10:08 INFO mapreduce.Job:  map 55% reduce 0%
17/11/03 18:10:11 INFO mapreduce.Job:  map 56% reduce 0%
17/11/03 18:10:14 INFO mapreduce.Job:  map 57% reduce 0%
17/11/03 18:10:15 INFO mapreduce.Job:  map 58% reduce 0%
17/11/03 18:10:17 INFO mapreduce.Job:  map 59% reduce 0%
17/11/03 18:10:20 INFO mapreduce.Job:  map 60% reduce 0%
17/11/03 18:10:21 INFO mapreduce.Job:  map 63% reduce 0%
17/11/03 18:10:23 INFO mapreduce.Job:  map 64% reduce 0%
17/11/03 18:10:26 INFO mapreduce.Job:  map 65% reduce 0%
17/11/03 18:10:27 INFO mapreduce.Job:  map 66% reduce 0%
17/11/03 18:10:29 INFO mapreduce.Job:  map 67% reduce 0%
17/11/03 18:10:32 INFO mapreduce.Job:  map 68% reduce 0%
17/11/03 18:10:34 INFO mapreduce.Job:  map 71% reduce 0%
17/11/03 18:10:36 INFO mapreduce.Job:  map 72% reduce 0%
17/11/03 18:10:37 INFO mapreduce.Job:  map 73% reduce 0%
17/11/03 18:10:38 INFO mapreduce.Job:  map 74% reduce 0%
17/11/03 18:10:40 INFO mapreduce.Job:  map 75% reduce 0%
17/11/03 18:10:45 INFO mapreduce.Job:  map 76% reduce 0%
17/11/03 18:10:46 INFO mapreduce.Job:  map 77% reduce 0%
17/11/03 18:10:47 INFO mapreduce.Job:  map 79% reduce 0%
17/11/03 18:10:48 INFO mapreduce.Job:  map 80% reduce 0%
17/11/03 18:10:49 INFO mapreduce.Job:  map 81% reduce 0%
17/11/03 18:10:53 INFO mapreduce.Job:  map 82% reduce 0%
17/11/03 18:10:55 INFO mapreduce.Job:  map 83% reduce 0%
17/11/03 18:10:57 INFO mapreduce.Job:  map 84% reduce 0%
17/11/03 18:10:58 INFO mapreduce.Job:  map 85% reduce 0%
17/11/03 18:11:00 INFO mapreduce.Job:  map 88% reduce 0%
17/11/03 18:11:04 INFO mapreduce.Job:  map 89% reduce 0%
17/11/03 18:11:06 INFO mapreduce.Job:  map 89% reduce 3%
17/11/03 18:11:08 INFO mapreduce.Job:  map 89% reduce 5%
17/11/03 18:11:10 INFO mapreduce.Job:  map 89% reduce 10%
17/11/03 18:11:11 INFO mapreduce.Job:  map 89% reduce 13%
17/11/03 18:11:12 INFO mapreduce.Job:  map 90% reduce 16%
17/11/03 18:11:13 INFO mapreduce.Job:  map 91% reduce 21%
17/11/03 18:11:14 INFO mapreduce.Job:  map 92% reduce 23%
17/11/03 18:11:15 INFO mapreduce.Job:  map 93% reduce 24%
17/11/03 18:11:16 INFO mapreduce.Job:  map 93% reduce 25%
17/11/03 18:11:19 INFO mapreduce.Job:  map 94% reduce 27%
17/11/03 18:11:22 INFO mapreduce.Job:  map 95% reduce 27%
17/11/03 18:11:24 INFO mapreduce.Job:  map 97% reduce 27%
17/11/03 18:11:25 INFO mapreduce.Job:  map 98% reduce 28%
17/11/03 18:11:28 INFO mapreduce.Job:  map 99% reduce 28%
17/11/03 18:11:30 INFO mapreduce.Job:  map 100% reduce 29%
17/11/03 18:11:33 INFO mapreduce.Job:  map 100% reduce 37%
17/11/03 18:11:34 INFO mapreduce.Job:  map 100% reduce 59%
17/11/03 18:11:36 INFO mapreduce.Job:  map 100% reduce 60%
17/11/03 18:11:37 INFO mapreduce.Job:  map 100% reduce 68%
17/11/03 18:11:39 INFO mapreduce.Job:  map 100% reduce 69%
17/11/03 18:11:40 INFO mapreduce.Job:  map 100% reduce 78%
17/11/03 18:11:42 INFO mapreduce.Job:  map 100% reduce 79%
17/11/03 18:11:43 INFO mapreduce.Job:  map 100% reduce 85%
17/11/03 18:11:45 INFO mapreduce.Job:  map 100% reduce 88%
17/11/03 18:11:46 INFO mapreduce.Job:  map 100% reduce 92%
17/11/03 18:11:47 INFO mapreduce.Job:  map 100% reduce 93%
17/11/03 18:11:48 INFO mapreduce.Job:  map 100% reduce 96%
17/11/03 18:11:49 INFO mapreduce.Job:  map 100% reduce 97%
17/11/03 18:11:51 INFO mapreduce.Job:  map 100% reduce 98%
17/11/03 18:11:52 INFO mapreduce.Job:  map 100% reduce 99%
17/11/03 18:11:55 INFO mapreduce.Job:  map 100% reduce 100%
17/11/03 18:11:55 INFO mapreduce.Job: Job job_1509745615368_0001 completed successfully
17/11/03 18:11:55 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=2909611417
		FILE: Number of bytes written=5782134011
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=6553627540
		HDFS: Number of bytes written=6553600000
		HDFS: Number of read operations=636
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters 
		Launched map tasks=204
		Launched reduce tasks=8
		Data-local map tasks=203
		Rack-local map tasks=1
		Total time spent by all maps in occupied slots (ms)=2223057
		Total time spent by all reduces in occupied slots (ms)=391141
		Total time spent by all map tasks (ms)=2223057
		Total time spent by all reduce tasks (ms)=391141
		Total vcore-seconds taken by all map tasks=2223057
		Total vcore-seconds taken by all reduce tasks=391141
		Total megabyte-seconds taken by all map tasks=2276410368
		Total megabyte-seconds taken by all reduce tasks=400528384
	Map-Reduce Framework
		Map input records=65536000
		Map output records=65536000
		Map output bytes=6684672000
		Map output materialized bytes=2846142396
		Input split bytes=27540
		Combine input records=0
		Combine output records=0
		Reduce input groups=65536000
		Reduce shuffle bytes=2846142396
		Reduce input records=65536000
		Reduce output records=65536000
		Spilled Records=131072000
		Shuffled Maps =1632
		Failed Shuffles=0
		Merged Map outputs=1632
		GC time elapsed (ms)=26441
		CPU time spent (ms)=1027950
		Physical memory (bytes) snapshot=101509988352
		Virtual memory (bytes) snapshot=334470782976
		Total committed heap usage (bytes)=117920235520
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=6553600000
	File Output Format Counters 
		Bytes Written=6553600000
17/11/03 18:11:55 INFO terasort.TeraSort: done
```

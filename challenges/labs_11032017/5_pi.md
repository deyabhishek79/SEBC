# PI program

```

[frankola@ip-172-31-34-47 ~]$ yarn jar /opt/cloudera/parcels/CDH/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar pi 50 100
Number of Maps  = 50
Samples per Map = 100
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Wrote input for Map #3
Wrote input for Map #4
Wrote input for Map #5
Wrote input for Map #6
Wrote input for Map #7
Wrote input for Map #8
Wrote input for Map #9
Wrote input for Map #10
Wrote input for Map #11
Wrote input for Map #12
Wrote input for Map #13
Wrote input for Map #14
Wrote input for Map #15
Wrote input for Map #16
Wrote input for Map #17
Wrote input for Map #18
Wrote input for Map #19
Wrote input for Map #20
Wrote input for Map #21
Wrote input for Map #22
Wrote input for Map #23
Wrote input for Map #24
Wrote input for Map #25
Wrote input for Map #26
Wrote input for Map #27
Wrote input for Map #28
Wrote input for Map #29
Wrote input for Map #30
Wrote input for Map #31
Wrote input for Map #32
Wrote input for Map #33
Wrote input for Map #34
Wrote input for Map #35
Wrote input for Map #36
Wrote input for Map #37
Wrote input for Map #38
Wrote input for Map #39
Wrote input for Map #40
Wrote input for Map #41
Wrote input for Map #42
Wrote input for Map #43
Wrote input for Map #44
Wrote input for Map #45
Wrote input for Map #46
Wrote input for Map #47
Wrote input for Map #48
Wrote input for Map #49
Starting Job
17/11/03 17:26:17 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-34-47.ec2.internal/172.31.34.47:8032
17/11/03 17:26:17 INFO hdfs.DFSClient: Created token for frankola: HDFS_DELEGATION_TOKEN owner=frankola@DEYABHISHEK79.FNG, renewer=yarn, realUser=, issueDate=1509744377215, maxDate=1510349177215, sequenceNumber=1, masterKeyId=2 on 172.31.34.47:8020
17/11/03 17:26:17 INFO security.TokenCache: Got dt for hdfs://ip-172-31-34-47.ec2.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.34.47:8020, Ident: (token for frankola: HDFS_DELEGATION_TOKEN owner=frankola@DEYABHISHEK79.FNG, renewer=yarn, realUser=, issueDate=1509744377215, maxDate=1510349177215, sequenceNumber=1, masterKeyId=2)
17/11/03 17:26:17 INFO input.FileInputFormat: Total input paths to process : 50
17/11/03 17:26:17 INFO mapreduce.JobSubmitter: number of splits:50
17/11/03 17:26:17 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1509743434994_0001
17/11/03 17:26:17 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.34.47:8020, Ident: (token for frankola: HDFS_DELEGATION_TOKEN owner=frankola@DEYABHISHEK79.FNG, renewer=yarn, realUser=, issueDate=1509744377215, maxDate=1510349177215, sequenceNumber=1, masterKeyId=2)
17/11/03 17:26:18 INFO impl.YarnClientImpl: Submitted application application_1509743434994_0001
17/11/03 17:26:18 INFO mapreduce.Job: The url to track the job: http://ip-172-31-34-47.ec2.internal:8088/proxy/application_1509743434994_0001/
17/11/03 17:26:18 INFO mapreduce.Job: Running job: job_1509743434994_0001
17/11/03 17:26:27 INFO mapreduce.Job: Job job_1509743434994_0001 running in uber mode : false
17/11/03 17:26:27 INFO mapreduce.Job:  map 0% reduce 0%
17/11/03 17:26:36 INFO mapreduce.Job:  map 6% reduce 0%
17/11/03 17:26:44 INFO mapreduce.Job:  map 12% reduce 0%
17/11/03 17:26:45 INFO mapreduce.Job:  map 30% reduce 0%
17/11/03 17:26:46 INFO mapreduce.Job:  map 36% reduce 0%
17/11/03 17:26:50 INFO mapreduce.Job:  map 38% reduce 0%
17/11/03 17:26:52 INFO mapreduce.Job:  map 42% reduce 0%
17/11/03 17:26:54 INFO mapreduce.Job:  map 46% reduce 0%
17/11/03 17:26:55 INFO mapreduce.Job:  map 58% reduce 0%
17/11/03 17:26:56 INFO mapreduce.Job:  map 68% reduce 0%
17/11/03 17:26:59 INFO mapreduce.Job:  map 70% reduce 0%
17/11/03 17:27:00 INFO mapreduce.Job:  map 72% reduce 0%
17/11/03 17:27:02 INFO mapreduce.Job:  map 76% reduce 0%
17/11/03 17:27:04 INFO mapreduce.Job:  map 84% reduce 0%
17/11/03 17:27:05 INFO mapreduce.Job:  map 94% reduce 0%
17/11/03 17:27:06 INFO mapreduce.Job:  map 100% reduce 0%
17/11/03 17:27:09 INFO mapreduce.Job:  map 100% reduce 100%
17/11/03 17:27:10 INFO mapreduce.Job: Job job_1509743434994_0001 completed successfully
17/11/03 17:27:10 INFO mapreduce.Job: Counters: 49
	File System Counters
		FILE: Number of bytes read=253
		FILE: Number of bytes written=6307986
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=14340
		HDFS: Number of bytes written=215
		HDFS: Number of read operations=203
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=3
	Job Counters 
		Launched map tasks=50
		Launched reduce tasks=1
		Data-local map tasks=50
		Total time spent by all maps in occupied slots (ms)=467615
		Total time spent by all reduces in occupied slots (ms)=3535
		Total time spent by all map tasks (ms)=467615
		Total time spent by all reduce tasks (ms)=3535
		Total vcore-seconds taken by all map tasks=467615
		Total vcore-seconds taken by all reduce tasks=3535
		Total megabyte-seconds taken by all map tasks=478837760
		Total megabyte-seconds taken by all reduce tasks=3619840
	Map-Reduce Framework
		Map input records=50
		Map output records=100
		Map output bytes=900
		Map output materialized bytes=1700
		Input split bytes=8440
		Combine input records=0
		Combine output records=0
		Reduce input groups=2
		Reduce shuffle bytes=1700
		Reduce input records=100
		Reduce output records=0
		Spilled Records=200
		Shuffled Maps =50
		Failed Shuffles=0
		Merged Map outputs=50
		GC time elapsed (ms)=2398
		CPU time spent (ms)=34400
		Physical memory (bytes) snapshot=22763384832
		Virtual memory (bytes) snapshot=80487800832
		Total committed heap usage (bytes)=26002063360
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=5900
	File Output Format Counters 
		Bytes Written=97
Job Finished in 53.39 seconds
Estimated value of Pi is 3.14160000000000000000

```

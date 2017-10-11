# HDFS Lab: Test HDFS throughput

## Create an end-user Linux account named with your GitHub handle
### Make sure this Linux account is added to all cluster nodes
### Create an HDFS directory under /user

```
[root@ip-172-31-41-199 ~]# adduser deyabhishek79
[root@ip-172-31-41-199 ~]# passwd deyabhishek79
Changing password for user deyabhishek79.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-41-199 ~]# ssh ip-172-31-33-224.ec2.internal
The authenticity of host 'ip-172-31-33-224.ec2.internal (172.31.33.224)' can't be established.
ECDSA key fingerprint is 05:72:02:06:59:1b:3a:70:8b:16:84:cd:b3:c2:cc:fd.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'ip-172-31-33-224.ec2.internal,172.31.33.224' (ECDSA) to the list of known hosts.
Last login: Wed Oct 11 01:01:58 2017
[root@ip-172-31-33-224 ~]# adduser deyabhishek79
[root@ip-172-31-33-224 ~]# passwd deyabhishek79
Changing password for user deyabhishek79.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-33-224 ~]# echo "deyabhishek79 ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
[root@ip-172-31-33-224 ~]# exit
logout
Connection to ip-172-31-33-224.ec2.internal closed.
[root@ip-172-31-41-199 ~]# echo "deyabhishek79 ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
[root@ip-172-31-41-199 ~]# ssh ip-172-31-41-252.ec2.internal
The authenticity of host 'ip-172-31-41-252.ec2.internal (172.31.41.252)' can't be established.
ECDSA key fingerprint is c7:e6:62:4b:a1:09:4f:1c:47:48:df:3b:78:17:06:03.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'ip-172-31-41-252.ec2.internal,172.31.41.252' (ECDSA) to the list of known hosts.
Last login: Wed Oct 11 01:01:58 2017
[root@ip-172-31-41-252 ~]# adduser deyabhishek79
[root@ip-172-31-41-252 ~]# passwd deyabhishek79
Changing password for user deyabhishek79.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-41-252 ~]# echo "deyabhishek79 ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
[root@ip-172-31-41-252 ~]# exit
logout
Connection to ip-172-31-41-252.ec2.internal closed.
[root@ip-172-31-41-199 ~]# ssh ip-172-31-37-254.ec2.internal
The authenticity of host 'ip-172-31-37-254.ec2.internal (172.31.37.254)' can't be established.
ECDSA key fingerprint is 98:17:96:cb:10:e8:7c:57:3a:46:51:77:f3:25:a6:ce.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'ip-172-31-37-254.ec2.internal,172.31.37.254' (ECDSA) to the list of known hosts.
Last login: Wed Oct 11 01:02:02 2017
[root@ip-172-31-37-254 ~]# adduser deyabhishek79
[root@ip-172-31-37-254 ~]# passwd deyabhishek79
Changing password for user deyabhishek79.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-37-254 ~]# echo "deyabhishek79 ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
[root@ip-172-31-37-254 ~]# exit
logout
Connection to ip-172-31-37-254.ec2.internal closed.
[root@ip-172-31-41-199 ~]# ssh ip-172-31-37-78.ec2.internal
The authenticity of host 'ip-172-31-37-78.ec2.internal (172.31.37.78)' can't be established.
ECDSA key fingerprint is 2b:20:d5:95:0f:ef:c8:4c:bb:a5:8a:5f:fa:6c:bb:9c.
Are you sure you want to continue connecting (yes/no)? yes
Warning: Permanently added 'ip-172-31-37-78.ec2.internal,172.31.37.78' (ECDSA) to the list of known hosts.
Last login: Wed Oct 11 01:01:58 2017
[root@ip-172-31-37-78 ~]# adduser deyabhishek79
[root@ip-172-31-37-78 ~]# passwd deyabhishek79
Changing password for user deyabhishek79.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-37-78 ~]# echo "deyabhishek79 ALL=(ALL) NOPASSWD:ALL" >> /etc/sudoers
[root@ip-172-31-37-78 ~]# exit
logout
Connection to ip-172-31-37-78.ec2.internal closed.
[root@ip-172-31-41-199 ~]# sudo su hdfs
[hdfs@ip-172-31-41-199 root]$ hadoop fs -mkdir -p /user/deyabhishek79
[hdfs@ip-172-31-41-199 root]$ hadoop fs -chown deyabhishek79 /user/deyabhishek79
[hdfs@ip-172-31-41-199 root]$ hadoop fs -chmod 777 /user/deyabhishek79
[hdfs@ip-172-31-41-199 root]$ hadoop fs -ls /user
Found 5 items
drwxrwxrwx   - deyabhishek79 supergroup          0 2017-10-11 02:10 /user/deyabhishek79
drwxrwxrwx   - mapred        hadoop              0 2017-10-11 01:16 /user/history
drwxrwxr-t   - hive          hive                0 2017-10-11 01:16 /user/hive
drwxrwxr-x   - hue           hue                 0 2017-10-11 01:17 /user/hue
drwxrwxr-x   - oozie         oozie               0 2017-10-11 01:17 /user/oozie
[hdfs@ip-172-31-41-199 root]$ exit
exit

```
## Create a 10 GB file using teragen

```
[root@ip-172-31-41-199 ~]# su deyabhishek79
[deyabhishek79@ip-172-31-41-199 root]$ cd
[deyabhishek79@ip-172-31-41-199 ~]$ hadoop fs -ls /user
Found 5 items
drwxrwxrwx   - deyabhishek79 supergroup          0 2017-10-11 02:10 /user/deyabhishek79
drwxrwxrwx   - mapred        hadoop              0 2017-10-11 01:16 /user/history
drwxrwxr-t   - hive          hive                0 2017-10-11 01:16 /user/hive
drwxrwxr-x   - hue           hue                 0 2017-10-11 01:17 /user/hue
drwxrwxr-x   - oozie         oozie               0 2017-10-11 01:17 /user/oozie
[deyabhishek79@ip-172-31-41-199 ~]$ sudo -u hdfs time hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar teragen -Ddfs.block.size=33554432  -Dmapreduce.job.maps=4 100000000 /user/deyabhishek79/teragen_sample_data
17/10/11 02:16:04 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-41-199.ec2.internal/172.31.41.199:8032
17/10/11 02:16:04 INFO terasort.TeraSort: Generating 100000000 using 4
17/10/11 02:16:05 INFO mapreduce.JobSubmitter: number of splits:4
17/10/11 02:16:05 INFO Configuration.deprecation: dfs.block.size is deprecated. Instead, use dfs.blocksize
17/10/11 02:16:05 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507698961357_0001
17/10/11 02:16:05 INFO impl.YarnClientImpl: Submitted application application_1507698961357_0001
17/10/11 02:16:05 INFO mapreduce.Job: The url to track the job: http://ip-172-31-41-199.ec2.internal:8088/proxy/application_1507698961357_0001/
17/10/11 02:16:05 INFO mapreduce.Job: Running job: job_1507698961357_0001
17/10/11 02:16:12 INFO mapreduce.Job: Job job_1507698961357_0001 running in uber mode : false
17/10/11 02:16:12 INFO mapreduce.Job:  map 0% reduce 0%
17/10/11 02:16:26 INFO mapreduce.Job:  map 10% reduce 0%
17/10/11 02:16:29 INFO mapreduce.Job:  map 15% reduce 0%
17/10/11 02:16:32 INFO mapreduce.Job:  map 18% reduce 0%
17/10/11 02:16:35 INFO mapreduce.Job:  map 19% reduce 0%
17/10/11 02:16:47 INFO mapreduce.Job:  map 21% reduce 0%
17/10/11 02:16:56 INFO mapreduce.Job:  map 31% reduce 0%
17/10/11 02:16:59 INFO mapreduce.Job:  map 34% reduce 0%
17/10/11 02:17:02 INFO mapreduce.Job:  map 36% reduce 0%
17/10/11 02:17:05 INFO mapreduce.Job:  map 37% reduce 0%
17/10/11 02:17:14 INFO mapreduce.Job:  map 38% reduce 0%
17/10/11 02:17:17 INFO mapreduce.Job:  map 39% reduce 0%
17/10/11 02:17:20 INFO mapreduce.Job:  map 44% reduce 0%
17/10/11 02:17:23 INFO mapreduce.Job:  map 48% reduce 0%
17/10/11 02:17:26 INFO mapreduce.Job:  map 50% reduce 0%
17/10/11 02:17:35 INFO mapreduce.Job:  map 53% reduce 0%
17/10/11 02:17:47 INFO mapreduce.Job:  map 55% reduce 0%
17/10/11 02:17:50 INFO mapreduce.Job:  map 57% reduce 0%
17/10/11 02:17:53 INFO mapreduce.Job:  map 58% reduce 0%
17/10/11 02:17:56 INFO mapreduce.Job:  map 59% reduce 0%
17/10/11 02:17:59 INFO mapreduce.Job:  map 63% reduce 0%
17/10/11 02:18:05 INFO mapreduce.Job:  map 66% reduce 0%
17/10/11 02:18:08 INFO mapreduce.Job:  map 70% reduce 0%
17/10/11 02:18:11 INFO mapreduce.Job:  map 72% reduce 0%
17/10/11 02:18:14 INFO mapreduce.Job:  map 73% reduce 0%
17/10/11 02:18:26 INFO mapreduce.Job:  map 74% reduce 0%
17/10/11 02:18:29 INFO mapreduce.Job:  map 79% reduce 0%
17/10/11 02:18:32 INFO mapreduce.Job:  map 84% reduce 0%
17/10/11 02:18:35 INFO mapreduce.Job:  map 86% reduce 0%
17/10/11 02:18:38 INFO mapreduce.Job:  map 88% reduce 0%
17/10/11 02:18:41 INFO mapreduce.Job:  map 89% reduce 0%
17/10/11 02:18:53 INFO mapreduce.Job:  map 90% reduce 0%
17/10/11 02:18:57 INFO mapreduce.Job:  map 92% reduce 0%
17/10/11 02:18:59 INFO mapreduce.Job:  map 99% reduce 0%
17/10/11 02:19:02 INFO mapreduce.Job:  map 100% reduce 0%
17/10/11 02:19:02 INFO mapreduce.Job: Job job_1507698961357_0001 completed successfully
17/10/11 02:19:03 INFO mapreduce.Job: Counters: 31
	File System Counters
		FILE: Number of bytes read=0
		FILE: Number of bytes written=493228
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=344
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=16
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=8
	Job Counters 
		Launched map tasks=4
		Other local map tasks=4
		Total time spent by all maps in occupied slots (ms)=655760
		Total time spent by all reduces in occupied slots (ms)=0
		Total time spent by all map tasks (ms)=655760
		Total vcore-seconds taken by all map tasks=655760
		Total megabyte-seconds taken by all map tasks=671498240
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Input split bytes=344
		Spilled Records=0
		Failed Shuffles=0
		Merged Map outputs=0
		GC time elapsed (ms)=1275
		CPU time spent (ms)=167300
		Physical memory (bytes) snapshot=806813696
		Virtual memory (bytes) snapshot=6335983616
		Total committed heap usage (bytes)=964689920
	org.apache.hadoop.examples.terasort.TeraGen$Counters
		CHECKSUM=214760662691937609
	File Input Format Counters 
		Bytes Read=0
	File Output Format Counters 
		Bytes Written=10000000000
6.16user 0.27system 3:01.28elapsed 3%CPU (0avgtext+0avgdata 173920maxresident)k
80inputs+2016outputs (0major+58465minor)pagefaults 0swaps
```

## Run the terasort command on this file

```

[deyabhishek79@ip-172-31-41-199 ~]$ time sudo -u hdfs hadoop jar /opt/cloudera/parcels/CDH-5.9.3-1.cdh5.9.3.p0.4/lib/hadoop-mapreduce/hadoop-mapreduce-examples.jar terasort /user/deyabhishek79/teragen_sample_data /user/deyabhishek79/terasort_output
17/10/11 02:22:18 INFO terasort.TeraSort: starting
17/10/11 02:22:19 INFO input.FileInputFormat: Total input paths to process : 4
Spent 257ms computing base-splits.
Spent 6ms computing TeraScheduler splits.
Computing input splits took 263ms
Sampling 10 splits of 300
Making 8 from 100000 sampled records
Computing parititions took 1040ms
Spent 1307ms computing partitions.
17/10/11 02:22:20 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-41-199.ec2.internal/172.31.41.199:8032
17/10/11 02:22:21 INFO mapreduce.JobSubmitter: number of splits:300
17/10/11 02:22:21 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1507698961357_0002
17/10/11 02:22:21 INFO impl.YarnClientImpl: Submitted application application_1507698961357_0002
17/10/11 02:22:21 INFO mapreduce.Job: The url to track the job: http://ip-172-31-41-199.ec2.internal:8088/proxy/application_1507698961357_0002/
17/10/11 02:22:21 INFO mapreduce.Job: Running job: job_1507698961357_0002
17/10/11 02:22:27 INFO mapreduce.Job: Job job_1507698961357_0002 running in uber mode : false
17/10/11 02:22:27 INFO mapreduce.Job:  map 0% reduce 0%
17/10/11 02:22:37 INFO mapreduce.Job:  map 1% reduce 0%
17/10/11 02:22:39 INFO mapreduce.Job:  map 2% reduce 0%
17/10/11 02:22:40 INFO mapreduce.Job:  map 3% reduce 0%
17/10/11 02:22:42 INFO mapreduce.Job:  map 4% reduce 0%
17/10/11 02:22:45 INFO mapreduce.Job:  map 5% reduce 0%
17/10/11 02:22:49 INFO mapreduce.Job:  map 6% reduce 0%
17/10/11 02:22:50 INFO mapreduce.Job:  map 7% reduce 0%
17/10/11 02:22:54 INFO mapreduce.Job:  map 8% reduce 0%
17/10/11 02:22:55 INFO mapreduce.Job:  map 9% reduce 0%
17/10/11 02:22:59 INFO mapreduce.Job:  map 10% reduce 0%
17/10/11 02:23:00 INFO mapreduce.Job:  map 11% reduce 0%
17/10/11 02:23:05 INFO mapreduce.Job:  map 12% reduce 0%
17/10/11 02:23:07 INFO mapreduce.Job:  map 13% reduce 0%
17/10/11 02:23:08 INFO mapreduce.Job:  map 14% reduce 0%
17/10/11 02:23:09 INFO mapreduce.Job:  map 15% reduce 0%
17/10/11 02:23:15 INFO mapreduce.Job:  map 16% reduce 0%
17/10/11 02:23:18 INFO mapreduce.Job:  map 17% reduce 0%
17/10/11 02:23:19 INFO mapreduce.Job:  map 19% reduce 0%
17/10/11 02:23:23 INFO mapreduce.Job:  map 20% reduce 0%
17/10/11 02:23:28 INFO mapreduce.Job:  map 21% reduce 0%
17/10/11 02:23:29 INFO mapreduce.Job:  map 22% reduce 0%
17/10/11 02:23:31 INFO mapreduce.Job:  map 24% reduce 0%
17/10/11 02:23:37 INFO mapreduce.Job:  map 25% reduce 0%
17/10/11 02:23:39 INFO mapreduce.Job:  map 26% reduce 0%
17/10/11 02:23:40 INFO mapreduce.Job:  map 27% reduce 0%
17/10/11 02:23:44 INFO mapreduce.Job:  map 28% reduce 0%
17/10/11 02:23:46 INFO mapreduce.Job:  map 29% reduce 0%
17/10/11 02:23:48 INFO mapreduce.Job:  map 30% reduce 0%
17/10/11 02:23:50 INFO mapreduce.Job:  map 31% reduce 0%
17/10/11 02:23:55 INFO mapreduce.Job:  map 32% reduce 0%
17/10/11 02:23:56 INFO mapreduce.Job:  map 34% reduce 0%
17/10/11 02:24:00 INFO mapreduce.Job:  map 35% reduce 0%
17/10/11 02:24:03 INFO mapreduce.Job:  map 36% reduce 0%
17/10/11 02:24:07 INFO mapreduce.Job:  map 37% reduce 0%
17/10/11 02:24:08 INFO mapreduce.Job:  map 38% reduce 0%
17/10/11 02:24:09 INFO mapreduce.Job:  map 39% reduce 0%
17/10/11 02:24:12 INFO mapreduce.Job:  map 40% reduce 0%
17/10/11 02:24:16 INFO mapreduce.Job:  map 41% reduce 0%
17/10/11 02:24:19 INFO mapreduce.Job:  map 42% reduce 0%
17/10/11 02:24:21 INFO mapreduce.Job:  map 44% reduce 0%
17/10/11 02:24:24 INFO mapreduce.Job:  map 45% reduce 0%
17/10/11 02:24:27 INFO mapreduce.Job:  map 46% reduce 0%
17/10/11 02:24:32 INFO mapreduce.Job:  map 47% reduce 0%
17/10/11 02:24:34 INFO mapreduce.Job:  map 49% reduce 0%
17/10/11 02:24:36 INFO mapreduce.Job:  map 50% reduce 0%
17/10/11 02:24:40 INFO mapreduce.Job:  map 51% reduce 0%
17/10/11 02:24:43 INFO mapreduce.Job:  map 52% reduce 0%
17/10/11 02:24:45 INFO mapreduce.Job:  map 53% reduce 0%
17/10/11 02:24:47 INFO mapreduce.Job:  map 54% reduce 0%
17/10/11 02:24:49 INFO mapreduce.Job:  map 55% reduce 0%
17/10/11 02:24:52 INFO mapreduce.Job:  map 56% reduce 0%
17/10/11 02:24:55 INFO mapreduce.Job:  map 57% reduce 0%
17/10/11 02:24:59 INFO mapreduce.Job:  map 58% reduce 0%
17/10/11 02:25:00 INFO mapreduce.Job:  map 60% reduce 0%
17/10/11 02:25:04 INFO mapreduce.Job:  map 61% reduce 0%
17/10/11 02:25:09 INFO mapreduce.Job:  map 62% reduce 0%
17/10/11 02:25:10 INFO mapreduce.Job:  map 63% reduce 0%
17/10/11 02:25:13 INFO mapreduce.Job:  map 64% reduce 0%
17/10/11 02:25:14 INFO mapreduce.Job:  map 65% reduce 0%
17/10/11 02:25:17 INFO mapreduce.Job:  map 66% reduce 0%
17/10/11 02:25:20 INFO mapreduce.Job:  map 67% reduce 0%
17/10/11 02:25:23 INFO mapreduce.Job:  map 68% reduce 0%
17/10/11 02:25:25 INFO mapreduce.Job:  map 69% reduce 0%
17/10/11 02:25:26 INFO mapreduce.Job:  map 70% reduce 0%
17/10/11 02:25:30 INFO mapreduce.Job:  map 71% reduce 0%
17/10/11 02:25:31 INFO mapreduce.Job:  map 72% reduce 0%
17/10/11 02:25:36 INFO mapreduce.Job:  map 73% reduce 0%
17/10/11 02:25:37 INFO mapreduce.Job:  map 74% reduce 0%
17/10/11 02:25:39 INFO mapreduce.Job:  map 75% reduce 0%
17/10/11 02:25:40 INFO mapreduce.Job:  map 76% reduce 0%
17/10/11 02:25:44 INFO mapreduce.Job:  map 77% reduce 0%
17/10/11 02:25:48 INFO mapreduce.Job:  map 78% reduce 0%
17/10/11 02:25:50 INFO mapreduce.Job:  map 80% reduce 0%
17/10/11 02:25:51 INFO mapreduce.Job:  map 81% reduce 0%
17/10/11 02:25:58 INFO mapreduce.Job:  map 82% reduce 0%
17/10/11 02:26:00 INFO mapreduce.Job:  map 84% reduce 0%
17/10/11 02:26:01 INFO mapreduce.Job:  map 85% reduce 0%
17/10/11 02:26:09 INFO mapreduce.Job:  map 85% reduce 2%
17/10/11 02:26:10 INFO mapreduce.Job:  map 85% reduce 3%
17/10/11 02:26:12 INFO mapreduce.Job:  map 86% reduce 9%
17/10/11 02:26:13 INFO mapreduce.Job:  map 86% reduce 12%
17/10/11 02:26:14 INFO mapreduce.Job:  map 86% reduce 14%
17/10/11 02:26:15 INFO mapreduce.Job:  map 87% reduce 17%
17/10/11 02:26:16 INFO mapreduce.Job:  map 87% reduce 19%
17/10/11 02:26:17 INFO mapreduce.Job:  map 87% reduce 20%
17/10/11 02:26:18 INFO mapreduce.Job:  map 87% reduce 22%
17/10/11 02:26:19 INFO mapreduce.Job:  map 87% reduce 23%
17/10/11 02:26:21 INFO mapreduce.Job:  map 87% reduce 24%
17/10/11 02:26:23 INFO mapreduce.Job:  map 87% reduce 25%
17/10/11 02:26:24 INFO mapreduce.Job:  map 88% reduce 25%
17/10/11 02:26:27 INFO mapreduce.Job:  map 89% reduce 26%
17/10/11 02:26:36 INFO mapreduce.Job:  map 90% reduce 26%
17/10/11 02:26:39 INFO mapreduce.Job:  map 91% reduce 26%
17/10/11 02:26:45 INFO mapreduce.Job:  map 91% reduce 27%
17/10/11 02:26:48 INFO mapreduce.Job:  map 92% reduce 27%
17/10/11 02:26:51 INFO mapreduce.Job:  map 93% reduce 27%
17/10/11 02:27:00 INFO mapreduce.Job:  map 94% reduce 27%
17/10/11 02:27:03 INFO mapreduce.Job:  map 95% reduce 27%
17/10/11 02:27:05 INFO mapreduce.Job:  map 95% reduce 28%
17/10/11 02:27:12 INFO mapreduce.Job:  map 96% reduce 28%
17/10/11 02:27:16 INFO mapreduce.Job:  map 97% reduce 28%
17/10/11 02:27:24 INFO mapreduce.Job:  map 98% reduce 28%
17/10/11 02:27:27 INFO mapreduce.Job:  map 99% reduce 29%
17/10/11 02:27:38 INFO mapreduce.Job:  map 100% reduce 29%
17/10/11 02:27:39 INFO mapreduce.Job:  map 100% reduce 31%
17/10/11 02:27:40 INFO mapreduce.Job:  map 100% reduce 39%
17/10/11 02:27:41 INFO mapreduce.Job:  map 100% reduce 43%
17/10/11 02:27:42 INFO mapreduce.Job:  map 100% reduce 56%
17/10/11 02:27:43 INFO mapreduce.Job:  map 100% reduce 59%
17/10/11 02:27:44 INFO mapreduce.Job:  map 100% reduce 61%
17/10/11 02:27:45 INFO mapreduce.Job:  map 100% reduce 64%
17/10/11 02:27:46 INFO mapreduce.Job:  map 100% reduce 66%
17/10/11 02:27:47 INFO mapreduce.Job:  map 100% reduce 67%
17/10/11 02:27:48 INFO mapreduce.Job:  map 100% reduce 70%
17/10/11 02:27:49 INFO mapreduce.Job:  map 100% reduce 74%
17/10/11 02:27:50 INFO mapreduce.Job:  map 100% reduce 76%
17/10/11 02:27:51 INFO mapreduce.Job:  map 100% reduce 78%
17/10/11 02:27:52 INFO mapreduce.Job:  map 100% reduce 80%
17/10/11 02:27:54 INFO mapreduce.Job:  map 100% reduce 82%
17/10/11 02:27:55 INFO mapreduce.Job:  map 100% reduce 84%
17/10/11 02:27:56 INFO mapreduce.Job:  map 100% reduce 85%
17/10/11 02:27:57 INFO mapreduce.Job:  map 100% reduce 87%
17/10/11 02:27:58 INFO mapreduce.Job:  map 100% reduce 88%
17/10/11 02:27:59 INFO mapreduce.Job:  map 100% reduce 89%
17/10/11 02:28:00 INFO mapreduce.Job:  map 100% reduce 91%
17/10/11 02:28:01 INFO mapreduce.Job:  map 100% reduce 92%
17/10/11 02:28:02 INFO mapreduce.Job:  map 100% reduce 94%
17/10/11 02:28:03 INFO mapreduce.Job:  map 100% reduce 97%
17/10/11 02:28:06 INFO mapreduce.Job:  map 100% reduce 98%
17/10/11 02:28:09 INFO mapreduce.Job:  map 100% reduce 99%
17/10/11 02:28:12 INFO mapreduce.Job:  map 100% reduce 100%
17/10/11 02:28:12 INFO mapreduce.Job: Job job_1507698961357_0002 completed successfully
17/10/11 02:28:13 INFO mapreduce.Job: Counters: 50
	File System Counters
		FILE: Number of bytes read=4442528174
		FILE: Number of bytes written=8823816845
		FILE: Number of read operations=0
		FILE: Number of large read operations=0
		FILE: Number of write operations=0
		HDFS: Number of bytes read=10000047400
		HDFS: Number of bytes written=10000000000
		HDFS: Number of read operations=924
		HDFS: Number of large read operations=0
		HDFS: Number of write operations=16
	Job Counters 
		Launched map tasks=300
		Launched reduce tasks=8
		Data-local map tasks=298
		Rack-local map tasks=2
		Total time spent by all maps in occupied slots (ms)=2662091
		Total time spent by all reduces in occupied slots (ms)=918266
		Total time spent by all map tasks (ms)=2662091
		Total time spent by all reduce tasks (ms)=918266
		Total vcore-seconds taken by all map tasks=2662091
		Total vcore-seconds taken by all reduce tasks=918266
		Total megabyte-seconds taken by all map tasks=2725981184
		Total megabyte-seconds taken by all reduce tasks=940304384
	Map-Reduce Framework
		Map input records=100000000
		Map output records=100000000
		Map output bytes=10200000000
		Map output materialized bytes=4342841401
		Input split bytes=47400
		Combine input records=0
		Combine output records=0
		Reduce input groups=100000000
		Reduce shuffle bytes=4342841401
		Reduce input records=100000000
		Reduce output records=100000000
		Spilled Records=200000000
		Shuffled Maps =2400
		Failed Shuffles=0
		Merged Map outputs=2400
		GC time elapsed (ms)=30518
		CPU time spent (ms)=1445400
		Physical memory (bytes) snapshot=146142633984
		Virtual memory (bytes) snapshot=488109699072
		Total committed heap usage (bytes)=172730875904
	Shuffle Errors
		BAD_ID=0
		CONNECTION=0
		IO_ERROR=0
		WRONG_LENGTH=0
		WRONG_MAP=0
		WRONG_REDUCE=0
	File Input Format Counters 
		Bytes Read=10000000000
	File Output Format Counters 
		Bytes Written=10000000000
17/10/11 02:28:13 INFO terasort.TeraSort: done

real	5m55.947s
user	0m9.862s
sys	0m0.401s
[deyabhishek79@ip-172-31-41-199 ~]$ 

```

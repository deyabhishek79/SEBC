# Yarn Test Results

```
[deyabhishek79@ip-172-31-41-199 ~]$ sh -x YarnTest.sh 
+ HADOOP_MR=/opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce
+ HADOOP_PATH=/opt/cloudera/parcels/CDH/bin
++ date
+ echo Testing loop started on Wed Oct 11 15:32:01 EDT 2017
Testing loop started on Wed Oct 11 15:32:01 EDT 2017
+ for i in 8
+ for j in 1
+ for k in 512 1024
++ echo '(512*0.8)/1'
++ bc
+ MAP_MB=409
++ echo '(512*0.8)/1'
++ bc
+ RED_MB=409
+ hadoop fs -mkdir /user/deyabhishek79/results/tg-10GB-8-1-512
mkdir: `/user/deyabhishek79/results/tg-10GB-8-1-512': File exists
+ hadoop fs -mkdir /user/deyabhishek79/results/ts-10GB-8-1-512
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=8 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 10737418240 /user/deyabhishek79/results/tg-10GB-8-1-512

real	0m2.545s
user	0m3.446s
sys	0m0.187s
+ echo Dmapreduce.job.maps=8
Dmapreduce.job.maps=8
+ echo Dmapreduce.map.memory.mb=512
Dmapreduce.map.memory.mb=512
+ echo Dmapreduce.map.java.opts.max.heap=409
Dmapreduce.map.java.opts.max.heap=409
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=8 -Dmapreduce.job.reduces=1 -Dmapreduce.map.memory.mb=512 -Dmapreduce.map.java.opts.max.heap=409 -Dmapreduce.reduce.memory.mb=512 -Dmapreduce.reduce.java.opts.max.heap=409 /user/deyabhishek79/results/tg-10GB-8-1-512 /user//results/ts-10GB-8-1-512

real	0m2.489s
user	0m3.856s
sys	0m0.203s
+ echo Dmapreduce.job.maps=8
Dmapreduce.job.maps=8
+ echo Dmapreduce.job.reduces=1
Dmapreduce.job.reduces=1
+ echo Dmapreduce.map.memory.mb=512
Dmapreduce.map.memory.mb=512
+ echo Dmapreduce.map.java.opts.max.heap=409
Dmapreduce.map.java.opts.max.heap=409
+ echo Dmapreduce.reduce.memory.mb=512
Dmapreduce.reduce.memory.mb=512
+ echo Dmapreduce.reduce.java.opts.max.heap=409
Dmapreduce.reduce.java.opts.max.heap=409
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /user/deyabhishek79/results/tg-10GB-8-1-512
Deleted /user/deyabhishek79/results/tg-10GB-8-1-512
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /user/deyabhishek79/results/ts-10GB-8-1-512
Deleted /user/deyabhishek79/results/ts-10GB-8-1-512
+ for k in 512 1024
++ echo '(1024*0.8)/1'
++ bc
+ MAP_MB=819
++ echo '(1024*0.8)/1'
++ bc
+ RED_MB=819
+ hadoop fs -mkdir /user/deyabhishek79/results/tg-10GB-8-1-1024
+ hadoop fs -mkdir /user/deyabhishek79/results/ts-10GB-8-1-1024
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar teragen -Dmapreduce.job.maps=8 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 10737418240 /user/deyabhishek79/results/tg-10GB-8-1-1024

real	0m2.559s
user	0m3.583s
sys	0m0.209s
+ echo Dmapreduce.job.maps=8
Dmapreduce.job.maps=8
+ echo Dmapreduce.map.memory.mb=1024
Dmapreduce.map.memory.mb=1024
+ echo Dmapreduce.map.java.opts.max.heap=819
Dmapreduce.map.java.opts.max.heap=819
+ /opt/cloudera/parcels/CDH/bin/hadoop jar /opt/cloudera/parcels/CDH/lib/hadoop-0.20-mapreduce/hadoop-examples.jar terasort -Dmapreduce.job.maps=8 -Dmapreduce.job.reduces=1 -Dmapreduce.map.memory.mb=1024 -Dmapreduce.map.java.opts.max.heap=819 -Dmapreduce.reduce.memory.mb=1024 -Dmapreduce.reduce.java.opts.max.heap=819 /user/deyabhishek79/results/tg-10GB-8-1-1024 /user//results/ts-10GB-8-1-1024

real	0m2.491s
user	0m3.392s
sys	0m0.198s
+ echo Dmapreduce.job.maps=8
Dmapreduce.job.maps=8
+ echo Dmapreduce.job.reduces=1
Dmapreduce.job.reduces=1
+ echo Dmapreduce.map.memory.mb=1024
Dmapreduce.map.memory.mb=1024
+ echo Dmapreduce.map.java.opts.max.heap=819
Dmapreduce.map.java.opts.max.heap=819
+ echo Dmapreduce.reduce.memory.mb=1024
Dmapreduce.reduce.memory.mb=1024
+ echo Dmapreduce.reduce.java.opts.max.heap=819
Dmapreduce.reduce.java.opts.max.heap=819
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /user/deyabhishek79/results/tg-10GB-8-1-1024
Deleted /user/deyabhishek79/results/tg-10GB-8-1-1024
+ /opt/cloudera/parcels/CDH/bin/hadoop fs -rm -r -skipTrash /user/deyabhishek79/results/ts-10GB-8-1-1024
Deleted /user/deyabhishek79/results/ts-10GB-8-1-1024
++ date
+ echo Testing loop ended on Wed Oct 11 15:32:34 EDT 2017
Testing loop ended on Wed Oct 11 15:32:34 EDT 2017
```

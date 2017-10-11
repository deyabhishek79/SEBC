# HDFS Lab: Test HDFS Snapshots

```
[deyabhishek79@ip-172-31-41-199 ~]$ ls -lrt /tmp/precious_files.tar.gz
-rwxrwxrwx. 1 ec2-user ec2-user 351831027 Oct 11 02:47 /tmp/precious_files.tar.gz
[deyabhishek79@ip-172-31-41-199 ~]$ hadoop fs -copyFromLocal /tmp/precious_files.tar.gz /user/deyabhishek79/precious/
[deyabhishek79@ip-172-31-41-199 ~]$ hadoop fs -ls /user/deyabhishek79/precious
Found 1 items
-rw-r--r--   3 deyabhishek79 supergroup  351831027 2017-10-11 02:50 /user/deyabhishek79/precious/precious_files.tar.gz
[deyabhishek79@ip-172-31-41-199 ~]$ hadoop fs -rm -skipTrash /user/deyabhishek79/precious/precious_files.tar.gz
Deleted /user/deyabhishek79/precious/precious_files.tar.gz
[deyabhishek79@ip-172-31-41-199 ~]$ 

```

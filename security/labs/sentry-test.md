# Verify user privileges
```
[deyabhishek79@ip-172-31-41-199 ~]$ beeline
Beeline version 1.1.0-cdh5.13.0 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-199.ec2.internal@DEYABHISHEK79.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-199.ec2.internal@DEYABHISHEK79.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.0)
Driver: Hive JDBC (version 1.1.0-cdh5.13.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171012004343_77a2308e-4666-4cad-b9ef-d99c6765b309): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171012004343_77a2308e-4666-4cad-b9ef-d99c6765b309); Time taken: 0.749 seconds
INFO  : Executing command(queryId=hive_20171012004343_77a2308e-4666-4cad-b9ef-d99c6765b309): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012004343_77a2308e-4666-4cad-b9ef-d99c6765b309); Time taken: 0.492 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (2.625 seconds)

```
# Create a Sentry role with full authorization

```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171012004545_8f3c3b2f-7b38-490e-b358-8de5b48785b1): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012004545_8f3c3b2f-7b38-490e-b358-8de5b48785b1); Time taken: 0.077 seconds
INFO  : Executing command(queryId=hive_20171012004545_8f3c3b2f-7b38-490e-b358-8de5b48785b1): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012004545_8f3c3b2f-7b38-490e-b358-8de5b48785b1); Time taken: 0.154 seconds
INFO  : OK
No rows affected (0.246 seconds)

[root@ip-172-31-41-199 ~]# groupadd mysentryprimarygroup
[root@ip-172-31-41-199 ~]# ssh ip-172-31-33-224.ec2.internal
Last login: Wed Oct 11 21:08:46 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-33-224 ~]# groupadd mysentryprimarygroup
[root@ip-172-31-33-224 ~]# exit
logout
Connection to ip-172-31-33-224.ec2.internal closed.
[root@ip-172-31-41-199 ~]# ssh ip-172-31-41-252.ec2.internal
Last login: Wed Oct 11 23:12:37 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-41-252 ~]# groupadd mysentryprimarygroup
[root@ip-172-31-41-252 ~]# exit
logout
Connection to ip-172-31-41-252.ec2.internal closed.
[root@ip-172-31-41-199 ~]# ssh ip-172-31-37-254.ec2.internal
Last login: Wed Oct 11 21:10:40 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-37-254 ~]# groupadd mysentryprimarygroup
[root@ip-172-31-37-254 ~]# exit
logout
Connection to ip-172-31-37-254.ec2.internal closed.
[root@ip-172-31-41-199 ~]# ssh ip-172-31-37-78.ec2.internal
Last login: Wed Oct 11 21:11:00 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-37-78 ~]# groupadd mysentryprimarygroup
[root@ip-172-31-37-78 ~]# exit
logout
Connection to ip-172-31-37-78.ec2.internal closed.
[root@ip-172-31-41-199 ~]# usermod -G mysentryprimarygroup deyabhishek79
[root@ip-172-31-41-199 ~]# ssh ip-172-31-33-224.ec2.internal
Last login: Thu Oct 12 10:29:47 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-33-224 ~]# usermod -G mysentryprimarygroup deyabhishek79
[root@ip-172-31-33-224 ~]# exit
logout
Connection to ip-172-31-33-224.ec2.internal closed.
[root@ip-172-31-41-199 ~]# ssh ip-172-31-37-254.ec2.internal
Last login: Thu Oct 12 10:31:00 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-37-254 ~]# usermod -G mysentryprimarygroup deyabhishek79
[root@ip-172-31-37-254 ~]# exit
logout
Connection to ip-172-31-37-254.ec2.internal closed.
[root@ip-172-31-41-199 ~]# ssh ip-172-31-37-78.ec2.internal
Last login: Thu Oct 12 10:31:14 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-37-78 ~]# usermod -G mysentryprimarygroup deyabhishek79
[root@ip-172-31-37-78 ~]# exit
logout
Connection to ip-172-31-37-78.ec2.internal closed.
[root@ip-172-31-41-199 ~]# ssh ip-172-31-33-224.ec2.internal
Last login: Thu Oct 12 10:32:38 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-33-224 ~]# usermod -G mysentryprimarygroup deyabhishek79
[root@ip-172-31-33-224 ~]# exit
logout
Connection to ip-172-31-33-224.ec2.internal closed.
[root@ip-172-31-41-199 ~]# su deyabhishek79
[deyabhishek79@ip-172-31-41-199 root]$ cd
[deyabhishek79@ip-172-31-41-199 ~]$ kinit
Password for deyabhishek79@DEYABHISHEK79.COM: 
[deyabhishek79@ip-172-31-41-199 ~]$ beeline
Beeline version 1.1.0-cdh5.13.0 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-199.ec2.internal@DEYABHISHEK79.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-199.ec2.internal@DEYABHISHEK79.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.0)
Driver: Hive JDBC (version 1.1.0-cdh5.13.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171012103434_f36bbab5-c745-419f-9f02-4493a2946aa5): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012103434_f36bbab5-c745-419f-9f02-4493a2946aa5); Time taken: 0.082 seconds
INFO  : Executing command(queryId=hive_20171012103434_f36bbab5-c745-419f-9f02-4493a2946aa5): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012103434_f36bbab5-c745-419f-9f02-4493a2946aa5); Time taken: 0.029 seconds
INFO  : OK
No rows affected (0.177 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE sentry_admin TO GROUP mysentryprimarygroup;
INFO  : Compiling command(queryId=hive_20171012103535_06f840c8-7c80-47f9-ab16-f9fa19fcbf7f): GRANT ROLE sentry_admin TO GROUP mysentryprimarygroup
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012103535_06f840c8-7c80-47f9-ab16-f9fa19fcbf7f); Time taken: 0.065 seconds
INFO  : Executing command(queryId=hive_20171012103535_06f840c8-7c80-47f9-ab16-f9fa19fcbf7f): GRANT ROLE sentry_admin TO GROUP mysentryprimarygroup
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012103535_06f840c8-7c80-47f9-ab16-f9fa19fcbf7f); Time taken: 0.027 seconds
INFO  : OK
No rows affected (0.104 seconds)
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171012103535_0a7cdc8e-edcb-4541-a4f2-546250837f85): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171012103535_0a7cdc8e-edcb-4541-a4f2-546250837f85); Time taken: 0.07 seconds
INFO  : Executing command(queryId=hive_20171012103535_0a7cdc8e-edcb-4541-a4f2-546250837f85): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012103535_0a7cdc8e-edcb-4541-a4f2-546250837f85); Time taken: 0.18 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
| employee  |
+-----------+--+
1 row selected (0.319 seconds)

0: jdbc:hive2://localhost:10000/default> CREATE TABLE invites (foo INT, bar STRING) PARTITIONED BY (ds STRING);
INFO  : Compiling command(queryId=hive_20171012104949_8b812c49-6ba8-4e8f-b901-45bc71befa29): CREATE TABLE invites (foo INT, bar STRING) PARTITIONED BY (ds STRING)
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012104949_8b812c49-6ba8-4e8f-b901-45bc71befa29); Time taken: 0.111 seconds
INFO  : Executing command(queryId=hive_20171012104949_8b812c49-6ba8-4e8f-b901-45bc71befa29): CREATE TABLE invites (foo INT, bar STRING) PARTITIONED BY (ds STRING)
INFO  : Starting task [Stage-0:DDL] in serial mode
...
```

# Create additional test users

```
[root@ip-172-31-41-199 ~]# sudo groupadd selector
[root@ip-172-31-41-199 ~]# sudo groupadd inserters
[root@ip-172-31-41-199 ~]# sudo useradd -u 1100 -g selector george
[root@ip-172-31-41-199 ~]# sudo useradd -u 1200 -g inserters ferdinand
[root@ip-172-31-41-199 conf.cloudera.sentry]# ssh ip-172-31-33-224.ec2.internal
Last login: Thu Oct 12 10:33:25 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-33-224 ~]# sudo groupadd selector
[root@ip-172-31-33-224 ~]# sudo groupadd inserters
[root@ip-172-31-33-224 ~]# sudo useradd -u 1100 -g selector george
[root@ip-172-31-33-224 ~]# sudo useradd -u 1200 -g inserters ferdinand
[root@ip-172-31-33-224 ~]# exit
logout
Connection to ip-172-31-33-224.ec2.internal closed.
[root@ip-172-31-41-199 conf.cloudera.sentry]# ssh ip-172-31-41-252.ec2.internal
Last login: Thu Oct 12 10:30:39 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-41-252 ~]# sudo groupadd selector
[root@ip-172-31-41-252 ~]# sudo groupadd inserters
[root@ip-172-31-41-252 ~]# sudo useradd -u 1100 -g selector george
[root@ip-172-31-41-252 ~]# sudo useradd -u 1200 -g inserters ferdinand
[root@ip-172-31-41-252 ~]# exit
logout
Connection to ip-172-31-41-252.ec2.internal closed.
[root@ip-172-31-41-199 conf.cloudera.sentry]# ssh ip-172-31-37-254.ec2.internal
Last login: Thu Oct 12 10:32:50 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-37-254 ~]# sudo groupadd selector
[root@ip-172-31-37-254 ~]# sudo groupadd inserters
[root@ip-172-31-37-254 ~]# sudo useradd -u 1100 -g selector george
[root@ip-172-31-37-254 ~]# sudo useradd -u 1200 -g inserters ferdinand
[root@ip-172-31-37-254 ~]# exit
logout
Connection to ip-172-31-37-254.ec2.internal closed.
[root@ip-172-31-41-199 conf.cloudera.sentry]# ssh ip-172-31-37-78.ec2.internal
Last login: Thu Oct 12 10:33:10 2017 from ip-172-31-41-199.ec2.internal
[root@ip-172-31-37-78 ~]# sudo groupadd selector
[root@ip-172-31-37-78 ~]# sudo groupadd inserters
[root@ip-172-31-37-78 ~]# sudo useradd -u 1100 -g selector george
[root@ip-172-31-37-78 ~]# sudo useradd -u 1200 -g inserters ferdinand
[root@ip-172-31-37-78 ~]# exit
logout
[root@ip-172-31-41-199 ~]# kadmin.local
Authenticating as principal hdfs/admin@DEYABHISHEK79.COM with password.
kadmin.local:  addprinc george
WARNING: no policy specified for george@DEYABHISHEK79.COM; defaulting to no policy
Enter password for principal "george@DEYABHISHEK79.COM": 
Re-enter password for principal "george@DEYABHISHEK79.COM": 
Principal "george@DEYABHISHEK79.COM" created.
kadmin.local:  addprinc ferdinand
WARNING: no policy specified for ferdinand@DEYABHISHEK79.COM; defaulting to no policy
Enter password for principal "ferdinand@DEYABHISHEK79.COM": 
Re-enter password for principal "ferdinand@DEYABHISHEK79.COM": 
Principal "ferdinand@DEYABHISHEK79.COM" created.
kadmin.local:  exit

```
# Create test roles

```
0: jdbc:hive2://localhost:10000/default> CREATE ROLE reads;
INFO  : Compiling command(queryId=hive_20171012021717_e20491bd-4d5c-4f95-b8d2-b358814eed6a): CREATE ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012021717_e20491bd-4d5c-4f95-b8d2-b358814eed6a); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20171012021717_e20491bd-4d5c-4f95-b8d2-b358814eed6a): CREATE ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012021717_e20491bd-4d5c-4f95-b8d2-b358814eed6a); Time taken: 0.023 seconds
INFO  : OK
No rows affected (0.109 seconds)
0: jdbc:hive2://localhost:10000/default> CREATE ROLE writes;
INFO  : Compiling command(queryId=hive_20171012021717_a27dcca4-08af-40ae-8f01-04655ad93ee1): CREATE ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012021717_a27dcca4-08af-40ae-8f01-04655ad93ee1); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20171012021717_a27dcca4-08af-40ae-8f01-04655ad93ee1): CREATE ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012021717_a27dcca4-08af-40ae-8f01-04655ad93ee1); Time taken: 0.012 seconds
INFO  : OK
No rows affected (0.088 seconds)

```

# Grant read privilege for all tables to reads

```
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON DATABASE default TO ROLE reads;
INFO  : Compiling command(queryId=hive_20171012105252_63296c40-94fc-4a6c-86a3-9887305cebc5): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012105252_63296c40-94fc-4a6c-86a3-9887305cebc5); Time taken: 0.074 seconds
INFO  : Executing command(queryId=hive_20171012105252_63296c40-94fc-4a6c-86a3-9887305cebc5): GRANT SELECT ON DATABASE default TO ROLE reads
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012105252_63296c40-94fc-4a6c-86a3-9887305cebc5); Time taken: 0.021 seconds
INFO  : OK
No rows affected (0.15 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE reads TO GROUP selector;
INFO  : Compiling command(queryId=hive_20171012105252_f2c6dd7e-530b-489e-883e-2ad435a917eb): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012105252_f2c6dd7e-530b-489e-883e-2ad435a917eb); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20171012105252_f2c6dd7e-530b-489e-883e-2ad435a917eb): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012105252_f2c6dd7e-530b-489e-883e-2ad435a917eb); Time taken: 0.013 seconds
INFO  : OK
No rows affected (0.091 seconds)

```

# Grant read privilege for default.employee only to 'writes':

```
INFO  : Compiling command(queryId=hive_20171012105252_f2c6dd7e-530b-489e-883e-2ad435a917eb): GRANT ROLE reads TO GROUP selector
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012105252_f2c6dd7e-530b-489e-883e-2ad435a917eb); Time taken: 0.064 seconds
INFO  : Executing command(queryId=hive_20171012105252_f2c6dd7e-530b-489e-883e-2ad435a917eb): GRANT ROLE reads TO GROUP selector
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012105252_f2c6dd7e-530b-489e-883e-2ad435a917eb); Time taken: 0.013 seconds
INFO  : OK
No rows affected (0.091 seconds)
0: jdbc:hive2://localhost:10000/default> REVOKE ALL ON DATABASE default FROM ROLE writes;
INFO  : Compiling command(queryId=hive_20171012105656_7a9c702f-7023-44e6-ba0b-e8455a84599d): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012105656_7a9c702f-7023-44e6-ba0b-e8455a84599d); Time taken: 0.085 seconds
INFO  : Executing command(queryId=hive_20171012105656_7a9c702f-7023-44e6-ba0b-e8455a84599d): REVOKE ALL ON DATABASE default FROM ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012105656_7a9c702f-7023-44e6-ba0b-e8455a84599d); Time taken: 0.048 seconds
INFO  : OK
No rows affected (0.144 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT SELECT ON default.employee TO ROLE writes;
INFO  : Compiling command(queryId=hive_20171012105757_afcaa98e-984f-445f-9bb3-0558f9b3000e): GRANT SELECT ON default.employee TO ROLE writes
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012105757_afcaa98e-984f-445f-9bb3-0558f9b3000e); Time taken: 0.063 seconds
INFO  : Executing command(queryId=hive_20171012105757_afcaa98e-984f-445f-9bb3-0558f9b3000e): GRANT SELECT ON default.employee TO ROLE writes
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012105757_afcaa98e-984f-445f-9bb3-0558f9b3000e); Time taken: 0.012 seconds
INFO  : OK
No rows affected (0.09 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE writes TO GROUP inserters;
INFO  : Compiling command(queryId=hive_20171012105757_1f12c7dc-dae0-46b1-90e8-eec463683b47): GRANT ROLE writes TO GROUP inserters
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171012105757_1f12c7dc-dae0-46b1-90e8-eec463683b47); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20171012105757_1f12c7dc-dae0-46b1-90e8-eec463683b47): GRANT ROLE writes TO GROUP inserters
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012105757_1f12c7dc-dae0-46b1-90e8-eec463683b47); Time taken: 0.012 seconds
INFO  : OK
No rows affected (0.088 seconds)

```

# kinit as george, then login to beeline, and repeat for ferdinand, to demonstrate roles' access

```
root@ip-172-31-41-199 ~]# su george
[george@ip-172-31-41-199 root]$ kinit george
Password for george@DEYABHISHEK79.COM: 
[george@ip-172-31-41-199 root]$ cd
[george@ip-172-31-41-199 ~]$ beeline
Beeline version 1.1.0-cdh5.13.0 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-199.ec2.internal@DEYABHISHEK79.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-199.ec2.internal@DEYABHISHEK79.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.0)
Driver: Hive JDBC (version 1.1.0-cdh5.13.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171012110000_949b3795-cf87-4c86-809b-9b44af7e73ce): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171012110000_949b3795-cf87-4c86-809b-9b44af7e73ce); Time taken: 0.076 seconds
INFO  : Executing command(queryId=hive_20171012110000_949b3795-cf87-4c86-809b-9b44af7e73ce): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012110000_949b3795-cf87-4c86-809b-9b44af7e73ce); Time taken: 0.136 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
| employee  |
| invites   |
+-----------+--+
2 rows selected (0.313 seconds)

[root@ip-172-31-41-199 ~]# su ferdinand
[ferdinand@ip-172-31-41-199 root]$ cd
[ferdinand@ip-172-31-41-199 ~]$ kinit ferdinand
Password for ferdinand@DEYABHISHEK79.COM: 
[ferdinand@ip-172-31-41-199 ~]$ beeline
Beeline version 1.1.0-cdh5.13.0 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-199.ec2.internal@DEYABHISHEK79.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-41-199.ec2.internal@DEYABHISHEK79.COM
Connected to: Apache Hive (version 1.1.0-cdh5.13.0)
Driver: Hive JDBC (version 1.1.0-cdh5.13.0)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171012110101_cb67be9e-f8f1-44af-8753-b3c0da147ec9): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171012110101_cb67be9e-f8f1-44af-8753-b3c0da147ec9); Time taken: 0.075 seconds
INFO  : Executing command(queryId=hive_20171012110101_cb67be9e-f8f1-44af-8753-b3c0da147ec9): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171012110101_cb67be9e-f8f1-44af-8753-b3c0da147ec9); Time taken: 0.134 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
| employee  |
+-----------+--+
1 row selected (0.306 seconds)

```

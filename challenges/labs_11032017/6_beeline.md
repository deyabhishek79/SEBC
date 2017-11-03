# Sentry

```

[reilly@ip-172-31-34-47 ~]$ beeline
Beeline version 1.1.0-cdh5.8.5 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-34-47.ec2.internal@DEYABHISHEK79.FNG
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-34-47.ec2.internal@DEYABHISHEK79.FNG
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-34-47.ec2.internal@DEYABHISHEK79.FNG: reilly
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-34-47.ec2.internal@DEYABHISHEK79.FNG: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.5)
Driver: Hive JDBC (version 1.1.0-cdh5.8.5)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> CREATE ROLE Logger;
INFO  : Compiling command(queryId=hive_20171103175151_17aa9494-4756-45bd-b1a7-c3879ee7ecf4): CREATE ROLE Logger
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175151_17aa9494-4756-45bd-b1a7-c3879ee7ecf4); Time taken: 0.576 seconds
INFO  : Executing command(queryId=hive_20171103175151_17aa9494-4756-45bd-b1a7-c3879ee7ecf4): CREATE ROLE Logger
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171103175151_17aa9494-4756-45bd-b1a7-c3879ee7ecf4); Time taken: 0.712 seconds
INFO  : OK
No rows affected (2.54 seconds)
0: jdbc:hive2://localhost:10000/default> CREATE ROLE Customer;
INFO  : Compiling command(queryId=hive_20171103175151_18b55176-607a-4c17-9c4e-a5cd11c8f6a5): CREATE ROLE Customer
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175151_18b55176-607a-4c17-9c4e-a5cd11c8f6a5); Time taken: 0.088 seconds
INFO  : Executing command(queryId=hive_20171103175151_18b55176-607a-4c17-9c4e-a5cd11c8f6a5): CREATE ROLE Customer
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171103175151_18b55176-607a-4c17-9c4e-a5cd11c8f6a5); Time taken: 0.028 seconds
INFO  : OK
No rows affected (0.125 seconds)
0: jdbc:hive2://localhost:10000/default> CREATE ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171103175252_4e96d86a-69c9-476c-b5a7-3dd44616dcac): CREATE ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175252_4e96d86a-69c9-476c-b5a7-3dd44616dcac); Time taken: 0.065 seconds
INFO  : Executing command(queryId=hive_20171103175252_4e96d86a-69c9-476c-b5a7-3dd44616dcac): CREATE ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171103175252_4e96d86a-69c9-476c-b5a7-3dd44616dcac); Time taken: 0.031 seconds
INFO  : OK
No rows affected (0.104 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE sentry_admin;
INFO  : Compiling command(queryId=hive_20171103175252_66608353-8d06-451e-9734-7b670170446f): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175252_66608353-8d06-451e-9734-7b670170446f); Time taken: 0.094 seconds
INFO  : Executing command(queryId=hive_20171103175252_66608353-8d06-451e-9734-7b670170446f): GRANT ALL ON SERVER server1 TO ROLE sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171103175252_66608353-8d06-451e-9734-7b670170446f); Time taken: 0.099 seconds
INFO  : OK
No rows affected (0.201 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE Logger to GROUP sanfrancisco;
INFO  : Compiling command(queryId=hive_20171103175353_a3294bd1-6c72-4d4a-aeef-69cbce0639f0): GRANT ROLE Logger to GROUP sanfrancisco
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175353_a3294bd1-6c72-4d4a-aeef-69cbce0639f0); Time taken: 0.062 seconds
INFO  : Executing command(queryId=hive_20171103175353_a3294bd1-6c72-4d4a-aeef-69cbce0639f0): GRANT ROLE Logger to GROUP sanfrancisco
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171103175353_a3294bd1-6c72-4d4a-aeef-69cbce0639f0); Time taken: 0.068 seconds
INFO  : OK
No rows affected (0.137 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ROLE Customer to GROUP paloalto;
INFO  : Compiling command(queryId=hive_20171103175353_182a1311-fc57-4948-bfbb-fc7614b164d6): GRANT ROLE Customer to GROUP paloalto
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175353_182a1311-fc57-4948-bfbb-fc7614b164d6); Time taken: 0.06 seconds
INFO  : Executing command(queryId=hive_20171103175353_182a1311-fc57-4948-bfbb-fc7614b164d6): GRANT ROLE Customer to GROUP paloalto
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171103175353_182a1311-fc57-4948-bfbb-fc7614b164d6); Time taken: 0.029 seconds
INFO  : OK
No rows affected (0.109 seconds)
0: jdbc:hive2://localhost:10000/default> grant all on database default to role sentry_admin;
INFO  : Compiling command(queryId=hive_20171103175353_93bf210a-6245-4b71-9372-490ae8cee907): grant all on database default to role sentry_admin
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175353_93bf210a-6245-4b71-9372-490ae8cee907); Time taken: 0.06 seconds
INFO  : Executing command(queryId=hive_20171103175353_93bf210a-6245-4b71-9372-490ae8cee907): grant all on database default to role sentry_admin
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171103175353_93bf210a-6245-4b71-9372-490ae8cee907); Time taken: 0.048 seconds
INFO  : OK
No rows affected (0.116 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE Logger;
INFO  : Compiling command(queryId=hive_20171103175454_7ff3bc06-0f6f-41ec-a0e3-7dbffce9e8ac): GRANT ALL ON SERVER server1 TO ROLE Logger
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175454_7ff3bc06-0f6f-41ec-a0e3-7dbffce9e8ac); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20171103175454_7ff3bc06-0f6f-41ec-a0e3-7dbffce9e8ac): GRANT ALL ON SERVER server1 TO ROLE Logger
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171103175454_7ff3bc06-0f6f-41ec-a0e3-7dbffce9e8ac); Time taken: 0.032 seconds
INFO  : OK
No rows affected (0.106 seconds)
0: jdbc:hive2://localhost:10000/default> GRANT ALL ON SERVER server1 TO ROLE Customer;
INFO  : Compiling command(queryId=hive_20171103175454_047b60e5-a23d-4c00-86be-84a166e999b2): GRANT ALL ON SERVER server1 TO ROLE Customer
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:null, properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175454_047b60e5-a23d-4c00-86be-84a166e999b2); Time taken: 0.066 seconds
INFO  : Executing command(queryId=hive_20171103175454_047b60e5-a23d-4c00-86be-84a166e999b2): GRANT ALL ON SERVER server1 TO ROLE Customer
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171103175454_047b60e5-a23d-4c00-86be-84a166e999b2); Time taken: 0.036 seconds
INFO  : OK
No rows affected (0.108 seconds)
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171103175454_5dd0e517-0231-46e8-836d-d0b051445148): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175454_5dd0e517-0231-46e8-836d-d0b051445148); Time taken: 0.244 seconds
INFO  : Executing command(queryId=hive_20171103175454_5dd0e517-0231-46e8-836d-d0b051445148): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171103175454_5dd0e517-0231-46e8-836d-d0b051445148); Time taken: 0.211 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| customers  |
| sample_07  |
| sample_08  |
| web_logs   |
+------------+--+
4 rows selected (0.571 seconds)
0: jdbc:hive2://localhost:10000/default> select * from web_logs sample 10;
Error: Error while compiling statement: FAILED: ParseException line 1:30 cannot recognize input near 'sample' '10' '<EOF>' in table source (state=42000,code=40000)
0: jdbc:hive2://localhost:10000/default> select * from web_logs limit 10;
INFO  : Compiling command(queryId=hive_20171103175555_34cbb335-d1e6-4cdf-8a19-e730426acfae): select * from web_logs limit 10
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:web_logs._version_, type:bigint, comment:null), FieldSchema(name:web_logs.app, type:string, comment:null), FieldSchema(name:web_logs.bytes, type:smallint, comment:null), FieldSchema(name:web_logs.city, type:string, comment:null), FieldSchema(name:web_logs.client_ip, type:string, comment:null), FieldSchema(name:web_logs.code, type:tinyint, comment:null), FieldSchema(name:web_logs.country_code, type:string, comment:null), FieldSchema(name:web_logs.country_code3, type:string, comment:null), FieldSchema(name:web_logs.country_name, type:string, comment:null), FieldSchema(name:web_logs.device_family, type:string, comment:null), FieldSchema(name:web_logs.extension, type:string, comment:null), FieldSchema(name:web_logs.latitude, type:float, comment:null), FieldSchema(name:web_logs.longitude, type:float, comment:null), FieldSchema(name:web_logs.method, type:string, comment:null), FieldSchema(name:web_logs.os_family, type:string, comment:null), FieldSchema(name:web_logs.os_major, type:string, comment:null), FieldSchema(name:web_logs.protocol, type:string, comment:null), FieldSchema(name:web_logs.record, type:string, comment:null), FieldSchema(name:web_logs.referer, type:string, comment:null), FieldSchema(name:web_logs.region_code, type:bigint, comment:null), FieldSchema(name:web_logs.request, type:string, comment:null), FieldSchema(name:web_logs.subapp, type:string, comment:null), FieldSchema(name:web_logs.time, type:string, comment:null), FieldSchema(name:web_logs.url, type:string, comment:null), FieldSchema(name:web_logs.user_agent, type:string, comment:null), FieldSchema(name:web_logs.user_agent_family, type:string, comment:null), FieldSchema(name:web_logs.user_agent_major, type:string, comment:null), FieldSchema(name:web_logs.id, type:string, comment:null), FieldSchema(name:web_logs.date, type:string, comment:null)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171103175555_34cbb335-d1e6-4cdf-8a19-e730426acfae); Time taken: 0.574 seconds
INFO  : Executing command(queryId=hive_20171103175555_34cbb335-d1e6-4cdf-8a19-e730426acfae): select * from web_logs limit 10
INFO  : Completed executing command(queryId=hive_20171103175555_34cbb335-d1e6-4cdf-8a19-e730426acfae); Time taken: 0.001 seconds
INFO  : OK
+----------------------+---------------+-----------------+----------------+---------------------+----------------+------------------------+-------------------------+------------------------+-------------------------+---------------------+---------------------+----------------------+------------------+---------------------+--------------------+--------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+------------------------------------------------------------+----------------------------+---------------------------------------+----------------+--+
|  web_logs._version_  | web_logs.app  | web_logs.bytes  | web_logs.city  | web_logs.client_ip  | web_logs.code  | web_logs.country_code  | web_logs.country_code3  | web_logs.country_name  | web_logs.device_family  | web_logs.extension  |  web_logs.latitude  |  web_logs.longitude  | web_logs.method  | web_logs.os_family  | web_logs.os_major  | web_logs.protocol  | web_logs.record  |                                                                                      web_logs.referer                                                                                       | web_logs.region_code  |                                                                                   web_logs.request                                                                                    | web_logs.subapp  |     web_logs.time     |                                                                               web_logs.url                                                                               |                               web_logs.user_agent                               |                 web_logs.user_agent_family                 | web_logs.user_agent_major  |              web_logs.id              | web_logs.date  |
+----------------------+---------------+-----------------+----------------+---------------------+----------------+------------------------+-------------------------+------------------------+-------------------------+---------------------+---------------------+----------------------+------------------+---------------------+--------------------+--------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+------------------------------------------------------------+----------------------------+---------------------------------------+----------------+--+
| 1480895575515725824  | metastore     | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 0                     | GET /metastore/table/default/sample_07 HTTP/1.1                                                                                                                                       | table            | 2014-05-04T06:35:49Z  | /metastore/table/default/sample_07                                                                                                                                       | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org)  | Other                                                      |                            | 8836e6ce-9a21-449f-a372-9e57641389b3  | 2015-11-18     |
| 1480895575528308736  | metastore     | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 0                     | GET /metastore/table/default/sample_07 HTTP/1.1                                                                                                                                       | table            | 2014-05-04T06:35:50Z  | /metastore/table/default/sample_07                                                                                                                                       | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org)  | Other                                                      |                            | 6ddf6e38-7b83-423c-8873-39842dca2dbb  | 2015-11-18     |
| 1480895575528308737  | search        | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 0                     | GET /search/?collection=10000001 HTTP/1.1                                                                                                                                             |                  | 2014-05-04T06:35:52Z  | /search/?collection=10000001                                                                                                                                             | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org)  | Other                                                      |                            | 313bb28e-dd7c-4364-a11e-9ffb0db7b303  | 2015-11-18     |
| 1480895575528308738  | search        | 1041            | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 0                     | GET /search/?collection=10000001 HTTP/1.1                                                                                                                                             |                  | 2014-05-04T06:35:53Z  | /search/?collection=10000001                                                                                                                                             | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org)  | Other                                                      |                            | ecb47c61-a9e4-4b59-9234-04bd57695987  | 2015-11-18     |
| 1480895575528308739  |               | 238             | Singapore      | 128.199.234.236     | NULL           | SG                     | SGP                     | Singapore              | Other                   |                     | 1.2930999994277954  | 103.85579681396484   | HEAD             | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 0                     | HEAD / HTTP/1.1                                                                                                                                                                       |                  | 2014-05-04T06:35:54Z  | /                                                                                                                                                                        | Mozilla/5.0 (compatible; phpservermon/3.0.1; +http://www.phpservermonitor.org)  | Other                                                      |                            | affdb6b9-3657-4d15-8af8-2ba2f3a69343  | 2015-11-18     |
| 1480895575528308740  | beeswax       | 1041            | Mountain View  | 66.249.76.236       | NULL           | US                     | USA                     | United States          | Spider                  |                     | 37.38600158691406   | -122.08380126953125  | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | NULL                  | GET /beeswax/query_history?q-type=beeswax&amp;q-user=dy8515s&amp;q-auto_query=off HTTP/1.1                                                                                            |                  | 2014-05-04T06:35:54Z  | /beeswax/query_history?q-type=beeswax&amp;q-user=dy8515s&amp;q-auto_query=off                                                                                            | Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)        | Googlebot                                                  | 2                          | e3f88d9e-7e5b-4ef7-8941-c0d83720616c  | 2015-11-18     |
| 1480895575528308741  |               | 1041            | Guiyang        | 222.85.131.87       | NULL           | CN                     | CHN                     | China                  | Other                   |                     | 26.58329963684082   | 106.7166976928711    | GET              | Windows 7           |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | 18                    | GET / HTTP/1.1                                                                                                                                                                        |                  | 2014-05-04T06:35:55Z  | /                                                                                                                                                                        | Mozilla/5.0 (compatible; MSIE 10.0; Windows NT 6.1; Trident/6.0)                | IE                                                         | 10                         | 4dbb1f74-6856-4fe3-8515-c53eab600b60  | 2015-11-18     |
| 1480895575529357312  | desktop       | 0               | Guiyang        | 222.85.131.87       | NULL           | CN                     | CHN                     | China                  | Other                   |                     | 26.58329963684082   | 106.7166976928711    |                  | Other               |                    |                    |                  | -                                                                                                                                                                                           | 18                    | -                                                                                                                                                                                     |                  | 2014-05-04T06:36:16Z  |                                                                                                                                                                          | -                                                                               | Other                                                      |                            | 86cdb56d-99c0-4701-a842-472741bb833a  | 2015-11-18     |
| 1480895575529357313  | search        | 1041            | Shanghai       | 101.226.168.225     | NULL           | CN                     | CHN                     | China                  | Other                   |                     | 31.04560089111328   | 121.39969635009766   | GET              | Windows 7           |                    | HTTP/1.1           |                  | http://demo.gethue.com/search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0  | 23                    | GET /search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0 HTTP/1.1     |                  | 2014-05-04T06:38:31Z  | /search/?collection=10000001&amp;fq=%7Cuser_statuses_count%3A%5B%229000%22%20TO%20%229999%22%5D%7Cuser_location%3A%22new%20york%22&amp;query&amp;rows=15&amp;start=0     | "Mozilla/5.0 (Windows NT 6.1) AppleWebKit/537.1 (KHTML                          |  like Gecko) Chrome/21.0.1180.89 Safari/537.1; 360Spider"  | Chrome                     | 21                                    | 2015-11-18     |
| 1480895575529357314  | search        | 1041            | Mountain View  | 66.249.76.225       | NULL           | US                     | USA                     | United States          | Spider                  |                     | 37.38600158691406   | -122.08380126953125  | GET              | Other               |                    | HTTP/1.1           |                  | -                                                                                                                                                                                           | NULL                  | GET /search/?collection=10000001&amp;query=&amp;fq=%7Cuser_followers_count%3A%5B%22100%22%20TO%20%22199%22%5D%7Cuser_location%3A%22philippines%22&amp;rows=15&amp;start=240 HTTP/1.1  |                  | 2014-05-04T06:38:55Z  | /search/?collection=10000001&amp;query=&amp;fq=%7Cuser_followers_count%3A%5B%22100%22%20TO%20%22199%22%5D%7Cuser_location%3A%22philippines%22&amp;rows=15&amp;start=240  | Mozilla/5.0 (compatible; Googlebot/2.1; +http://www.google.com/bot.html)        | Googlebot                                                  | 2                          | 8260ca42-55d6-4cd4-8beb-8767826dc929  | 2015-11-18     |
+----------------------+---------------+-----------------+----------------+---------------------+----------------+------------------------+-------------------------+------------------------+-------------------------+---------------------+---------------------+----------------------+------------------+---------------------+--------------------+--------------------+------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+-----------------------+---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------+------------------+-----------------------+--------------------------------------------------------------------------------------------------------------------------------------------------------------------------+---------------------------------------------------------------------------------+------------------------------------------------------------+----------------------------+---------------------------------------+----------------+--+
10 rows selected (0.841 seconds)
0: jdbc:hive2://localhost:10000/default> 

```

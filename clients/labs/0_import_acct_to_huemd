# Authenticate using Linux users/groups

```
[root@ip-172-31-41-199 hue]# export HUE_DATABASE_PASSWORD=mariadb
[root@ip-172-31-41-199 hue]# export HUE_IGNORE_PASSWORD_SCRIPT_ERRORS=1
[root@ip-172-31-41-199 hue]# export HUE_CONF_DIR="/var/run/cloudera-scm-agent/process/`ls -alrt /var/run/cloudera-scm-agent/process | grep HUE | tail -1 | awk '{print $9}'`"
[root@ip-172-31-41-199 hue]# /opt/cloudera/parcels/CDH/lib/hue/build/env/bin/hue useradmin_sync_with_unix
[12/Oct/2017 12:43:04 +0000] settings     DEBUG    DESKTOP_DB_TEST_NAME SET: /opt/cloudera/parcels/CDH-5.13.0-1.cdh5.13.0.p0.29/lib/hue/desktop/desktop-test.db
[12/Oct/2017 12:43:04 +0000] settings     DEBUG    DESKTOP_DB_TEST_USER SET: hue_test
[12/Oct/2017 09:43:05 +0000] __init__     INFO     Couldn't import snappy. Support for snappy compression disabled.
[12/Oct/2017 09:43:05 +0000] decorators   INFO     AXES: BEGIN LOG
[12/Oct/2017 09:43:05 +0000] decorators   INFO     Using django-axes 1.5.0
[12/Oct/2017 09:43:05 +0000] views        INFO     Created group sqoop
[12/Oct/2017 09:43:05 +0000] views        INFO     Created group hive
[12/Oct/2017 09:43:05 +0000] views        INFO     Created group hadoop
[12/Oct/2017 09:43:05 +0000] views        INFO     Created group llama
[12/Oct/2017 09:43:05 +0000] views        INFO     Created group mysentryprimarygroup
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user hadoopuser from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user httpfs from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user george from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user hdfs from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user kms from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user ferdinand from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user mapred from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user llama from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user ec2-user from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user yarn from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user deyabhishek79 from Unix
[12/Oct/2017 09:43:05 +0000] views        INFO     Synced user impala from Unix
```

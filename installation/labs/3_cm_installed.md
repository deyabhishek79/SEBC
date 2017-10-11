# Cloudera Manager and CDH Cluster Setup Prerequisites
## MySQL JDBC Driver
```
[root@ip-172-31-41-199 ~]#wget https://dev.mysql.com/get/Downloads/Connector-J/mysql-connector-java-5.1.44.tar.gz
[root@ip-172-31-41-199 ~]#tar zxvf mysql-connector-java-5.1.44.tar.gz
[root@ip-172-31-41-199 ~]#sudo mkdir -p /usr/share/java/
[root@ip-172-31-41-199 ~]#sudo cp mysql-connector-java-5.1.44/mysql-connector-java-5.1.44-bin.jar /usr/share/java/mysql-connector-java.jar

```

## Install Oracle JDK on the master node after downloading the rpm
```
[root@ip-172-31-41-199 ~]#yum install jdk-8u131-linux-x64.rpm
```

## Retrieve the correct repo for installation and modify the version of the CM
```
[root@ip-172-31-41-199 ~]#cd /etc/yum.repos.d/
[root@ip-172-31-41-199 ~]#wget "https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo"
[root@ip-172-31-41-199 ~]#vi cloudera-manager.repo 
[root@ip-172-31-41-199 ~]#mv cloudera-manager.repo cloudera-manager-5.9.3.repo 

```
Following entries needs to be edited into the repo file

```
[cloudera-manager]
name = Cloudera Manager, Version 5.9.3
baseurl = https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5.9.3/
gpgkey = https://archive.cloudera.com/redhat/cdh/RPM-GPG-KEY-cloudera
gpgcheck = 1
```

## Install CM Server and Daemon on master node
```
[root@ip-172-31-41-199 ~]#yum clean all
[root@ip-172-31-41-199 ~]#yum install cloudera-manager-daemons cloudera-manager-server

...
Is this ok [y/N]: y
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : cloudera-manager-daemons-5.9.3-1.cm593.p0.6.el7.x86_64                                                                                                           1/2 
  Installing : cloudera-manager-server-5.9.3-1.cm593.p0.6.el7.x86_64                                                                                                            2/2 
  Verifying  : cloudera-manager-daemons-5.9.3-1.cm593.p0.6.el7.x86_64                                                                                                           1/2 
  Verifying  : cloudera-manager-server-5.9.3-1.cm593.p0.6.el7.x86_64                                                                                                            2/2 

Installed:
  cloudera-manager-daemons.x86_64 0:5.9.3-1.cm593.p0.6.el7                                  cloudera-manager-server.x86_64 0:5.9.3-1.cm593.p0.6.el7                                 

```

## Prepare database for CM

```
[root@ip-172-31-41-199 ~]#sudo /usr/share/cmf/schema/scm_prepare_database.sh mysql cmdb mariadbuser mariadb

```

## Start CM Service

```
[root@ip-172-31-46-92 ~]# service cloudera-scm-server start
Starting cloudera-scm-server (via systemctl):              [  OK  ]

Check the logs at:
[root@ip-172-31-41-199 ~]#tail -f /var/log/cloudera-scm-server/cloudera-scm-server.log

```

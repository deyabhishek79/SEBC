# List the command and output for `ls /etc/yum.repos.d`

```
[root@ip-172-31-45-139 ~]# ls /etc/yum.repos.d
redhat.repo  redhat-rhui-client-config.repo  redhat-rhui.repo  rhui-load-balancers.conf
[root@ip-172-31-45-139 ~]# cd /etc/yum.repos.d/
[root@ip-172-31-45-139 yum.repos.d]# wget "https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo"
--2017-10-13 10:54:54--  https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/cloudera-manager.repo
Resolving archive.cloudera.com (archive.cloudera.com)... 151.101.32.167
Connecting to archive.cloudera.com (archive.cloudera.com)|151.101.32.167|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 290
Saving to: ‘cloudera-manager.repo’

100%[========================================================================================>] 290         --.-K/s   in 0s      

2017-10-13 10:54:54 (62.7 MB/s) - ‘cloudera-manager.repo’ saved [290/290]

[root@ip-172-31-45-139 yum.repos.d]# cat cloudera-manager.repo 
[cloudera-manager]
# Packages for Cloudera Manager, Version 5, on RedHat or CentOS 7 x86_64           	  
name=Cloudera Manager
baseurl=https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/5/
gpgkey =https://archive.cloudera.com/cm5/redhat/7/x86_64/cm/RPM-GPG-KEY-cloudera    
gpgcheck = 1


```

# List the cloud provider you are using (AWS, GCE, Azure, CloudCat, other)

`AWS`

# List your instances by IP address and DNS name

```
Public DNS
ec2-54-88-249-223.compute-1.amazonaws.com
ec2-54-91-82-50.compute-1.amazonaws.com
ec2-52-206-80-110.compute-1.amazonaws.com
ec2-34-228-220-92.compute-1.amazonaws.com
ec2-34-230-67-81.compute-1.amazonaws.com

Private DNS
ip-172-31-45-139.ec2.internal
ip-172-31-40-103.ec2.internal
ip-172-31-43-237.ec2.internal
ip-172-31-42-150.ec2.internal
ip-172-31-37-173.ec2.internal

```

# List the Linux release you are using 

`RHEL-7.2_HVM_GA-20151112-x86_64-1-Hourly2-GP2 (ami-2051294a)`


# List the file system capacity for the first node

```
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       40G  1.8G   39G   5% /

```

# List the command and output for `yum repolist enabled` 

```

root@ip-172-31-45-139 ec2-user]# yum repolist enabled
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                                                                    repo name                                                                                                status
!rhui-REGION-client-config-server-7/x86_64                                                 Red Hat Update Infrastructure 2.0 Client Configuration Server 7                                               6
!rhui-REGION-rhel-server-releases/7Server/x86_64                                           Red Hat Enterprise Linux Server 7 (RPMs)                                                                 17,255
!rhui-REGION-rhel-server-rh-common/7Server/x86_64                                          Red Hat Enterprise Linux Server 7 RH Common (RPMs)                                                          228
repolist: 17,489


``` 

# Add the following Linux accounts to all nodes

```
[root@ip-172-31-45-139 ~]# useradd jimenez -u 2800
[root@ip-172-31-45-139 ~]# useradd beltran -u 2900
[root@ip-172-31-45-139 ~]# groupadd astros
[root@ip-172-31-45-139 ~]# groupadd rangers
[root@ip-172-31-45-139 ~]# usermod -a -G astros beltran
[root@ip-172-31-45-139 ~]# usermod -a -G rangers jimenez
[root@ip-172-31-45-139 ~]# passwd jimenez
Changing password for user jimenez.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-45-139 ~]# passwd beltran
Changing password for user beltran.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-45-139 ~]# ssh ip-172-31-40-103.ec2.internal
Last login: Fri Oct 13 01:50:54 2017 from ip-172-31-45-139.ec2.internal
[root@ip-172-31-40-103 ~]# useradd jimenez -u 2800
[root@ip-172-31-40-103 ~]# useradd beltran -u 2900
[root@ip-172-31-40-103 ~]# groupadd astros
[root@ip-172-31-40-103 ~]# groupadd rangers
[root@ip-172-31-40-103 ~]# usermod -a -G astros beltran
[root@ip-172-31-40-103 ~]# usermod -a -G rangers jimenez
[root@ip-172-31-40-103 ~]# passwd beltran
Changing password for user beltran.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-40-103 ~]# passwd jimenez
Changing password for user jimenez.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-40-103 ~]# exit
logout
Connection to ip-172-31-40-103.ec2.internal closed.
[root@ip-172-31-45-139 ~]# ssh ip-172-31-43-237.ec2.internal
Last login: Fri Oct 13 01:51:10 2017 from ip-172-31-45-139.ec2.internal
[root@ip-172-31-43-237 ~]# useradd jimenez -u 2800
[root@ip-172-31-43-237 ~]# useradd beltran -u 2900
[root@ip-172-31-43-237 ~]# groupadd astros
[root@ip-172-31-43-237 ~]# groupadd rangers
[root@ip-172-31-43-237 ~]# usermod -a -G astros beltran
[root@ip-172-31-43-237 ~]# usermod -a -G rangers jimenez
[root@ip-172-31-43-237 ~]# passwd beltran
Changing password for user beltran.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-43-237 ~]# passwd jimenez
Changing password for user jimenez.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-43-237 ~]# exit
logout
Connection to ip-172-31-43-237.ec2.internal closed.
[root@ip-172-31-45-139 ~]# ssh ip-172-31-42-150.ec2.internal
Last login: Fri Oct 13 01:51:37 2017 from ip-172-31-45-139.ec2.internal
[root@ip-172-31-42-150 ~]# useradd jimenez -u 2800
[root@ip-172-31-42-150 ~]# useradd beltran -u 2900
[root@ip-172-31-42-150 ~]# groupadd astros
[root@ip-172-31-42-150 ~]# groupadd rangers
[root@ip-172-31-42-150 ~]# usermod -a -G astros beltran
[root@ip-172-31-42-150 ~]# usermod -a -G rangers jimenez
[root@ip-172-31-42-150 ~]# passwd beltran
Changing password for user beltran.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-42-150 ~]# passwd jimenez
Changing password for user jimenez.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-42-150 ~]# exit
logout
Connection to ip-172-31-42-150.ec2.internal closed.
[root@ip-172-31-45-139 ~]# ssh ip-172-31-37-173.ec2.internal
Last login: Fri Oct 13 01:51:57 2017 from ip-172-31-45-139.ec2.internal
[root@ip-172-31-37-173 ~]# useradd jimenez -u 2800
[root@ip-172-31-37-173 ~]# useradd beltran -u 2900
[root@ip-172-31-37-173 ~]# groupadd astros
[root@ip-172-31-37-173 ~]# groupadd rangers
[root@ip-172-31-37-173 ~]# usermod -a -G astros beltran
[root@ip-172-31-37-173 ~]# usermod -a -G rangers jimenez
[root@ip-172-31-37-173 ~]# passwd beltran
Changing password for user beltran.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-37-173 ~]# passwd jimenez
Changing password for user jimenez.
New password: 
Retype new password: 
passwd: all authentication tokens updated successfully.
[root@ip-172-31-37-173 ~]# exit
logout
Connection to ip-172-31-37-173.ec2.internal closed.

```

# List the `/etc/passwd` entries for `jimenez` and `beltran` 

```
jimenez:x:2800:2800::/home/jimenez:/bin/bash
beltran:x:2900:2900::/home/beltran:/bin/bash

```

# List the `/etc/group` entries for `astros` and `rangers` 

```
astros:x:2901:beltran
rangers:x:2902:jimenez

```

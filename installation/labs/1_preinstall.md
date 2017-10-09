#System Configuration Checks
##Check vm.swappiness on all your nodes
```
[ec2-user@ip-172-31-44-229 ~]$ sysctl vm.swappiness=1
[ec2-user@ip-172-31-44-229 ~]$ cat /proc/sys/vm/swappiness
1
```
##Show the mount attributes of your volume(s)
```
[ec2-user@ip-172-31-44-229 ~]$ mount
sysfs on /sys type sysfs (rw,nosuid,nodev,noexec,relatime,seclabel)
proc on /proc type proc (rw,nosuid,nodev,noexec,relatime)
devtmpfs on /dev type devtmpfs (rw,nosuid,seclabel,size=7599360k,nr_inodes=1899840,mode=755)
securityfs on /sys/kernel/security type securityfs (rw,nosuid,nodev,noexec,relatime)
tmpfs on /dev/shm type tmpfs (rw,nosuid,nodev,seclabel)
devpts on /dev/pts type devpts (rw,nosuid,noexec,relatime,seclabel,gid=5,mode=620,ptmxmode=000)
tmpfs on /run type tmpfs (rw,nosuid,nodev,seclabel,mode=755)
tmpfs on /sys/fs/cgroup type tmpfs (ro,nosuid,nodev,noexec,seclabel,mode=755)
cgroup on /sys/fs/cgroup/systemd type cgroup (rw,nosuid,nodev,noexec,relatime,xattr,release_agent=/usr/lib/systemd/systemd-cgroups-agent,name=systemd)
pstore on /sys/fs/pstore type pstore (rw,nosuid,nodev,noexec,relatime)
cgroup on /sys/fs/cgroup/devices type cgroup (rw,nosuid,nodev,noexec,relatime,devices)
cgroup on /sys/fs/cgroup/perf_event type cgroup (rw,nosuid,nodev,noexec,relatime,perf_event)
cgroup on /sys/fs/cgroup/net_cls type cgroup (rw,nosuid,nodev,noexec,relatime,net_cls)
cgroup on /sys/fs/cgroup/hugetlb type cgroup (rw,nosuid,nodev,noexec,relatime,hugetlb)
cgroup on /sys/fs/cgroup/freezer type cgroup (rw,nosuid,nodev,noexec,relatime,freezer)
cgroup on /sys/fs/cgroup/cpu,cpuacct type cgroup (rw,nosuid,nodev,noexec,relatime,cpuacct,cpu)
cgroup on /sys/fs/cgroup/blkio type cgroup (rw,nosuid,nodev,noexec,relatime,blkio)
cgroup on /sys/fs/cgroup/memory type cgroup (rw,nosuid,nodev,noexec,relatime,memory)
cgroup on /sys/fs/cgroup/cpuset type cgroup (rw,nosuid,nodev,noexec,relatime,cpuset)
configfs on /sys/kernel/config type configfs (rw,relatime)
/dev/xvda2 on / type xfs (rw,relatime,seclabel,attr2,inode64,noquota)
selinuxfs on /sys/fs/selinux type selinuxfs (rw,relatime)
debugfs on /sys/kernel/debug type debugfs (rw,relatime)
hugetlbfs on /dev/hugepages type hugetlbfs (rw,relatime,seclabel)
systemd-1 on /proc/sys/fs/binfmt_misc type autofs (rw,relatime,fd=28,pgrp=1,timeout=300,minproto=5,maxproto=5,direct)
mqueue on /dev/mqueue type mqueue (rw,relatime,seclabel)
tmpfs on /run/user/0 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700)
tmpfs on /run/user/1000 type tmpfs (rw,nosuid,nodev,relatime,seclabel,size=1497312k,mode=700,uid=1000,gid=1000)
```
## Disable transparent hugepage support
```
[ec2-user@ip-172-31-44-229 ~]$ grep -i HugePages_Total /proc/meminfo 
HugePages_Total:       0
[ec2-user@ip-172-31-44-229 ~]$ cat /proc/sys/vm/nr_hugepages 
0
[ec2-user@ip-172-31-44-229 ~]$ sysctl vm.nr_hugepages
vm.nr_hugepages = 0
```
Here it is already disabled. In case. we want to disable it , we can edit the file `/boot/grub/grub.conf` and put in the entry `transparent_hugepage=never`. Alternatively, we can also run un the following commands to disable THP on-the-fly
`echo never > /sys/kernel/mm/redhat_transparent_hugepage/enabled`
`echo never > /sys/kernel/mm/redhat_transparent_hugepage/defrag`

## Network Interface Configuration
```
[ec2-user@ip-172-31-44-229 ~]$ ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.44.229  netmask 255.255.240.0  broadcast 172.31.47.255
        inet6 fe80::cd2:85ff:fe48:5be2  prefixlen 64  scopeid 0x20<link>
        ether 0e:d2:85:48:5b:e2  txqueuelen 1000  (Ethernet)
        RX packets 5242  bytes 461398 (450.5 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 3559  bytes 516517 (504.4 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 4  bytes 340 (340.0 B)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 4  bytes 340 (340.0 B)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```
## DNS Lookups

### Install nslookup

```
[ec2-user@ip-172-31-44-229 ~]$ sudo yum install bind-utils
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
rhui-REGION-client-config-server-7                                                                                         | 2.9 kB  00:00:00     
rhui-REGION-rhel-server-releases                                                                                           | 3.5 kB  00:00:00     
rhui-REGION-rhel-server-rh-common                                                                                          | 3.8 kB  00:00:00     
(1/7): rhui-REGION-rhel-server-releases/7Server/x86_64/group                                                               | 709 kB  00:00:00     
(2/7): rhui-REGION-client-config-server-7/x86_64/primary_db                                                                | 5.5 kB  00:00:00     
(3/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/group                                                              |  104 B  00:00:00     
(4/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/updateinfo                                                         |  32 kB  00:00:00     
(5/7): rhui-REGION-rhel-server-releases/7Server/x86_64/updateinfo                                                          | 2.3 MB  00:00:00     
(6/7): rhui-REGION-rhel-server-rh-common/7Server/x86_64/primary_db                                                         | 119 kB  00:00:00     
(7/7): rhui-REGION-rhel-server-releases/7Server/x86_64/primary_db                                                          |  43 MB  00:00:00     
Resolving Dependencies
--> Running transaction check
---> Package bind-utils.x86_64 32:9.9.4-51.el7 will be installed
--> Processing Dependency: bind-libs = 32:9.9.4-51.el7 for package: 32:bind-utils-9.9.4-51.el7.x86_64
--> Processing Dependency: libGeoIP.so.1()(64bit) for package: 32:bind-utils-9.9.4-51.el7.x86_64
--> Processing Dependency: libbind9.so.90()(64bit) for package: 32:bind-utils-9.9.4-51.el7.x86_64
--> Processing Dependency: libdns.so.100()(64bit) for package: 32:bind-utils-9.9.4-51.el7.x86_64
--> Processing Dependency: libisc.so.95()(64bit) for package: 32:bind-utils-9.9.4-51.el7.x86_64
--> Processing Dependency: libisccc.so.90()(64bit) for package: 32:bind-utils-9.9.4-51.el7.x86_64
--> Processing Dependency: libisccfg.so.90()(64bit) for package: 32:bind-utils-9.9.4-51.el7.x86_64
--> Processing Dependency: liblwres.so.90()(64bit) for package: 32:bind-utils-9.9.4-51.el7.x86_64
--> Running transaction check
---> Package GeoIP.x86_64 0:1.5.0-11.el7 will be installed
---> Package bind-libs.x86_64 32:9.9.4-51.el7 will be installed
--> Processing Dependency: bind-license = 32:9.9.4-51.el7 for package: 32:bind-libs-9.9.4-51.el7.x86_64
--> Running transaction check
---> Package bind-license.noarch 32:9.9.4-29.el7 will be updated
--> Processing Dependency: bind-license = 32:9.9.4-29.el7 for package: 32:bind-libs-lite-9.9.4-29.el7.x86_64
---> Package bind-license.noarch 32:9.9.4-51.el7 will be an update
--> Running transaction check
---> Package bind-libs-lite.x86_64 32:9.9.4-29.el7 will be updated
---> Package bind-libs-lite.x86_64 32:9.9.4-51.el7 will be an update
--> Finished Dependency Resolution

Dependencies Resolved

==================================================================================================================================================
 Package                         Arch                    Version                          Repository                                         Size
==================================================================================================================================================
Installing:
 bind-utils                      x86_64                  32:9.9.4-51.el7                  rhui-REGION-rhel-server-releases                  203 k
Installing for dependencies:
 GeoIP                           x86_64                  1.5.0-11.el7                     rhui-REGION-rhel-server-releases                  1.1 M
 bind-libs                       x86_64                  32:9.9.4-51.el7                  rhui-REGION-rhel-server-releases                  1.0 M
Updating for dependencies:
 bind-libs-lite                  x86_64                  32:9.9.4-51.el7                  rhui-REGION-rhel-server-releases                  732 k
 bind-license                    noarch                  32:9.9.4-51.el7                  rhui-REGION-rhel-server-releases                   84 k

Transaction Summary
==================================================================================================================================================
Install  1 Package  (+2 Dependent packages)
Upgrade             ( 2 Dependent packages)

Total download size: 3.0 M
Is this ok [y/d/N]: y
Downloading packages:
Delta RPMs disabled because /usr/bin/applydeltarpm not installed.
(1/5): GeoIP-1.5.0-11.el7.x86_64.rpm                                                                                       | 1.1 MB  00:00:00     
(2/5): bind-libs-9.9.4-51.el7.x86_64.rpm                                                                                   | 1.0 MB  00:00:00     
(3/5): bind-libs-lite-9.9.4-51.el7.x86_64.rpm                                                                              | 732 kB  00:00:00     
(4/5): bind-license-9.9.4-51.el7.noarch.rpm                                                                                |  84 kB  00:00:00     
(5/5): bind-utils-9.9.4-51.el7.x86_64.rpm                                                                                  | 203 kB  00:00:00     
--------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                             7.6 MB/s | 3.0 MB  00:00:00     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : GeoIP-1.5.0-11.el7.x86_64                                                                                                      1/7 
  Updating   : 32:bind-license-9.9.4-51.el7.noarch                                                                                            2/7 
  Installing : 32:bind-libs-9.9.4-51.el7.x86_64                                                                                               3/7 
  Installing : 32:bind-utils-9.9.4-51.el7.x86_64                                                                                              4/7 
  Updating   : 32:bind-libs-lite-9.9.4-51.el7.x86_64                                                                                          5/7 
  Cleanup    : 32:bind-libs-lite-9.9.4-29.el7.x86_64                                                                                          6/7 
  Cleanup    : 32:bind-license-9.9.4-29.el7.noarch                                                                                            7/7 
  Verifying  : 32:bind-libs-lite-9.9.4-51.el7.x86_64                                                                                          1/7 
  Verifying  : 32:bind-utils-9.9.4-51.el7.x86_64                                                                                              2/7 
  Verifying  : 32:bind-license-9.9.4-51.el7.noarch                                                                                            3/7 
  Verifying  : GeoIP-1.5.0-11.el7.x86_64                                                                                                      4/7 
  Verifying  : 32:bind-libs-9.9.4-51.el7.x86_64                                                                                               5/7 
  Verifying  : 32:bind-license-9.9.4-29.el7.noarch                                                                                            6/7 
  Verifying  : 32:bind-libs-lite-9.9.4-29.el7.x86_64                                                                                          7/7 

Installed:
  bind-utils.x86_64 32:9.9.4-51.el7                                                                                                               

Dependency Installed:
  GeoIP.x86_64 0:1.5.0-11.el7                                           bind-libs.x86_64 32:9.9.4-51.el7                                          

Dependency Updated:
  bind-libs-lite.x86_64 32:9.9.4-51.el7                                    bind-license.noarch 32:9.9.4-51.el7                                   

Complete!

[ec2-user@ip-172-31-44-229 ~]$ sudo yum install bind
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
Resolving Dependencies
--> Running transaction check
---> Package bind.x86_64 32:9.9.4-51.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

==================================================================================================================================================
 Package                 Arch                      Version                              Repository                                           Size
==================================================================================================================================================
Installing:
 bind                    x86_64                    32:9.9.4-51.el7                      rhui-REGION-rhel-server-releases                    1.8 M

Transaction Summary
==================================================================================================================================================
Install  1 Package

Total download size: 1.8 M
Installed size: 4.3 M
Is this ok [y/d/N]: y
Downloading packages:
bind-9.9.4-51.el7.x86_64.rpm                                                                                               | 1.8 MB  00:00:00     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Installing : 32:bind-9.9.4-51.el7.x86_64                                                                                                    1/1 
  Verifying  : 32:bind-9.9.4-51.el7.x86_64                                                                                                    1/1 

Installed:
  bind.x86_64 32:9.9.4-51.el7                                                                                                                     

Complete!
```
Show nslookup output

```
[ec2-user@ip-172-31-44-229 ~]$ nslookup ec2-54-81-172-131.compute-1.amazonaws.com
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ec2-54-81-172-131.compute-1.amazonaws.com
Address: 172.31.44.229
```
getent output
```
[ec2-user@ip-172-31-44-229 ~]$ getent hosts ip-172-31-44-229
172.31.44.229   ip-172-31-44-229.ec2.internal
[ec2-user@ip-172-31-44-229 ~]$ getent hosts
127.0.0.1       localhost localhost.localdomain localhost4 localhost4.localdomain4
127.0.0.1       localhost localhost.localdomain localhost6 localhost6.localdomain6
```


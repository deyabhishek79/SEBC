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
....
Installed:
  bind-utils.x86_64 32:9.9.4-51.el7                                                                                                               

Dependency Installed:
  GeoIP.x86_64 0:1.5.0-11.el7                                           bind-libs.x86_64 32:9.9.4-51.el7                                          

Dependency Updated:
  bind-libs-lite.x86_64 32:9.9.4-51.el7                                    bind-license.noarch 32:9.9.4-51.el7                                   

Complete!

[ec2-user@ip-172-31-44-229 ~]$ sudo yum install bind
.....
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
## Enable NSCD service
```
[ec2-user@ip-172-31-44-229 ~]$ systemctl status named
● named.service - Berkeley Internet Name Domain (DNS)
   Loaded: loaded (/usr/lib/systemd/system/named.service; disabled; vendor preset: disabled)
   Active: inactive (dead)

[ec2-user@ip-172-31-44-229 ~]$ sudo systemctl enable named
Created symlink from /etc/systemd/system/multi-user.target.wants/named.service to /usr/lib/systemd/system/named.service.

[ec2-user@ip-172-31-44-229 ~]$ sudo systemctl status named
● named.service - Berkeley Internet Name Domain (DNS)
   Loaded: loaded (/usr/lib/systemd/system/named.service; enabled; vendor preset: disabled)
   Active: inactive (dead)

[ec2-user@ip-172-31-44-229 ~]$ sudo yum install nscd

[ec2-user@ip-172-31-44-229 ~]$ sudo chkconfig nscd on
Note: Forwarding request to 'systemctl enable nscd.service'.
Created symlink from /etc/systemd/system/multi-user.target.wants/nscd.service to /usr/lib/systemd/system/nscd.service.
Created symlink from /etc/systemd/system/sockets.target.wants/nscd.socket to /usr/lib/systemd/system/nscd.socket.
```
## NTPD Service

```
[ec2-user@ip-172-31-44-229 ~]$ sudo ntpq -p
     remote           refid      st t when poll reach   delay   offset  jitter
==============================================================================
*horp-bsd01.horp 164.67.62.194    2 u   59   64    7   22.204   -0.411   0.549
 tick.mdacore.ne 130.207.244.240  2 u   60   64    7   33.337   -9.906   0.029
 208.76.53.137   71.40.128.146    2 u   58   64    7   26.811   -8.795   0.062
 ntp1.wiktel.com .PPS.            1 u   54   64    7   38.373    0.889   0.026
[ec2-user@ip-172-31-44-229 ~]$ sudo ntpstat
synchronised to NTP server (69.89.207.99) at stratum 2 
   time correct to within 31 ms
   polling server every 64 s 
```
It was already running. For installation, follow the steps
Install using `sudo yum install ntp`.
Configure the NTP service to run at reboot using `sudo chkconfig ntpd on`.
Start Start the NTP service using `service ntpd start`.
Synchronize the node using `ntpdate -u <your_ntp_server>`.
Synchronize the system clock (to prevent synchronization problems) using `hwclock --systohc`.

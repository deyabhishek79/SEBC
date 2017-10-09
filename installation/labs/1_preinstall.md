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


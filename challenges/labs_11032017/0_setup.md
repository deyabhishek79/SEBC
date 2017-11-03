# List the cloud provider your are using
`AWS`

# List the Linux release you are using

```

[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "cat /etc/redhat-release";done
ip-172-31-34-47.ec2.internal
Red Hat Enterprise Linux Server release 7.2 (Maipo)
ip-172-31-44-218.ec2.internal
Red Hat Enterprise Linux Server release 7.2 (Maipo)
ip-172-31-38-76.ec2.internal
Red Hat Enterprise Linux Server release 7.2 (Maipo)
ip-172-31-45-193.ec2.internal
Red Hat Enterprise Linux Server release 7.2 (Maipo)
ip-172-31-47-237.ec2.internal
Red Hat Enterprise Linux Server release 7.2 (Maipo)

```

# List your instances by IP address and DNS name

```
[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; nslookup $i;done 
ip-172-31-34-47.ec2.internal
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ip-172-31-34-47.ec2.internal
Address: 172.31.34.47

ip-172-31-44-218.ec2.internal
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ip-172-31-44-218.ec2.internal
Address: 172.31.44.218

ip-172-31-38-76.ec2.internal
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ip-172-31-38-76.ec2.internal
Address: 172.31.38.76

ip-172-31-45-193.ec2.internal
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ip-172-31-45-193.ec2.internal
Address: 172.31.45.193

ip-172-31-47-237.ec2.internal
Server:		172.31.0.2
Address:	172.31.0.2#53

Non-authoritative answer:
Name:	ip-172-31-47-237.ec2.internal
Address: 172.31.47.237


```
# List the file system capacity for the 1st node

```

[root@ip-172-31-34-47 .ssh]# df -h .
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda2       40G  1.8G   39G   5% /
[root@ip-172-31-34-47 .ssh]# free -h
              total        used        free      shared  buff/cache   available
Mem:            14G        159M         12G         16M        1.3G         13G
Swap:            0B          0B          0B
[root@ip-172-31-34-47 .ssh]# cat /proc/cpuinfo | grep -i processor
processor	: 0
processor	: 1
processor	: 2
processor	: 3
[root@ip-172-31-34-47 .ssh]# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 9001
        inet 172.31.34.47  netmask 255.255.240.0  broadcast 172.31.47.255
        inet6 fe80::ce7:d7ff:fe9b:afea  prefixlen 64  scopeid 0x20<link>
        ether 0e:e7:d7:9b:af:ea  txqueuelen 1000  (Ethernet)
        RX packets 231852  bytes 255506954 (243.6 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 110628  bytes 8138969 (7.7 MiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 0  (Local Loopback)
        RX packets 769  bytes 164810 (160.9 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 769  bytes 164810 (160.9 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

```


# List the command and output for yum replolist enabled

```

[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "yum repolist enabled";done
ip-172-31-34-47.ec2.internal
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                          repo name                status
rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastru      8
rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linux 17,474
rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linux    228
repolist: 17,710
ip-172-31-44-218.ec2.internal
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                          repo name                status
rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastru      8
rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linux 17,474
rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linux    228
repolist: 17,710
ip-172-31-38-76.ec2.internal
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                          repo name                status
rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastru      8
rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linux 17,474
rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linux    228
repolist: 17,710
ip-172-31-45-193.ec2.internal
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                          repo name                status
rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastru      8
rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linux 17,474
rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linux    228
repolist: 17,710
ip-172-31-47-237.ec2.internal
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
repo id                                          repo name                status
rhui-REGION-client-config-server-7/x86_64        Red Hat Update Infrastru      8
rhui-REGION-rhel-server-releases/7Server/x86_64  Red Hat Enterprise Linux 17,474
rhui-REGION-rhel-server-rh-common/7Server/x86_64 Red Hat Enterprise Linux    228
repolist: 17,710

```

# Add the following Linux accounts to all nodes

## User reilly with a UID of 2800

```

ot@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "useradd -u 2800 reilly";done
ip-172-31-34-47.ec2.internal
ip-172-31-44-218.ec2.internal
ip-172-31-38-76.ec2.internal
ip-172-31-45-193.ec2.internal
ip-172-31-47-237.ec2.internal

```

## User frankola with a UID of 2900

```
[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "useradd -u 2900 frankola";done
ip-172-31-34-47.ec2.internal
ip-172-31-44-218.ec2.internal
ip-172-31-38-76.ec2.internal
ip-172-31-45-193.ec2.internal
ip-172-31-47-237.ec2.internal

```

## Create the group paloalto and add frankola to it

```
[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "groupadd paloalto";done
ip-172-31-34-47.ec2.internal
ip-172-31-44-218.ec2.internal
ip-172-31-38-76.ec2.internal
ip-172-31-45-193.ec2.internal
ip-172-31-47-237.ec2.internal
[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "usermod -G paloalto frankola";done
ip-172-31-34-47.ec2.internal
ip-172-31-44-218.ec2.internal
ip-172-31-38-76.ec2.internal
ip-172-31-45-193.ec2.internal
ip-172-31-47-237.ec2.internal

```

## Create the group sanfrancisco and add reilly to it

```
[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "usermod -G sanfrancisco reilly";done
ip-172-31-34-47.ec2.internal
ip-172-31-44-218.ec2.internal
ip-172-31-38-76.ec2.internal
ip-172-31-45-193.ec2.internal
ip-172-31-47-237.ec2.internal

[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "usermod -G sanfrancisco reilly";done
ip-172-31-34-47.ec2.internal
ip-172-31-44-218.ec2.internal
ip-172-31-38-76.ec2.internal
ip-172-31-45-193.ec2.internal
ip-172-31-47-237.ec2.internal

[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "id reilly";done
ip-172-31-34-47.ec2.internal
uid=2800(reilly) gid=2800(reilly) groups=2902(sanfrancisco),2800(reilly)
ip-172-31-44-218.ec2.internal
uid=2800(reilly) gid=2800(reilly) groups=2902(sanfrancisco),2800(reilly)
ip-172-31-38-76.ec2.internal
uid=2800(reilly) gid=2800(reilly) groups=2902(sanfrancisco),2800(reilly)
ip-172-31-45-193.ec2.internal
uid=2800(reilly) gid=2800(reilly) groups=2902(sanfrancisco),2800(reilly)
ip-172-31-47-237.ec2.internal
uid=2800(reilly) gid=2800(reilly) groups=2902(sanfrancisco),2800(reilly)
[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "id frankola";done
ip-172-31-34-47.ec2.internal
uid=2900(frankola) gid=2900(frankola) groups=2901(paloalto),2900(frankola)
ip-172-31-44-218.ec2.internal
uid=2900(frankola) gid=2900(frankola) groups=2901(paloalto),2900(frankola)
ip-172-31-38-76.ec2.internal
uid=2900(frankola) gid=2900(frankola) groups=2901(paloalto),2900(frankola)
ip-172-31-45-193.ec2.internal
uid=2900(frankola) gid=2900(frankola) groups=2901(paloalto),2900(frankola)
ip-172-31-47-237.ec2.internal
uid=2900(frankola) gid=2900(frankola) groups=2901(paloalto),2900(frankola)

```

# List the /etc/passwd entries for reilly and frankola

```
[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "cat /etc/passwd | egrep \"reilly|frankola\"";done
ip-172-31-34-47.ec2.internal
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash
ip-172-31-44-218.ec2.internal
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash
ip-172-31-38-76.ec2.internal
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash
ip-172-31-45-193.ec2.internal
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash
ip-172-31-47-237.ec2.internal
reilly:x:2800:2800::/home/reilly:/bin/bash
frankola:x:2900:2900::/home/frankola:/bin/bash

```

# List the /etc/group entries for paloalto and sanfrancisco

```
[root@ip-172-31-34-47 .ssh]# for i in `cat hosts`; do echo $i; ssh $i "cat /etc/group | egrep \"paloalto|sanfrancisco\"";done
ip-172-31-34-47.ec2.internal
paloalto:x:2901:frankola
sanfrancisco:x:2902:reilly
ip-172-31-44-218.ec2.internal
paloalto:x:2901:frankola
sanfrancisco:x:2902:reilly
ip-172-31-38-76.ec2.internal
paloalto:x:2901:frankola
sanfrancisco:x:2902:reilly
ip-172-31-45-193.ec2.internal
paloalto:x:2901:frankola
sanfrancisco:x:2902:reilly
ip-172-31-47-237.ec2.internal
paloalto:x:2901:frankola
sanfrancisco:x:2902:reilly

```

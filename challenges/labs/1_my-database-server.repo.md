# MariaDB Conf repo

```
[root@ip-172-31-45-139 ~]# sudo yum install mariadb-server
Loaded plugins: amazon-id, rhui-lb, search-disabled-repos
rhui-REGION-client-config-server-7                                                                                                                                                 | 2.9 kB  00:00:00     
rhui-REGION-rhel-server-releases                                                                                                                                                   | 3.5 kB  00:00:00     
rhui-REGION-rhel-server-rh-common                                                                                                                                                  | 3.8 kB  00:00:00     
Resolving Dependencies
--> Running transaction check
---> Package mariadb-server.x86_64 1:5.5.56-2.el7 will be installed
--> Processing Dependency: mariadb(x86-64) = 1:5.5.56-2.el7 for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: mariadb-libs(x86-64) = 1:5.5.56-2.el7 for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: /usr/bin/perl for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: libaio.so.1(LIBAIO_0.1)(64bit) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: libaio.so.1(LIBAIO_0.4)(64bit) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(DBI) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(Data::Dumper) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(File::Basename) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(File::Copy) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(File::Path) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(File::Temp) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(Getopt::Long) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(POSIX) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(Sys::Hostname) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(strict) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl(vars) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl-DBD-MySQL for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: perl-DBI for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Processing Dependency: libaio.so.1()(64bit) for package: 1:mariadb-server-5.5.56-2.el7.x86_64
--> Running transaction check
---> Package libaio.x86_64 0:0.3.109-13.el7 will be installed
---> Package mariadb.x86_64 1:5.5.56-2.el7 will be installed
--> Processing Dependency: perl(Exporter) for package: 1:mariadb-5.5.56-2.el7.x86_64
---> Package mariadb-libs.x86_64 1:5.5.44-2.el7 will be updated
---> Package mariadb-libs.x86_64 1:5.5.56-2.el7 will be an update
---> Package perl.x86_64 4:5.16.3-292.el7 will be installed
--> Processing Dependency: perl-libs = 4:5.16.3-292.el7 for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Scalar::Util) >= 1.10 for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Socket) >= 1.3 for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Carp) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Cwd) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(File::Spec) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(File::Spec::Functions) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(File::Spec::Unix) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Filter::Util::Call) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Pod::Simple::Search) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Pod::Simple::XHTML) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Scalar::Util) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Socket) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Storable) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Time::HiRes) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(Time::Local) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(constant) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(threads) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl(threads::shared) for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl-libs for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: perl-macros for package: 4:perl-5.16.3-292.el7.x86_64
--> Processing Dependency: libperl.so()(64bit) for package: 4:perl-5.16.3-292.el7.x86_64
---> Package perl-DBD-MySQL.x86_64 0:4.023-5.el7 will be installed
---> Package perl-DBI.x86_64 0:1.627-4.el7 will be installed
--> Processing Dependency: perl(RPC::PlClient) >= 0.2000 for package: perl-DBI-1.627-4.el7.x86_64
--> Processing Dependency: perl(RPC::PlServer) >= 0.2001 for package: perl-DBI-1.627-4.el7.x86_64
---> Package perl-Data-Dumper.x86_64 0:2.145-3.el7 will be installed
---> Package perl-File-Path.noarch 0:2.09-2.el7 will be installed
---> Package perl-File-Temp.noarch 0:0.23.01-3.el7 will be installed
---> Package perl-Getopt-Long.noarch 0:2.40-2.el7 will be installed
--> Processing Dependency: perl(Pod::Usage) >= 1.14 for package: perl-Getopt-Long-2.40-2.el7.noarch
--> Processing Dependency: perl(Text::ParseWords) for package: perl-Getopt-Long-2.40-2.el7.noarch
--> Running transaction check
---> Package perl-Carp.noarch 0:1.26-244.el7 will be installed
---> Package perl-Exporter.noarch 0:5.68-3.el7 will be installed
---> Package perl-Filter.x86_64 0:1.49-3.el7 will be installed
---> Package perl-PathTools.x86_64 0:3.40-5.el7 will be installed
---> Package perl-PlRPC.noarch 0:0.2020-14.el7 will be installed
--> Processing Dependency: perl(Net::Daemon) >= 0.13 for package: perl-PlRPC-0.2020-14.el7.noarch
--> Processing Dependency: perl(Compress::Zlib) for package: perl-PlRPC-0.2020-14.el7.noarch
--> Processing Dependency: perl(Net::Daemon::Log) for package: perl-PlRPC-0.2020-14.el7.noarch
--> Processing Dependency: perl(Net::Daemon::Test) for package: perl-PlRPC-0.2020-14.el7.noarch
---> Package perl-Pod-Simple.noarch 1:3.28-4.el7 will be installed
--> Processing Dependency: perl(Pod::Escapes) >= 1.04 for package: 1:perl-Pod-Simple-3.28-4.el7.noarch
--> Processing Dependency: perl(Encode) for package: 1:perl-Pod-Simple-3.28-4.el7.noarch
---> Package perl-Pod-Usage.noarch 0:1.63-3.el7 will be installed
--> Processing Dependency: perl(Pod::Text) >= 3.15 for package: perl-Pod-Usage-1.63-3.el7.noarch
--> Processing Dependency: perl-Pod-Perldoc for package: perl-Pod-Usage-1.63-3.el7.noarch
---> Package perl-Scalar-List-Utils.x86_64 0:1.27-248.el7 will be installed
---> Package perl-Socket.x86_64 0:2.010-4.el7 will be installed
---> Package perl-Storable.x86_64 0:2.45-3.el7 will be installed
---> Package perl-Text-ParseWords.noarch 0:3.29-4.el7 will be installed
---> Package perl-Time-HiRes.x86_64 4:1.9725-3.el7 will be installed
---> Package perl-Time-Local.noarch 0:1.2300-2.el7 will be installed
---> Package perl-constant.noarch 0:1.27-2.el7 will be installed
---> Package perl-libs.x86_64 4:5.16.3-292.el7 will be installed
---> Package perl-macros.x86_64 4:5.16.3-292.el7 will be installed
---> Package perl-threads.x86_64 0:1.87-4.el7 will be installed
---> Package perl-threads-shared.x86_64 0:1.43-6.el7 will be installed
--> Running transaction check
---> Package perl-Encode.x86_64 0:2.51-7.el7 will be installed
---> Package perl-IO-Compress.noarch 0:2.061-2.el7 will be installed
--> Processing Dependency: perl(Compress::Raw::Bzip2) >= 2.061 for package: perl-IO-Compress-2.061-2.el7.noarch
--> Processing Dependency: perl(Compress::Raw::Zlib) >= 2.061 for package: perl-IO-Compress-2.061-2.el7.noarch
---> Package perl-Net-Daemon.noarch 0:0.48-5.el7 will be installed
---> Package perl-Pod-Escapes.noarch 1:1.04-292.el7 will be installed
---> Package perl-Pod-Perldoc.noarch 0:3.20-4.el7 will be installed
--> Processing Dependency: perl(HTTP::Tiny) for package: perl-Pod-Perldoc-3.20-4.el7.noarch
--> Processing Dependency: perl(parent) for package: perl-Pod-Perldoc-3.20-4.el7.noarch
---> Package perl-podlators.noarch 0:2.5.1-3.el7 will be installed
--> Running transaction check
---> Package perl-Compress-Raw-Bzip2.x86_64 0:2.061-3.el7 will be installed
---> Package perl-Compress-Raw-Zlib.x86_64 1:2.061-4.el7 will be installed
---> Package perl-HTTP-Tiny.noarch 0:0.033-3.el7 will be installed
---> Package perl-parent.noarch 1:0.225-244.el7 will be installed
--> Finished Dependency Resolution

Dependencies Resolved

==========================================================================================================================================================================================================
 Package                                             Arch                               Version                                        Repository                                                    Size
==========================================================================================================================================================================================================
Installing:
 mariadb-server                                      x86_64                             1:5.5.56-2.el7                                 rhui-REGION-rhel-server-releases                              11 M
Installing for dependencies:
 libaio                                              x86_64                             0.3.109-13.el7                                 rhui-REGION-rhel-server-releases                              24 k
 mariadb                                             x86_64                             1:5.5.56-2.el7                                 rhui-REGION-rhel-server-releases                             9.1 M
 perl                                                x86_64                             4:5.16.3-292.el7                               rhui-REGION-rhel-server-releases                             8.0 M
 perl-Carp                                           noarch                             1.26-244.el7                                   rhui-REGION-rhel-server-releases                              19 k
 perl-Compress-Raw-Bzip2                             x86_64                             2.061-3.el7                                    rhui-REGION-rhel-server-releases                              32 k
 perl-Compress-Raw-Zlib                              x86_64                             1:2.061-4.el7                                  rhui-REGION-rhel-server-releases                              57 k
 perl-DBD-MySQL                                      x86_64                             4.023-5.el7                                    rhui-REGION-rhel-server-releases                             140 k
 perl-DBI                                            x86_64                             1.627-4.el7                                    rhui-REGION-rhel-server-releases                             802 k
 perl-Data-Dumper                                    x86_64                             2.145-3.el7                                    rhui-REGION-rhel-server-releases                              47 k
 perl-Encode                                         x86_64                             2.51-7.el7                                     rhui-REGION-rhel-server-releases                             1.5 M
 perl-Exporter                                       noarch                             5.68-3.el7                                     rhui-REGION-rhel-server-releases                              28 k
 perl-File-Path                                      noarch                             2.09-2.el7                                     rhui-REGION-rhel-server-releases                              27 k
 perl-File-Temp                                      noarch                             0.23.01-3.el7                                  rhui-REGION-rhel-server-releases                              56 k
 perl-Filter                                         x86_64                             1.49-3.el7                                     rhui-REGION-rhel-server-releases                              76 k
 perl-Getopt-Long                                    noarch                             2.40-2.el7                                     rhui-REGION-rhel-server-releases                              56 k
 perl-HTTP-Tiny                                      noarch                             0.033-3.el7                                    rhui-REGION-rhel-server-releases                              38 k
 perl-IO-Compress                                    noarch                             2.061-2.el7                                    rhui-REGION-rhel-server-releases                             260 k
 perl-Net-Daemon                                     noarch                             0.48-5.el7                                     rhui-REGION-rhel-server-releases                              51 k
 perl-PathTools                                      x86_64                             3.40-5.el7                                     rhui-REGION-rhel-server-releases                              83 k
 perl-PlRPC                                          noarch                             0.2020-14.el7                                  rhui-REGION-rhel-server-releases                              36 k
 perl-Pod-Escapes                                    noarch                             1:1.04-292.el7                                 rhui-REGION-rhel-server-releases                              51 k
 perl-Pod-Perldoc                                    noarch                             3.20-4.el7                                     rhui-REGION-rhel-server-releases                              87 k
 perl-Pod-Simple                                     noarch                             1:3.28-4.el7                                   rhui-REGION-rhel-server-releases                             216 k
 perl-Pod-Usage                                      noarch                             1.63-3.el7                                     rhui-REGION-rhel-server-releases                              27 k
 perl-Scalar-List-Utils                              x86_64                             1.27-248.el7                                   rhui-REGION-rhel-server-releases                              36 k
 perl-Socket                                         x86_64                             2.010-4.el7                                    rhui-REGION-rhel-server-releases                              49 k
 perl-Storable                                       x86_64                             2.45-3.el7                                     rhui-REGION-rhel-server-releases                              77 k
 perl-Text-ParseWords                                noarch                             3.29-4.el7                                     rhui-REGION-rhel-server-releases                              14 k
 perl-Time-HiRes                                     x86_64                             4:1.9725-3.el7                                 rhui-REGION-rhel-server-releases                              45 k
 perl-Time-Local                                     noarch                             1.2300-2.el7                                   rhui-REGION-rhel-server-releases                              24 k
 perl-constant                                       noarch                             1.27-2.el7                                     rhui-REGION-rhel-server-releases                              19 k
 perl-libs                                           x86_64                             4:5.16.3-292.el7                               rhui-REGION-rhel-server-releases                             688 k
 perl-macros                                         x86_64                             4:5.16.3-292.el7                               rhui-REGION-rhel-server-releases                              43 k
 perl-parent                                         noarch                             1:0.225-244.el7                                rhui-REGION-rhel-server-releases                              12 k
 perl-podlators                                      noarch                             2.5.1-3.el7                                    rhui-REGION-rhel-server-releases                             112 k
 perl-threads                                        x86_64                             1.87-4.el7                                     rhui-REGION-rhel-server-releases                              49 k
 perl-threads-shared                                 x86_64                             1.43-6.el7                                     rhui-REGION-rhel-server-releases                              39 k
Updating for dependencies:
 mariadb-libs                                        x86_64                             1:5.5.56-2.el7                                 rhui-REGION-rhel-server-releases                             757 k

Transaction Summary
==========================================================================================================================================================================================================
Install  1 Package  (+37 Dependent packages)
Upgrade             (  1 Dependent package)

Total download size: 34 M
Is this ok [y/d/N]: y
Downloading packages:
Delta RPMs disabled because /usr/bin/applydeltarpm not installed.
(1/39): mariadb-libs-5.5.56-2.el7.x86_64.rpm                                                                                                                                       | 757 kB  00:00:00     
(2/39): libaio-0.3.109-13.el7.x86_64.rpm                                                                                                                                           |  24 kB  00:00:00     
(3/39): mariadb-5.5.56-2.el7.x86_64.rpm                                                                                                                                            | 9.1 MB  00:00:00     
(4/39): perl-5.16.3-292.el7.x86_64.rpm                                                                                                                                             | 8.0 MB  00:00:00     
(5/39): mariadb-server-5.5.56-2.el7.x86_64.rpm                                                                                                                                     |  11 MB  00:00:00     
(6/39): perl-Compress-Raw-Bzip2-2.061-3.el7.x86_64.rpm                                                                                                                             |  32 kB  00:00:00     
(7/39): perl-Carp-1.26-244.el7.noarch.rpm                                                                                                                                          |  19 kB  00:00:00     
(8/39): perl-Compress-Raw-Zlib-2.061-4.el7.x86_64.rpm                                                                                                                              |  57 kB  00:00:00     
(9/39): perl-DBD-MySQL-4.023-5.el7.x86_64.rpm                                                                                                                                      | 140 kB  00:00:00     
(10/39): perl-Data-Dumper-2.145-3.el7.x86_64.rpm                                                                                                                                   |  47 kB  00:00:00     
(11/39): perl-DBI-1.627-4.el7.x86_64.rpm                                                                                                                                           | 802 kB  00:00:00     
(12/39): perl-Exporter-5.68-3.el7.noarch.rpm                                                                                                                                       |  28 kB  00:00:00     
(13/39): perl-Encode-2.51-7.el7.x86_64.rpm                                                                                                                                         | 1.5 MB  00:00:00     
(14/39): perl-File-Temp-0.23.01-3.el7.noarch.rpm                                                                                                                                   |  56 kB  00:00:00     
(15/39): perl-File-Path-2.09-2.el7.noarch.rpm                                                                                                                                      |  27 kB  00:00:00     
(16/39): perl-Filter-1.49-3.el7.x86_64.rpm                                                                                                                                         |  76 kB  00:00:00     
(17/39): perl-Getopt-Long-2.40-2.el7.noarch.rpm                                                                                                                                    |  56 kB  00:00:00     
(18/39): perl-HTTP-Tiny-0.033-3.el7.noarch.rpm                                                                                                                                     |  38 kB  00:00:00     
(19/39): perl-IO-Compress-2.061-2.el7.noarch.rpm                                                                                                                                   | 260 kB  00:00:00     
(20/39): perl-Net-Daemon-0.48-5.el7.noarch.rpm                                                                                                                                     |  51 kB  00:00:00     
(21/39): perl-PlRPC-0.2020-14.el7.noarch.rpm                                                                                                                                       |  36 kB  00:00:00     
(22/39): perl-PathTools-3.40-5.el7.x86_64.rpm                                                                                                                                      |  83 kB  00:00:00     
(23/39): perl-Pod-Escapes-1.04-292.el7.noarch.rpm                                                                                                                                  |  51 kB  00:00:00     
(24/39): perl-Pod-Perldoc-3.20-4.el7.noarch.rpm                                                                                                                                    |  87 kB  00:00:00     
(25/39): perl-Pod-Simple-3.28-4.el7.noarch.rpm                                                                                                                                     | 216 kB  00:00:00     
(26/39): perl-Pod-Usage-1.63-3.el7.noarch.rpm                                                                                                                                      |  27 kB  00:00:00     
(27/39): perl-Scalar-List-Utils-1.27-248.el7.x86_64.rpm                                                                                                                            |  36 kB  00:00:00     
(28/39): perl-Storable-2.45-3.el7.x86_64.rpm                                                                                                                                       |  77 kB  00:00:00     
(29/39): perl-Socket-2.010-4.el7.x86_64.rpm                                                                                                                                        |  49 kB  00:00:00     
(30/39): perl-Text-ParseWords-3.29-4.el7.noarch.rpm                                                                                                                                |  14 kB  00:00:00     
(31/39): perl-Time-HiRes-1.9725-3.el7.x86_64.rpm                                                                                                                                   |  45 kB  00:00:00     
(32/39): perl-Time-Local-1.2300-2.el7.noarch.rpm                                                                                                                                   |  24 kB  00:00:00     
(33/39): perl-constant-1.27-2.el7.noarch.rpm                                                                                                                                       |  19 kB  00:00:00     
(34/39): perl-libs-5.16.3-292.el7.x86_64.rpm                                                                                                                                       | 688 kB  00:00:00     
(35/39): perl-parent-0.225-244.el7.noarch.rpm                                                                                                                                      |  12 kB  00:00:00     
(36/39): perl-macros-5.16.3-292.el7.x86_64.rpm                                                                                                                                     |  43 kB  00:00:00     
(37/39): perl-podlators-2.5.1-3.el7.noarch.rpm                                                                                                                                     | 112 kB  00:00:00     
(38/39): perl-threads-1.87-4.el7.x86_64.rpm                                                                                                                                        |  49 kB  00:00:00     
(39/39): perl-threads-shared-1.43-6.el7.x86_64.rpm                                                                                                                                 |  39 kB  00:00:00     
----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
Total                                                                                                                                                                      18 MB/s |  34 MB  00:00:01     
Running transaction check
Running transaction test
Transaction test succeeded
Running transaction
  Updating   : 1:mariadb-libs-5.5.56-2.el7.x86_64                                                                                                                                                    1/40 
  Installing : 1:perl-parent-0.225-244.el7.noarch                                                                                                                                                    2/40 
  Installing : perl-HTTP-Tiny-0.033-3.el7.noarch                                                                                                                                                     3/40 
  Installing : perl-podlators-2.5.1-3.el7.noarch                                                                                                                                                     4/40 
  Installing : perl-Pod-Perldoc-3.20-4.el7.noarch                                                                                                                                                    5/40 
  Installing : 1:perl-Pod-Escapes-1.04-292.el7.noarch                                                                                                                                                6/40 
  Installing : perl-Text-ParseWords-3.29-4.el7.noarch                                                                                                                                                7/40 
  Installing : perl-Encode-2.51-7.el7.x86_64                                                                                                                                                         8/40 
  Installing : perl-Pod-Usage-1.63-3.el7.noarch                                                                                                                                                      9/40 
  Installing : 4:perl-macros-5.16.3-292.el7.x86_64                                                                                                                                                  10/40 
  Installing : 4:perl-libs-5.16.3-292.el7.x86_64                                                                                                                                                    11/40 
  Installing : perl-Storable-2.45-3.el7.x86_64                                                                                                                                                      12/40 
  Installing : perl-Exporter-5.68-3.el7.noarch                                                                                                                                                      13/40 
  Installing : perl-constant-1.27-2.el7.noarch                                                                                                                                                      14/40 
  Installing : perl-Time-Local-1.2300-2.el7.noarch                                                                                                                                                  15/40 
  Installing : perl-Socket-2.010-4.el7.x86_64                                                                                                                                                       16/40 
  Installing : perl-Carp-1.26-244.el7.noarch                                                                                                                                                        17/40 
  Installing : 4:perl-Time-HiRes-1.9725-3.el7.x86_64                                                                                                                                                18/40 
  Installing : perl-PathTools-3.40-5.el7.x86_64                                                                                                                                                     19/40 
  Installing : perl-Scalar-List-Utils-1.27-248.el7.x86_64                                                                                                                                           20/40 
  Installing : perl-File-Temp-0.23.01-3.el7.noarch                                                                                                                                                  21/40 
  Installing : perl-File-Path-2.09-2.el7.noarch                                                                                                                                                     22/40 
  Installing : perl-threads-shared-1.43-6.el7.x86_64                                                                                                                                                23/40 
  Installing : perl-threads-1.87-4.el7.x86_64                                                                                                                                                       24/40 
  Installing : perl-Filter-1.49-3.el7.x86_64                                                                                                                                                        25/40 
  Installing : 1:perl-Pod-Simple-3.28-4.el7.noarch                                                                                                                                                  26/40 
  Installing : perl-Getopt-Long-2.40-2.el7.noarch                                                                                                                                                   27/40 
  Installing : 4:perl-5.16.3-292.el7.x86_64                                                                                                                                                         28/40 
  Installing : perl-Data-Dumper-2.145-3.el7.x86_64                                                                                                                                                  29/40 
  Installing : perl-Compress-Raw-Bzip2-2.061-3.el7.x86_64                                                                                                                                           30/40 
  Installing : perl-Net-Daemon-0.48-5.el7.noarch                                                                                                                                                    31/40 
  Installing : 1:perl-Compress-Raw-Zlib-2.061-4.el7.x86_64                                                                                                                                          32/40 
  Installing : perl-IO-Compress-2.061-2.el7.noarch                                                                                                                                                  33/40 
  Installing : perl-PlRPC-0.2020-14.el7.noarch                                                                                                                                                      34/40 
  Installing : perl-DBI-1.627-4.el7.x86_64                                                                                                                                                          35/40 
  Installing : perl-DBD-MySQL-4.023-5.el7.x86_64                                                                                                                                                    36/40 
  Installing : 1:mariadb-5.5.56-2.el7.x86_64                                                                                                                                                        37/40 
  Installing : libaio-0.3.109-13.el7.x86_64                                                                                                                                                         38/40 
  Installing : 1:mariadb-server-5.5.56-2.el7.x86_64                                                                                                                                                 39/40 
  Cleanup    : 1:mariadb-libs-5.5.44-2.el7.x86_64                                                                                                                                                   40/40 
  Verifying  : perl-HTTP-Tiny-0.033-3.el7.noarch                                                                                                                                                     1/40 
  Verifying  : perl-threads-shared-1.43-6.el7.x86_64                                                                                                                                                 2/40 
  Verifying  : perl-Storable-2.45-3.el7.x86_64                                                                                                                                                       3/40 
  Verifying  : perl-IO-Compress-2.061-2.el7.noarch                                                                                                                                                   4/40 
  Verifying  : perl-Exporter-5.68-3.el7.noarch                                                                                                                                                       5/40 
  Verifying  : perl-constant-1.27-2.el7.noarch                                                                                                                                                       6/40 
  Verifying  : perl-PathTools-3.40-5.el7.x86_64                                                                                                                                                      7/40 
  Verifying  : 4:perl-macros-5.16.3-292.el7.x86_64                                                                                                                                                   8/40 
  Verifying  : 1:mariadb-server-5.5.56-2.el7.x86_64                                                                                                                                                  9/40 
  Verifying  : perl-Compress-Raw-Bzip2-2.061-3.el7.x86_64                                                                                                                                           10/40 
  Verifying  : 1:perl-parent-0.225-244.el7.noarch                                                                                                                                                   11/40 
  Verifying  : perl-Net-Daemon-0.48-5.el7.noarch                                                                                                                                                    12/40 
  Verifying  : 4:perl-5.16.3-292.el7.x86_64                                                                                                                                                         13/40 
  Verifying  : perl-File-Temp-0.23.01-3.el7.noarch                                                                                                                                                  14/40 
  Verifying  : 1:perl-Pod-Simple-3.28-4.el7.noarch                                                                                                                                                  15/40 
  Verifying  : perl-Time-Local-1.2300-2.el7.noarch                                                                                                                                                  16/40 
  Verifying  : 4:perl-libs-5.16.3-292.el7.x86_64                                                                                                                                                    17/40 
  Verifying  : perl-Pod-Perldoc-3.20-4.el7.noarch                                                                                                                                                   18/40 
  Verifying  : perl-DBD-MySQL-4.023-5.el7.x86_64                                                                                                                                                    19/40 
  Verifying  : libaio-0.3.109-13.el7.x86_64                                                                                                                                                         20/40 
  Verifying  : perl-Socket-2.010-4.el7.x86_64                                                                                                                                                       21/40 
  Verifying  : perl-Carp-1.26-244.el7.noarch                                                                                                                                                        22/40 
  Verifying  : perl-Data-Dumper-2.145-3.el7.x86_64                                                                                                                                                  23/40 
  Verifying  : 4:perl-Time-HiRes-1.9725-3.el7.x86_64                                                                                                                                                24/40 
  Verifying  : perl-Scalar-List-Utils-1.27-248.el7.x86_64                                                                                                                                           25/40 
  Verifying  : 1:perl-Compress-Raw-Zlib-2.061-4.el7.x86_64                                                                                                                                          26/40 
  Verifying  : 1:perl-Pod-Escapes-1.04-292.el7.noarch                                                                                                                                               27/40 
  Verifying  : perl-PlRPC-0.2020-14.el7.noarch                                                                                                                                                      28/40 
  Verifying  : perl-Pod-Usage-1.63-3.el7.noarch                                                                                                                                                     29/40 
  Verifying  : perl-DBI-1.627-4.el7.x86_64                                                                                                                                                          30/40 
  Verifying  : perl-Encode-2.51-7.el7.x86_64                                                                                                                                                        31/40 
  Verifying  : perl-podlators-2.5.1-3.el7.noarch                                                                                                                                                    32/40 
  Verifying  : perl-Getopt-Long-2.40-2.el7.noarch                                                                                                                                                   33/40 
  Verifying  : perl-File-Path-2.09-2.el7.noarch                                                                                                                                                     34/40 
  Verifying  : perl-threads-1.87-4.el7.x86_64                                                                                                                                                       35/40 
  Verifying  : perl-Filter-1.49-3.el7.x86_64                                                                                                                                                        36/40 
  Verifying  : perl-Text-ParseWords-3.29-4.el7.noarch                                                                                                                                               37/40 
  Verifying  : 1:mariadb-libs-5.5.56-2.el7.x86_64                                                                                                                                                   38/40 
  Verifying  : 1:mariadb-5.5.56-2.el7.x86_64                                                                                                                                                        39/40 
  Verifying  : 1:mariadb-libs-5.5.44-2.el7.x86_64                                                                                                                                                   40/40 

Installed:
  mariadb-server.x86_64 1:5.5.56-2.el7                                                                                                                                                                    

Dependency Installed:
  libaio.x86_64 0:0.3.109-13.el7                       mariadb.x86_64 1:5.5.56-2.el7                       perl.x86_64 4:5.16.3-292.el7                 perl-Carp.noarch 0:1.26-244.el7                 
  perl-Compress-Raw-Bzip2.x86_64 0:2.061-3.el7         perl-Compress-Raw-Zlib.x86_64 1:2.061-4.el7         perl-DBD-MySQL.x86_64 0:4.023-5.el7          perl-DBI.x86_64 0:1.627-4.el7                   
  perl-Data-Dumper.x86_64 0:2.145-3.el7                perl-Encode.x86_64 0:2.51-7.el7                     perl-Exporter.noarch 0:5.68-3.el7            perl-File-Path.noarch 0:2.09-2.el7              
  perl-File-Temp.noarch 0:0.23.01-3.el7                perl-Filter.x86_64 0:1.49-3.el7                     perl-Getopt-Long.noarch 0:2.40-2.el7         perl-HTTP-Tiny.noarch 0:0.033-3.el7             
  perl-IO-Compress.noarch 0:2.061-2.el7                perl-Net-Daemon.noarch 0:0.48-5.el7                 perl-PathTools.x86_64 0:3.40-5.el7           perl-PlRPC.noarch 0:0.2020-14.el7               
  perl-Pod-Escapes.noarch 1:1.04-292.el7               perl-Pod-Perldoc.noarch 0:3.20-4.el7                perl-Pod-Simple.noarch 1:3.28-4.el7          perl-Pod-Usage.noarch 0:1.63-3.el7              
  perl-Scalar-List-Utils.x86_64 0:1.27-248.el7         perl-Socket.x86_64 0:2.010-4.el7                    perl-Storable.x86_64 0:2.45-3.el7            perl-Text-ParseWords.noarch 0:3.29-4.el7        
  perl-Time-HiRes.x86_64 4:1.9725-3.el7                perl-Time-Local.noarch 0:1.2300-2.el7               perl-constant.noarch 0:1.27-2.el7            perl-libs.x86_64 4:5.16.3-292.el7               
  perl-macros.x86_64 4:5.16.3-292.el7                  perl-parent.noarch 1:0.225-244.el7                  perl-podlators.noarch 0:2.5.1-3.el7          perl-threads.x86_64 0:1.87-4.el7                
  perl-threads-shared.x86_64 0:1.43-6.el7             

Dependency Updated:
  mariadb-libs.x86_64 1:5.5.56-2.el7                                                                                                                                                                      

Complete!


```

# MariaDB Status and hostname

```

[root@ip-172-31-45-139 ~]# hostname -f
ip-172-31-45-139.ec2.internal

`mysql -u root -p -e "status;"`
+------------------------------------------+-------------------------+
| Variable_name                            | Value                   |
+------------------------------------------+-------------------------+
| Aborted_clients                          | 0                       |
| Aborted_connects                         | 9                       |
| Access_denied_errors                     | 0                       |
| Aria_pagecache_blocks_not_flushed        | 0                       |
| Aria_pagecache_blocks_unused             | 15737                   |
| Aria_pagecache_blocks_used               | 0                       |
| Aria_pagecache_read_requests             | 0                       |
| Aria_pagecache_reads                     | 0                       |
| Aria_pagecache_write_requests            | 0                       |
| Aria_pagecache_writes                    | 0                       |
| Aria_transaction_log_syncs               | 0                       |
| Binlog_commits                           | 3                       |
| Binlog_group_commits                     | 3                       |
| Binlog_snapshot_file                     | mysql_binary_log.000003 |
| Binlog_snapshot_position                 | 2172                    |
| Binlog_bytes_written                     | 0                       |
| Binlog_cache_disk_use                    | 0                       |
| Binlog_cache_use                         | 0                       |
| Binlog_stmt_cache_disk_use               | 0                       |
| Binlog_stmt_cache_use                    | 3                       |
| Busy_time                                | 0.000000                |
| Bytes_received                           | 137                     |
| Bytes_sent                               | 182                     |
| Com_admin_commands                       | 0                       |
| Com_alter_db                             | 0                       |
| Com_alter_db_upgrade                     | 0                       |
| Com_alter_event                          | 0                       |
| Com_alter_function                       | 0                       |
| Com_alter_procedure                      | 0                       |
| Com_alter_server                         | 0                       |
| Com_alter_table                          | 0                       |
| Com_alter_tablespace                     | 0                       |
| Com_analyze                              | 0                       |
| Com_assign_to_keycache                   | 0                       |
| Com_begin                                | 0                       |
| Com_binlog                               | 0                       |
| Com_call_procedure                       | 0                       |
| Com_change_db                            | 0                       |
| Com_change_master                        | 0                       |
| Com_check                                | 0                       |
| Com_checksum                             | 0                       |
| Com_commit                               | 0                       |
| Com_create_db                            | 0                       |
| Com_create_event                         | 0                       |
| Com_create_function                      | 0                       |
| Com_create_index                         | 0                       |
| Com_create_procedure                     | 0                       |
| Com_create_server                        | 0                       |
| Com_create_table                         | 0                       |
| Com_create_trigger                       | 0                       |
| Com_create_udf                           | 0                       |
| Com_create_user                          | 0                       |
| Com_create_view                          | 0                       |
| Com_dealloc_sql                          | 0                       |
| Com_delete                               | 0                       |
| Com_delete_multi                         | 0                       |
| Com_do                                   | 0                       |
| Com_drop_db                              | 0                       |
| Com_drop_event                           | 0                       |
| Com_drop_function                        | 0                       |
| Com_drop_index                           | 0                       |
| Com_drop_procedure                       | 0                       |
| Com_drop_server                          | 0                       |
| Com_drop_table                           | 0                       |
| Com_drop_trigger                         | 0                       |
| Com_drop_user                            | 0                       |
| Com_drop_view                            | 0                       |
| Com_empty_query                          | 0                       |
| Com_execute_sql                          | 0                       |
| Com_flush                                | 0                       |
| Com_grant                                | 0                       |
| Com_ha_close                             | 0                       |
| Com_ha_open                              | 0                       |
| Com_ha_read                              | 0                       |
| Com_help                                 | 0                       |
| Com_insert                               | 0                       |
| Com_insert_select                        | 0                       |
| Com_install_plugin                       | 0                       |
| Com_kill                                 | 0                       |
| Com_load                                 | 0                       |
| Com_lock_tables                          | 0                       |
| Com_optimize                             | 0                       |
| Com_preload_keys                         | 0                       |
| Com_prepare_sql                          | 0                       |
| Com_purge                                | 0                       |
| Com_purge_before_date                    | 0                       |
| Com_release_savepoint                    | 0                       |
| Com_rename_table                         | 0                       |
| Com_rename_user                          | 0                       |
| Com_repair                               | 0                       |
| Com_replace                              | 0                       |
| Com_replace_select                       | 0                       |
| Com_reset                                | 0                       |
| Com_resignal                             | 0                       |
| Com_revoke                               | 0                       |
| Com_revoke_all                           | 0                       |
| Com_rollback                             | 0                       |
| Com_rollback_to_savepoint                | 0                       |
| Com_savepoint                            | 0                       |
| Com_select                               | 1                       |
| Com_set_option                           | 0                       |
| Com_show_authors                         | 0                       |
| Com_show_binlog_events                   | 0                       |
| Com_show_binlogs                         | 0                       |
| Com_show_charsets                        | 0                       |
| Com_show_client_statistics               | 0                       |
| Com_show_collations                      | 0                       |
| Com_show_contributors                    | 0                       |
| Com_show_create_db                       | 0                       |
| Com_show_create_event                    | 0                       |
| Com_show_create_func                     | 0                       |
| Com_show_create_proc                     | 0                       |
| Com_show_create_table                    | 0                       |
| Com_show_create_trigger                  | 0                       |
| Com_show_databases                       | 0                       |
| Com_show_engine_logs                     | 0                       |
| Com_show_engine_mutex                    | 0                       |
| Com_show_engine_status                   | 0                       |
| Com_show_errors                          | 0                       |
| Com_show_events                          | 0                       |
| Com_show_fields                          | 0                       |
| Com_show_function_status                 | 0                       |
| Com_show_grants                          | 0                       |
| Com_show_index_statistics                | 0                       |
| Com_show_keys                            | 0                       |
| Com_show_master_status                   | 0                       |
| Com_show_open_tables                     | 0                       |
| Com_show_plugins                         | 0                       |
| Com_show_privileges                      | 0                       |
| Com_show_procedure_status                | 0                       |
| Com_show_processlist                     | 0                       |
| Com_show_profile                         | 0                       |
| Com_show_profiles                        | 0                       |
| Com_show_relaylog_events                 | 0                       |
| Com_show_slave_hosts                     | 0                       |
| Com_show_slave_status                    | 0                       |
| Com_show_status                          | 1                       |
| Com_show_storage_engines                 | 0                       |
| Com_show_table_statistics                | 0                       |
| Com_show_table_status                    | 0                       |
| Com_show_tables                          | 0                       |
| Com_show_triggers                        | 0                       |
| Com_show_user_statistics                 | 0                       |
| Com_show_variables                       | 0                       |
| Com_show_warnings                        | 0                       |
| Com_signal                               | 0                       |
| Com_slave_start                          | 0                       |
| Com_slave_stop                           | 0                       |
| Com_stmt_close                           | 0                       |
| Com_stmt_execute                         | 0                       |
| Com_stmt_fetch                           | 0                       |
| Com_stmt_prepare                         | 0                       |
| Com_stmt_reprepare                       | 0                       |
| Com_stmt_reset                           | 0                       |
| Com_stmt_send_long_data                  | 0                       |
| Com_truncate                             | 0                       |
| Com_uninstall_plugin                     | 0                       |
| Com_unlock_tables                        | 0                       |
| Com_update                               | 0                       |
| Com_update_multi                         | 0                       |
| Com_xa_commit                            | 0                       |
| Com_xa_end                               | 0                       |
| Com_xa_prepare                           | 0                       |
| Com_xa_recover                           | 0                       |
| Com_xa_rollback                          | 0                       |
| Com_xa_start                             | 0                       |
| Compression                              | OFF                     |
| Connections                              | 21                      |
| Cpu_time                                 | 0.000000                |
| Created_tmp_disk_tables                  | 0                       |
| Created_tmp_files                        | 6                       |
| Created_tmp_tables                       | 0                       |
| Delayed_errors                           | 0                       |
| Delayed_insert_threads                   | 0                       |
| Delayed_writes                           | 0                       |
| Empty_queries                            | 0                       |
| Executed_events                          | 0                       |
| Executed_triggers                        | 0                       |
| Feature_dynamic_columns                  | 0                       |
| Feature_fulltext                         | 0                       |
| Feature_gis                              | 0                       |
| Feature_locale                           | 0                       |
| Feature_subquery                         | 0                       |
| Feature_timezone                         | 0                       |
| Feature_trigger                          | 0                       |
| Feature_xml                              | 0                       |
| Flush_commands                           | 2                       |
| Handler_commit                           | 0                       |
| Handler_delete                           | 0                       |
| Handler_discover                         | 0                       |
| Handler_icp_attempts                     | 0                       |
| Handler_icp_match                        | 0                       |
| Handler_mrr_init                         | 0                       |
| Handler_mrr_key_refills                  | 0                       |
| Handler_mrr_rowid_refills                | 0                       |
| Handler_prepare                          | 0                       |
| Handler_read_first                       | 0                       |
| Handler_read_key                         | 0                       |
| Handler_read_last                        | 0                       |
| Handler_read_next                        | 0                       |
| Handler_read_prev                        | 0                       |
| Handler_read_rnd                         | 0                       |
| Handler_read_rnd_deleted                 | 0                       |
| Handler_read_rnd_next                    | 0                       |
| Handler_rollback                         | 0                       |
| Handler_savepoint                        | 0                       |
| Handler_savepoint_rollback               | 0                       |
| Handler_tmp_update                       | 0                       |
| Handler_tmp_write                        | 0                       |
| Handler_update                           | 0                       |
| Handler_write                            | 0                       |
| Innodb_adaptive_hash_cells               | 8850461                 |
| Innodb_adaptive_hash_hash_searches       | 0                       |
| Innodb_adaptive_hash_heap_buffers        | 0                       |
| Innodb_adaptive_hash_non_hash_searches   | 34                      |
| Innodb_background_log_sync               | 2                       |
| Innodb_buffer_pool_bytes_data            | 5029888                 |
| Innodb_buffer_pool_bytes_dirty           | 0                       |
| Innodb_buffer_pool_pages_data            | 307                     |
| Innodb_buffer_pool_pages_dirty           | 0                       |
| Innodb_buffer_pool_pages_flushed         | 317                     |
| Innodb_buffer_pool_pages_free            | 261835                  |
| Innodb_buffer_pool_pages_LRU_flushed     | 0                       |
| Innodb_buffer_pool_pages_made_not_young  | 0                       |
| Innodb_buffer_pool_pages_made_young      | 0                       |
| Innodb_buffer_pool_pages_misc            | 1                       |
| Innodb_buffer_pool_pages_old             | 0                       |
| Innodb_buffer_pool_pages_total           | 262143                  |
| Innodb_buffer_pool_read_ahead            | 0                       |
| Innodb_buffer_pool_read_ahead_evicted    | 0                       |
| Innodb_buffer_pool_read_ahead_rnd        | 0                       |
| Innodb_buffer_pool_read_requests         | 2576                    |
| Innodb_buffer_pool_reads                 | 0                       |
| Innodb_buffer_pool_wait_free             | 0                       |
| Innodb_buffer_pool_write_requests        | 2397                    |
| Innodb_checkpoint_age                    | 0                       |
| Innodb_checkpoint_max_age                | 868547913               |
| Innodb_checkpoint_target_age             | 841405791               |
| Innodb_current_row_locks                 | 0                       |
| Innodb_data_fsyncs                       | 19                      |
| Innodb_data_pending_fsyncs               | 0                       |
| Innodb_data_pending_reads                | 0                       |
| Innodb_data_pending_writes               | 0                       |
| Innodb_data_read                         | 0                       |
| Innodb_data_reads                        | 0                       |
| Innodb_data_writes                       | 1374                    |
| Innodb_data_written                      | 9132032                 |
| Innodb_dblwr_pages_written               | 143                     |
| Innodb_dblwr_writes                      | 2                       |
| Innodb_deadlocks                         | 0                       |
| Innodb_descriptors_memory                | 8000                    |
| Innodb_dict_tables                       | 8                       |
| Innodb_have_atomic_builtins              | ON                      |
| Innodb_history_list_length               | 0                       |
| Innodb_ibuf_discarded_delete_marks       | 0                       |
| Innodb_ibuf_discarded_deletes            | 0                       |
| Innodb_ibuf_discarded_inserts            | 0                       |
| Innodb_ibuf_free_list                    | 0                       |
| Innodb_ibuf_merged_delete_marks          | 0                       |
| Innodb_ibuf_merged_deletes               | 0                       |
| Innodb_ibuf_merged_inserts               | 0                       |
| Innodb_ibuf_merges                       | 0                       |
| Innodb_ibuf_segment_size                 | 2                       |
| Innodb_ibuf_size                         | 1                       |
| Innodb_log_waits                         | 0                       |
| Innodb_log_write_requests                | 3177                    |
| Innodb_log_writes                        | 5                       |
| Innodb_lsn_current                       | 1597945                 |
| Innodb_lsn_flushed                       | 1597945                 |
| Innodb_lsn_last_checkpoint               | 1597945                 |
| Innodb_master_thread_1_second_loops      | 2                       |
| Innodb_master_thread_10_second_loops     | 0                       |
| Innodb_master_thread_background_loops    | 3                       |
| Innodb_master_thread_main_flush_loops    | 3                       |
| Innodb_master_thread_sleeps              | 2                       |
| Innodb_max_trx_id                        | 771                     |
| Innodb_mem_adaptive_hash                 | 70824288                |
| Innodb_mem_dictionary                    | 17741428                |
| Innodb_mem_total                         | 4408213504              |
| Innodb_mutex_os_waits                    | 1                       |
| Innodb_mutex_spin_rounds                 | 32                      |
| Innodb_mutex_spin_waits                  | 5                       |
| Innodb_oldest_view_low_limit_trx_id      | 768                     |
| Innodb_os_log_fsyncs                     | 10                      |
| Innodb_os_log_pending_fsyncs             | 0                       |
| Innodb_os_log_pending_writes             | 0                       |
| Innodb_os_log_written                    | 1591808                 |
| Innodb_page_size                         | 16384                   |
| Innodb_pages_created                     | 307                     |
| Innodb_pages_read                        | 0                       |
| Innodb_pages_written                     | 317                     |
| Innodb_purge_trx_id                      | 0                       |
| Innodb_purge_undo_no                     | 0                       |
| Innodb_read_views_memory                 | 88                      |
| Innodb_row_lock_current_waits            | 0                       |
| Innodb_row_lock_time                     | 0                       |
| Innodb_row_lock_time_avg                 | 0                       |
| Innodb_row_lock_time_max                 | 0                       |
| Innodb_row_lock_waits                    | 0                       |
| Innodb_rows_deleted                      | 0                       |
| Innodb_rows_inserted                     | 0                       |
| Innodb_rows_read                         | 0                       |
| Innodb_rows_updated                      | 0                       |
| Innodb_s_lock_os_waits                   | 7                       |
| Innodb_s_lock_spin_rounds                | 210                     |
| Innodb_s_lock_spin_waits                 | 7                       |
| Innodb_truncated_status_writes           | 0                       |
| Innodb_x_lock_os_waits                   | 0                       |
| Innodb_x_lock_spin_rounds                | 0                       |
| Innodb_x_lock_spin_waits                 | 0                       |
| Key_blocks_not_flushed                   | 0                       |
| Key_blocks_unused                        | 26788                   |
| Key_blocks_used                          | 4                       |
| Key_blocks_warm                          | 0                       |
| Key_read_requests                        | 12                      |
| Key_reads                                | 4                       |
| Key_write_requests                       | 16                      |
| Key_writes                               | 5                       |
| Last_query_cost                          | 0.000000                |
| Max_used_connections                     | 1                       |
| Not_flushed_delayed_rows                 | 0                       |
| Open_files                               | 25                      |
| Open_streams                             | 0                       |
| Open_table_definitions                   | 34                      |
| Open_tables                              | 27                      |
| Opened_files                             | 94                      |
| Opened_table_definitions                 | 0                       |
| Opened_tables                            | 0                       |
| Opened_views                             | 0                       |
| Performance_schema_cond_classes_lost     | 0                       |
| Performance_schema_cond_instances_lost   | 0                       |
| Performance_schema_file_classes_lost     | 0                       |
| Performance_schema_file_handles_lost     | 0                       |
| Performance_schema_file_instances_lost   | 0                       |
| Performance_schema_locker_lost           | 0                       |
| Performance_schema_mutex_classes_lost    | 0                       |
| Performance_schema_mutex_instances_lost  | 0                       |
| Performance_schema_rwlock_classes_lost   | 0                       |
| Performance_schema_rwlock_instances_lost | 0                       |
| Performance_schema_table_handles_lost    | 0                       |
| Performance_schema_table_instances_lost  | 0                       |
| Performance_schema_thread_classes_lost   | 0                       |
| Performance_schema_thread_instances_lost | 0                       |
| Prepared_stmt_count                      | 0                       |
| Qcache_free_blocks                       | 1                       |
| Qcache_free_memory                       | 67091120                |
| Qcache_hits                              | 0                       |
| Qcache_inserts                           | 0                       |
| Qcache_lowmem_prunes                     | 0                       |
| Qcache_not_cached                        | 10                      |
| Qcache_queries_in_cache                  | 0                       |
| Qcache_total_blocks                      | 1                       |
| Queries                                  | 36                      |
| Questions                                | 2                       |
| Rows_read                                | 0                       |
| Rows_sent                                | 1                       |
| Rows_tmp_read                            | 0                       |
| Rpl_status                               | AUTH_MASTER             |
| Select_full_join                         | 0                       |
| Select_full_range_join                   | 0                       |
| Select_range                             | 0                       |
| Select_range_check                       | 0                       |
| Select_scan                              | 0                       |
| Slave_heartbeat_period                   | 0.000                   |
| Slave_open_temp_tables                   | 0                       |
| Slave_received_heartbeats                | 0                       |
| Slave_retried_transactions               | 0                       |
| Slave_running                            | OFF                     |
| Slow_launch_threads                      | 0                       |
| Slow_queries                             | 0                       |
| Sort_merge_passes                        | 0                       |
| Sort_range                               | 0                       |
| Sort_rows                                | 0                       |
| Sort_scan                                | 0                       |
| Ssl_accept_renegotiates                  | 0                       |
| Ssl_accepts                              | 0                       |
| Ssl_callback_cache_hits                  | 0                       |
| Ssl_cipher                               |                         |
| Ssl_cipher_list                          |                         |
| Ssl_client_connects                      | 0                       |
| Ssl_connect_renegotiates                 | 0                       |
| Ssl_ctx_verify_depth                     | 0                       |
| Ssl_ctx_verify_mode                      | 0                       |
| Ssl_default_timeout                      | 0                       |
| Ssl_finished_accepts                     | 0                       |
| Ssl_finished_connects                    | 0                       |
| Ssl_session_cache_hits                   | 0                       |
| Ssl_session_cache_misses                 | 0                       |
| Ssl_session_cache_mode                   | NONE                    |
| Ssl_session_cache_overflows              | 0                       |
| Ssl_session_cache_size                   | 0                       |
| Ssl_session_cache_timeouts               | 0                       |
| Ssl_sessions_reused                      | 0                       |
| Ssl_used_session_cache_entries           | 0                       |
| Ssl_verify_depth                         | 0                       |
| Ssl_verify_mode                          | 0                       |
| Ssl_version                              |                         |
| Subquery_cache_hit                       | 0                       |
| Subquery_cache_miss                      | 0                       |
| Syncs                                    | 4                       |
| Table_locks_immediate                    | 66                      |
| Table_locks_waited                       | 0                       |
| Tc_log_max_pages_used                    | 0                       |
| Tc_log_page_size                         | 0                       |
| Tc_log_page_waits                        | 0                       |
| Threadpool_idle_threads                  | 0                       |
| Threadpool_threads                       | 0                       |
| Threads_cached                           | 0                       |
| Threads_connected                        | 1                       |
| Threads_created                          | 1                       |
| Threads_running                          | 1                       |
| Uptime                                   | 875                     |
| Uptime_since_flush_status                | 875                     |
+------------------------------------------+-------------------------+
413 rows in set (0.00 sec)

`mysql -u root  -p -e "show databases;"`
show databases;
+--------------------+
| Database           |
+--------------------+
| information_schema |
| hive               |
| hue                |
| mysql              |
| oozie              |
| performance_schema |
| rman               |
| scm                |
| sentry             |
+--------------------+
9 rows in set (0.00 sec)

``` 

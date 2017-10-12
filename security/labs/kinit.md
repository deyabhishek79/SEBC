# kinit command

```

[root@ip-172-31-41-199 ~]# kadmin.local
Authenticating as principal hadoopuser/admin@DEYABHISHEK79.COM with password.
kadmin.local:  addprinc deyabhishek79@DEYABHISHEK79.COM
WARNING: no policy specified for deyabhishek79@DEYABHISHEK79.COM; defaulting to no policy
Enter password for principal "deyabhishek79@DEYABHISHEK79.COM": 
Re-enter password for principal "deyabhishek79@DEYABHISHEK79.COM": 
Principal "deyabhishek79@DEYABHISHEK79.COM" created.
kadmin.local:  exit
[root@ip-172-31-41-199 ~]# su deyabhishek79
[deyabhishek79@ip-172-31-41-199 root]$ kinit deyabhishek79
Password for deyabhishek79@DEYABHISHEK79.COM: 
[deyabhishek79@ip-172-31-41-199 root]$ cd
[deyabhishek79@ip-172-31-41-199 ~]$ hadoop fs -ls /user/deyabhishek79
Found 3 items
drwx------   - deyabhishek79 supergroup          0 2017-10-11 15:45 /user/deyabhishek79/.staging
drwxr-xr-x   - deyabhishek79 supergroup          0 2017-10-11 03:16 /user/deyabhishek79/precious
drwxr-xr-x   - deyabhishek79 supergroup          0 2017-10-11 15:46 /user/deyabhishek79/results

```

# klist command

```

[root@ip-172-31-41-199 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: hadoopuser@DEYABHISHEK79.COM

Valid starting       Expires              Service principal
10/11/2017 20:41:35  10/12/2017 20:41:35  krbtgt/DEYABHISHEK79.COM@DEYABHISHEK79.COM
	renew until 10/18/2017 20:41:35
```


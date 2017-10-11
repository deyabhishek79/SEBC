# Upgrade Cloudera Manager API Calls

## Report the latest available version of the API

```
[root@ip-172-31-41-199 ~]# curl -u 'deyabhishek79:cloudera' "http://52.90.50.48:7180/api/version"
v18

```

## Report the CM version

```
[root@ip-172-31-41-199 ~]# curl -u 'deyabhishek79:cloudera' "http://52.90.50.48:7180/api/v14/cm/version"
{
  "version" : "5.13.0",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20171002-1719",
  "gitHash" : "bd657e597e6743c458ee2c9aabe808b7c972981c",
  "snapshot" : false
}

```

## List all CM users

```
[root@ip-172-31-41-199 ~]# curl -u 'deyabhishek79:cloudera' "http://52.90.50.48:7180/api/v14/users"
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "deyabhishek79",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CONFIGURATOR" ]
  } ]
}

```

## Report the database server in use by CM

```

[root@ip-172-31-41-199 ~]# curl -u 'deyabhishek79:cloudera' "http://52.90.50.48:7180/api/v14/cm/scmDbInfo"
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}

```


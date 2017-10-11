# Use the API

## Stop the Hive Service
```
curl -u 'deyabhishek79:cloudera' -X POST "http://52.90.50.48:7180/api/v12/clusters/deyabhishek79/services/hive/commands/stop"

[root@ip-172-31-41-199 ~]# curl -u 'deyabhishek79:cloudera' -X POST "http://52.90.50.48:7180/api/v12/clusters/deyabhishek79/services/hive/commands/stop"
{
  "id" : 439,
  "name" : "Stop",
  "startTime" : "2017-10-11T17:59:32.259Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
```

## Check the status of Hive Service stopped
```
[root@ip-172-31-41-199 ~]# curl -u 'deyabhishek79:cloudera' -X GET "http://52.90.50.48:7180/api/v12/clusters/deyabhishek79/services/hive"
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-41-199.ec2.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-41-199.ec2.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STOPPED",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "STOPPED"
}
```
## Restart the Hive Service
```
[root@ip-172-31-41-199 ~]# curl -u 'deyabhishek79:cloudera' -X POST "http://52.90.50.48:7180/api/v12/clusters/deyabhishek79/serviceshive/commands/start"
{
  "id" : 443,
  "name" : "Start",
  "startTime" : "2017-10-11T18:00:31.288Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}

```
## Check the status of Hive service just started

```
[root@ip-172-31-41-199 ~]# curl -u 'deyabhishek79:cloudera' -X GET "http://52.90.50.48:7180/api/v12/clusters/deyabhishek79/services/ive"
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-41-199.ec2.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-41-199.ec2.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTING",
  "healthSummary" : "DISABLED",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "DISABLED",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "DISABLED",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "STARTING"
}
```

## Check the status of Hive Service
```
[root@ip-172-31-41-199 ec2-user]# curl -u 'deyabhishek79:cloudera' -X GET "http://52.90.50.48:7180/api/v12/clusters/deyabhishek79/services/hive"
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-41-199.ec2.internal:7180/cmf/serviceRedirect/hive",
  "roleInstancesUrl" : "http://ip-172-31-41-199.ec2.internal:7180/cmf/serviceRedirect/hive/instances",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD",
    "suppressed" : false
  } ],
  "configStalenessStatus" : "FRESH",
  "clientConfigStalenessStatus" : "FRESH",
  "maintenanceMode" : false,
  "maintenanceOwners" : [ ],
  "displayName" : "Hive",
  "entityStatus" : "GOOD_HEALTH"
}

```

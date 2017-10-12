# Distcp between Secure Clusters in Distinct Kerberos Realms (Theoritical Notes)

## Specify the Destination Parameters in krb5.conf
### Edit the krb5.conf file on the client (where the distcp job will be submitted) to include the destination hostname and realm.
```
[realms]
HADOOP.QA.domain.COM = { kdc = kdc.domain.com:88 admin_server = admin.test.com:749
default_domain = domain.com supported_enctypes = arcfour-hmac:normal des-cbc-crc:normal
des-cbc-md5:normal des:normal des:v4 des:norealm des:onlyrealm des:afs3 } 

[domain_realm]
.domain.com = HADOOP.test.domain.COM
domain.com = HADOOP.test.domain.COM
test03.domain.com = HADOOP.QA.domain.COM

```
## Configure HDFS RPC Protection and Acceptable Kerberos Principal Patterns

```
Set the hadoop.rpc.protection property to authentication in both clusters. You can modify this property either in hdfs-site.xml, or using Cloudera Manager as follows:
Open the Cloudera Manager Admin Console.
Go to the HDFS service.
Click the Configuration tab.
Select Scope > HDFS-1 (Service-Wide).
Select Category > Security.
Locate the Hadoop RPC Protection property and select authentication.
Click Save Changes to commit the changes.
The following steps are not required if the two realms are already set up to trust each other, or have the same principal pattern. However, this isn't usually the case.

Set the dfs.namenode.kerberos.principal.pattern property to * to allow distcp irrespective of the principal patterns of the source and destination clusters. You can modify this property either in hdfs-site.xml on both clusters, or using Cloudera Manager as follows:
Open the Cloudera Manager Admin Console.
Go to the HDFS service.
Click the Configuration tab.
Select Scope > Gateway.
Select Category > Advanced.
Edit the HDFS Client Advanced Configuration Snippet (Safety Valve) for hdfs-site.xml property to add:
<property>
  <name>dfs.namenode.kerberos.principal.pattern</name>
  <value>*</value>
</property>
Click Save Changes to commit the changes.
```

## (If TLS/SSL is enabled) Specify Truststore Properties

```
The following properties must be configured in the ssl-client.xml file on the client submitting the distcp job to establish trust between the target and destination clusters.
<property>
<name>ssl.client.truststore.location</name>
<value>path_to_truststore</value>
</property>

<property>
<name>ssl.client.truststore.password</name>
<value>XXXXXX</value>
</property>

<property>
<name>ssl.client.truststore.type</name>
<value>jks</value>
</property>
```

## Set HADOOP_CONF to the Destination Cluster
### Set the HADOOP_CONF path to be the destination environment. If you are not using HFTP, set the HADOOP_CONF path to the source environment instead.

## Launch Distcp

```
Kinit on the client and launch the distcp job.
hadoop distcp hdfs://test01.domain.com:8020/user/alice hdfs://test02.domain.com:8020/user/alice
If launching distcp fails, force Kerberos to use TCP instead of UDP by adding the following parameter to the krb5.conf file on the client.
[libdefaults]
udp_preference_limit = 1
```

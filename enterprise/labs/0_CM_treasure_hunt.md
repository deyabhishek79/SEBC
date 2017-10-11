# What is ubertask optimization?

```
It is a performance optimization which involves whether to enable the small-jobs "ubertask" optimization, which runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings.

API- mapreduce_job_ubertask_enabled

```

# Where in CM is the Kerberos Security Realm value displayed?

```

In the Cloudera Manager Admin Console, select Administration > Settings.
Click the Security category, and enter the Kerberos realm for the cluster in the Kerberos Security Realm field (for example, YOUR-LOCAL-REALM.COM or YOUR-SUB-REALM.YOUR-LOCAL-REALM.COM) that you configured in the krb5.conf file.
Click Save Changes.

```

# Which CDH service(s) host a property for enabling Kerberos authentication?

```
To start the Kerberos wizard:
Go to the Cloudera Manager Admin Console and click  to the right of the cluster for which you want to enable Kerberos authentication.
Select Enable Kerberos.

https://www.cloudera.com/documentation/enterprise/5-9-x/topics/cm_sg_s4_kerb_wizard.html#xd_583c10bfdbd326ba--6eed2fb8-14349d04bee--7713

```

# How do you upgrade the CM agents?

```
One should go to All Hosts, Re-run upgrade wizard

1.Log in to the Cloudera Manager Admin Console.
2.Upgrade hosts using one of the following methods:
a.Select Yes, I would like to upgrade the Cloudera Manager Agent packages now and click Continue.
b.Select the release of the Cloudera Manager Agent to install. Normally, this is the Matched Release for this Cloudera Manager Server. However, if you used a custom repository (instead of archive.cloudera.com) for the Cloudera Manager server, select Custom Repository and provide the required information. The custom repository allows you to use an alternative location, but that location must contain the matched Agent version.
c.Click Continue. The JDK Installation Options page displays.Leave Install Oracle Java SE Development Kit (JDK) checked to allow Cloudera Manager to install the JDK on each cluster host, or uncheck if you plan to install it yourself.
If local laws permit you to deploy unlimited strength encryption, and you are running a secure cluster, check the Install Java Unlimited Strength Encryption Policy Files checkbox. Click Continue. d.Specify credentials and initiate Agent installation:
Select root or enter the username for an account that has password-less sudo permission.
Select an authentication method:
If you choose password authentication, enter and confirm the password.
If you choose public-key authentication, provide a passphrase and path to the required key files.
You can specify an alternate SSH port. The default value is 22.
You can specify the maximum number of host installations to run at once. The default value is 10.
e.Click Continue. The Cloudera Manager Agent packages and optionally the JDK are installed.
f.Click Continue. The Host Inspector runs to inspect your managed hosts for correct versions and configurations. If there are problems, you can make changes and then rerun the inspector. When you are satisfied with the inspection results, click Continue.

3.Click Finish.
4.If you are upgrading from Cloudera Manager 5.0 and are using an external database for Cloudera Navigator, the Database Setup page displays. Configure database settings:
5.Enter the database host, database type, database name, username, and password for the database that you created when you set up the database.
6.Click Test Connection to confirm that Cloudera Manager can communicate with the database using the information you have supplied. If the test succeeds in all cases, click Continue; otherwise check and correct the information you have provided for the database and then try the test again. (For some servers, if you are using the embedded database, you will see a message saying the database will be created at a later step in the installation process.)
7.The Review Changes page displays. Review the configuration changes to be applied and click Continue. The Upgrade wizard displays a dialog box allowing you to choose whether to restart the Cloudera Management Service.
8.Click Continue. If you kept the default selection, the Upgrade wizard restarts the Cloudera Management Service.
9.Click Finish. The Home > Status tab displays.

Details on agents can be found at :
https://www.cloudera.com/documentation/enterprise/5-9-x/topics/cm_ag_agent_config.html

```

# Give the tsquery statement used to chart Hue's CPU utilization?

```
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName="hue"

``` 

# Name all the roles that make up the Hive service

```

There are two Hive service roles:
Hive Metastore Server. This role manages the Metastore process when Hive is configured with a Remote Metastore. You are strongly encouraged to read Configuring the Hive Metastore (CDH 4) or Configuring the Hive Metastore (CDH 5).
HiveServer2 - supports a Thrift API tailored for JDBC and ODBC clients, Kerberos authentication, and multi-client concurrency. There is also a CLI for HiveServer2 named Beeline. Cloudera recommends that you deploy HiveServer2 whenever possible. You can use the original HiveServer, and run it concurrently with HiveServer2. However, Cloudera Manager does not manage HiveServer, so you must configure and manage it outside Cloudera Manager. See HiveServer2 documentation (CDH 4) or HiveServer2 documentation (CDH 5) for more information.

```

# What steps must be completed before integrating Cloudera Manager with Kerberos?

```
Prerequisites - These instructions assume you know how to install and configure Kerberos, you already have a working Kerberos key distribution center (KDC) and realm setup, and that you've installed the following Kerberos client packages on all cluster hosts and hosts that will be used to access the cluster, depending on the OS in use.
Packages to be Installed
RHEL/CentOS 5, RHEL/CentOS 6	
openldap-clients on the Cloudera Manager Server host
krb5-workstation, krb5-libs on ALL hosts

Furthermore, Oozie and Hue require that the realm support renewable tickets. Cloudera Manager supports setting up kerberized clusters with MIT KDC and Active Directory.

If you want to integrate Kerberos directly with Active Directory, ensure you have support from your AD administration team to do so. This includes any future support required to troubleshoot issues such as Kerberos TGT/TGS ticket renewal, access to KDC logs for debugging and so on.


ALL STEPS:

1. Install Cloudera Manager and CDH
2. If You are Using AES-256 Encryption, Install the JCE Policy File
If you are using CentOS or RHEL 5.5 or higher, which use AES-256 encryption by default for tickets, you must install the Java Cryptography Extension (JCE) Unlimited Strength Jurisdiction Policy File on all cluster and Hadoop user hosts. There are 2 ways to do this:
In the Cloudera Manager Admin Console, navigate to the Hosts page. Both, the Add New Hosts to Cluster wizard and the Re-run Upgrade Wizard will give you the option to have Cloudera Manager install the JCE Policy file for you.
You can follow the JCE Policy File installation instructions in the README.txt file included in the jce_policy-x.zip file.
Alternatively, you can configure Kerberos to not use AES-256 by removing aes256-cts:normal from the supported_enctypes field of the kdc.conf or krb5.conf file. Note that after changing the kdc.conf file, you'll need to restart both the KDC and the kadmin server for those changes to take affect. You may also need to recreate or change the password of the relevant principals, including potentially the Ticket Granting Ticket principal (for example, krbtgt/EXAMPLE.COM@EXAMPLE.COM). If AES-256 is still used after all of those steps, it's because the aes256-cts:normal setting existed when the Kerberos database was created. To fix this, create a new Kerberos database and then restart both the KDC and the kadmin server.

To verify the type of encryption used in your cluster:
On the local KDC host, type this command in the kadmin.local or kadmin shell to create a test principal:
kadmin:  addprinc test
On a cluster host, type this command to start a Kerberos session as the test principal:
$ kinit test 
After successfully running the previous command, type this command to view the encryption type in use:
$ klist -e 
If AES is being used, output like the following is displayed after you type the klist command (note that AES-256 is included in the output):

Ticket cache: FILE:/tmp/krb5cc_0
Default principal: test@EXAMPLE.COM
Valid starting     Expires            Service principal
05/19/11 13:25:04  05/20/11 13:25:04  krbtgt/EXAMPLE.COM@EXAMPLE.COM
    Etype (skey, tkt): AES-256 CTS mode with 96-bit SHA-1 HMAC, AES-256 CTS mode with 96-bit SHA-1 HMAC 

3. Get or Create a Kerberos Principal for the Cloudera Manager Server
In order to create and deploy the host principals and keytabs on your cluster, the Cloudera Manager Server must have the correct Kerberos principal. Specifically, the Cloudera Manager Server must have a Kerberos principal that has administrator privileges. Typically, principals with the second component of admin in the principal name (for example, username/admin@EXAMPLE.COM) have administrator privileges. This is why admin is shown in the following instructions and examples.

To get or create the Kerberos principal for the Cloudera Manager Server, you can do either of the following:
Ask your Kerberos administrator to create a Kerberos administrator principal for the Cloudera Manager Server.
Create the Kerberos principal for the Cloudera Manager Server yourself by using the following instructions in this step.
Creating the Cloudera Manager Principal
If you are using Active Directory
Create an Organizational Unit (OU) in your AD where all the principals used by your CDH cluster will reside.
Add a new AD user, for example, <username>@EXAMPLE.COM. The password for this user should be set to never expire.
Use AD's Delegate Control wizard to allow this new user to Create, Delete and Manage User Accounts.
If you are using MIT KDC
The instructions in this section illustrate an example of creating the Cloudera Manager Server principal for MIT Kerberos. (If you are using another version of Kerberos, refer to your Kerberos documentation for instructions.)
Note: If you are running kadmin and the Kerberos Key Distribution Center (KDC) on the same host, use kadmin.local in the following steps. If the Kerberos KDC is running on a remote host, you must use kadmin instead of kadmin.local.
In the kadmin.local or kadmin shell, type the following command to create the Cloudera Manager Server principal, replacing EXAMPLE.COM with the name of your realm:
kadmin:  addprinc -pw <Password> cloudera-scm/admin@EXAMPLE.COM

4. Import KDC Account Manager Credentials
In the Cloudera Manager Admin Console, select Administration > Security.
Go to the Kerberos Credentials tab and click Import Kerberos Account Manager Credentials.
In the Import Kerberos Account Manager Credentials dialog box, enter the username and password for the user that can create principals for CDH cluster in the KDC. This is the user/principal you created in Step 3: Get or Create a Kerberos Principal for the Cloudera Manager Server. Cloudera Manager encrypts the username and password into a keytab and uses it as needed to create new principals.
Note: The username entered should have the realm portion in upper-case only as shown in the example in the UI.
Click Close when complete.


5.Configure the Kerberos Default Realm in the Cloudera Manager Admin Console
Minimum Required Role: Full Administrator

Important: Hadoop requires a default Kerberos realm be configured in the libdefaults property in the /etc/krb5.conf file on every host in the cluster:
[libdefaults]
default_realm = EXAMPLE.COM
In the Cloudera Manager Admin Console, select Administration > Settings.
Under the Category filter, click Kerberos.
In the Kerberos Security Realm field, enter the name of your default Kerberos realm. Use the same realm name configured in the /etc/krb5.conf file. For example, EXAMPLE.COM:


Click Save Changes.

6. Stop All Services

7. Enable Hadoop Security
Minimum Required Role: Configurator (also provided by Cluster Administrator, Full Administrator)

To enable Hadoop security for the cluster, you enable it on an HDFS service. After you do so, the Cloudera Manager Server automatically enables Hadoop security on the MapReduce and YARN services associated with that HDFS service.

Go to the HDFS Service > Configuration tab.
In the Search field, type Hadoop Secure to show the Hadoop security properties (found under the Service-Wide > Security category).
Click the value for the Hadoop Secure Authentication property and select the kerberos option to enable Hadoop security on the selected HDFS service.
Click the value for the Hadoop Secure Authorization property and select the checkbox to enable service-level authorization on the selected HDFS service. You can specify comma-separated lists of users and groups authorized to use Hadoop services or perform admin operations using the following properties under the Service-Wide > Security section:
Authorized Users: Comma-separated list of users authorized to use Hadoop services.
Authorized Groups: Comma-separated list of groups authorized to use Hadoop services.
Authorized Admin Users: Comma-separated list of users authorized to perform admin operations on Hadoop.
Authorized Admin Groups: Comma-separated list of groups authorized to perform admin operations on Hadoop.
Important: For Cloudera Manager's Monitoring services to work, the hue user should always be added as an authorized user.
In the Search field, type DataNode Transceiver to find the DataNode Transceiver Port property.
Click the value for the DataNode Transceiver Port property and specify a privileged port number (below 1024). Cloudera recommends 1004.
Note: If there is more than one DataNode Role Group, you must specify a privileged port number for each DataNode Transceiver Port property.
In the Search field, type DataNode HTTP to find the DataNode HTTP Web UI Port property and specify a privileged port number (below 1024). Cloudera recommends 1006.
Note: These port numbers for the two DataNode properties must be below 1024 to provide part of the security mechanism to make it impossible for a user to run a MapReduce task that impersonates a DataNode. The port numbers for the NameNode and Secondary NameNode can be anything you want, but the default port numbers are good ones to use.
In the Search field type Data Directory Permissions to find the DataNode Data Directory Permissions property.
Reset the value for the DataNode Data Directory Permissions property to the default value of 700 if not already set to that.
Make sure you have changed the DataNode Transceiver Port, DataNode Data Directory Permissions and DataNode HTTP Web UI Port properties for every DataNode role group.
Click Save Changes to save the configuration settings.
To enable ZooKeeper security:

Go to the ZooKeeper Service > Configuration tab and click View and Edit.
Click the value for Enable Kerberos Authentication property.
Click Save Changes to save the configuration settings.
To enable HBase security:

Go to the HBase Service > Configuration tab and click View and Edit.
In the Search field, type HBase Secure to show the Hadoop security properties (found under the Service-Wide > Security category).
Click the value for the HBase Secure Authorization property and select the checkbox to enable authorization on the selected HBase service.
Click the value for the HBase Secure Authentication property and select kerberos to enable authorization on the selected HBase service.
Click Save Changes to save the configuration settings.
(CDH 4.3 or later) To enable Solr security:
Go to the Solr Service > Configuration tab and click View and Edit.
In the Search field, type Solr Secure to show the Solr security properties (found under the Service-Wide > Security category).
Click the value for the Solr Secure Authentication property and select kerberos to enable authorization on the selected Solr service.
Click Save Changes to save the configuration settings.

8. Wait for the Generate Credentials Command to Finish
Minimum Required Role: Configurator (also provided by Cluster Administrator, Full Administrator)

After you enable security for any of the services in Cloudera Manager, a command called Generate Credentials will be triggered automatically. You can watch the progress of the command on the top right corner of the screen that shows the running commands. Wait for this command to finish (indicated by a grey box containing "0" in it).

9. Enable Hue to Work with Hadoop Security using Cloudera Manager

10. Start all Services
```

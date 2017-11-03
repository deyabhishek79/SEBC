# The first line of your CM server log

```
head -1 /var/log/cloudera-scm-server/cloudera-scm-server.log 
2017-11-03 16:15:57,271 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties, -Dfile.encoding=UTF-8, -Dcmf.root.logger=INFO,LOGFILE, -Dcmf.log.dir=/var/log/cloudera-scm-server, -Dcmf.log.file=cloudera-scm-server.log, -Dcmf.jetty.threshhold=WARN, -Dcmf.schema.dir=/usr/share/cmf/schema, -Djava.awt.headless=true, -Djava.net.preferIPv4Stack=true, -Dpython.home=/usr/share/cmf/python, -XX:+UseConcMarkSweepGC, -XX:+UseParNewGC, -XX:+HeapDumpOnOutOfMemoryError, -Xmx2G, -XX:MaxPermSize=256m, -XX:+HeapDumpOnOutOfMemoryError, -XX:HeapDumpPath=/tmp, -XX:OnOutOfMemoryError=kill -9 %p], Args: [], Version: 5.13.0 (#55 built by jenkins on 20171002-1719 git: bd657e597e6743c458ee2c9aabe808b7c972981c)

```

# Started Jetty server

```
2017-11-03 16:17:01,947 INFO SearchRepositoryManager-0:com.cloudera.server.web.cmf.search.components.SearchRepositoryManager: Constructing repo:2017-11-03T20:17:01.947Z
2017-11-03 16:17:02,413 INFO WebServerImpl:org.mortbay.log: jetty-6.1.26.cloudera.4
2017-11-03 16:17:02,415 INFO WebServerImpl:org.mortbay.log: Started SelectChannelConnector@0.0.0.0:7180
2017-11-03 16:17:02,415 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.
```

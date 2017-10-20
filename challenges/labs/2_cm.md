List repo
````
ls /etc/yum.repos.d/
CentOS-Base.repo  CentOS-Debuginfo.repo  CentOS-Media.repo    CentOS-Vault.repo  mysql-community.repo         mysql-community-source.repo
CentOS-CR.repo    CentOS-fasttrack.repo  CentOS-Sources.repo  cm5.repo
````

cloudera manager prepare database:
````
[root@ip-172-31-27-185 ~]# /usr/share/cmf/schema/scm_prepare_database.sh -h ip-172-31-19-162.eu-central-1.compute.internal mysql scm scm azerty
JAVA_HOME=/usr/java/jdk1.8.0_144
Verifying that we can write to /etc/cloudera-scm-server
Creating SCM configuration file in /etc/cloudera-scm-server
Executing:  /usr/java/jdk1.8.0_144/bin/java -cp /usr/share/java/mysql-connector-java.jar:/usr/share/java/oracle-connector-java.jar:/usr/share/cmf/schema/../lib/* com.cloudera.enterprise.dbutil.DbCommandExecutor /etc/cloudera-scm-server/db.properties com.cloudera.cmf.db.
[                          main] DbCommandExecutor              INFO  Successfully connected to database.
All done, your SCM database is configured correctly!

````

The first line from your server log
````
[root@ip-172-31-27-185 ~]# head /var/log/cloudera-scm-server/cloudera-scm-server.log
2017-10-20 08:29:35,474 INFO main:com.cloudera.server.cmf.Main: Starting SCM Server. JVM Args: [-Dlog4j.configuration=file:/etc/cloudera-scm-server/log4j.properties, -Dfile.encoding=UTF-8, -Dcmf.root.logger=INFO,LOGFILE, -Dcmf.log.dir=/var/log/cloudera-scm-server, -Dcmf.log.file=cloudera-scm-server.log, -Dcmf.jetty.threshhold=WARN, -Dcmf.schema.dir=/usr/share/cmf/schema, -Djava.awt.headless=true, -Djava.net.preferIPv4Stack=true, -Dpython.home=/usr/share/cmf/python, -XX:+UseConcMarkSweepGC, -XX:+UseParNewGC, -XX:+HeapDumpOnOutOfMemoryError, -Xmx2G, -XX:MaxPermSize=256m, -XX:+HeapDumpOnOutOfMemoryError, -XX:HeapDumpPath=/tmp, -XX:OnOutOfMemoryError=kill -9 %p], Args: [], Version: 5.9.3 (#6 built by jenkins on 20170627-1506 git: 23506bb4e114dd460bdac64c57a672e6be631907)

````

The log line that contains the phrase "Started Jetty server"
````
2017-10-20 08:30:40,138 INFO WebServerImpl:com.cloudera.server.cmf.WebServerImpl: Started Jetty server.
````
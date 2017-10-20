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

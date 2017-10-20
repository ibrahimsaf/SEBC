````
[root@ip-172-31-19-162 ~]# kinit -kt /run/cloudera-scm-agent/process/79-hive-HIVEMETASTORE/hive.keytab hive/ip-172-31-19-162.eu-central-1.compute.internal@IBRAHIMSAF.CO.UK
[root@ip-172-31-19-162 ~]# beeline
Beeline version 1.1.0-cdh5.9.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-19-162.eu-central-1.compute.internal@IBRAHIMSAF.CO.UK
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-19-162.eu-central-1.compute.internal@IBRAHIMSAF.CO.UK
Connected to: Apache Hive (version 1.1.0-cdh5.9.3)
Driver: Hive JDBC (version 1.1.0-cdh5.9.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default>


````
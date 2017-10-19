```
[root@ip-172-31-7-61 ~]# kinit ibrahimsaf/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM
Password for ibrahimsaf/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM:


[root@ip-172-31-7-61 ~]# klist
Ticket cache: FILE:/tmp/krb5cc_0
Default principal: ibrahimsaf/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM

Valid starting       Expires              Service principal
10/19/2017 11:53:52  10/20/2017 11:53:52  krbtgt/IBRAHIM.COM@IBRAHIM.COM
        renew until 10/26/2017 11:53:52





[root@ip-172-31-7-61 ~]# hostname -f
ip-172-31-7-61.eu-central-1.compute.internal


[root@ip-172-31-7-61 ~]# beeline
^[[ABeeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM: ibrahimsaf
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171019115757_25231984-bdf1-4de0-840e-18c82c90c6ca): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019115757_25231984-bdf1-4de0-840e-18c82c90c6ca); Time taken: 0.206 seconds
INFO  : Executing command(queryId=hive_20171019115757_25231984-bdf1-4de0-840e-18c82c90c6ca): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019115757_25231984-bdf1-4de0-840e-18c82c90c6ca); Time taken: 0.121 seconds
INFO  : OK
+-----------+--+
| tab_name  |
+-----------+--+
+-----------+--+
No rows selected (1.503 seconds)

```

````
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

````

I have imported only too tables in Hive, george can see all tables (lab_table and sample_07):
````
[root@ip-172-31-7-61 ~]# kdestroy
[root@ip-172-31-7-61 ~]# kinit george
Password for george@IBRAHIM.COM:
[root@ip-172-31-7-61 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM: georges*
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM: [root@ip-172-31-7-61 ~]#
[root@ip-172-31-7-61 ~]#
[root@ip-172-31-7-61 ~]# beeline
Beeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM
scan complete in 3ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM: george
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171019124444_5f8410f3-7e88-4c6c-99cb-4e3b1aff4766): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019124444_5f8410f3-7e88-4c6c-99cb-4e3b1aff4766); Time taken: 0.056 seconds
INFO  : Executing command(queryId=hive_20171019124444_5f8410f3-7e88-4c6c-99cb-4e3b1aff4766): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019124444_5f8410f3-7e88-4c6c-99cb-4e3b1aff4766); Time taken: 0.102 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| lab_table  |
| sample_07  |
+------------+--+
2 rows selected (0.247 seconds)

````


````
[root@ip-172-31-7-61 ~]# kdestroy
[root@ip-172-31-7-61 ~]# kinit ferdinand
Password for ferdinand@IBRAHIM.COM:
[root@ip-172-31-7-61 ~]# beeline
^[[ABeeline version 1.1.0-cdh5.8.3 by Apache Hive
beeline> !connect jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM
scan complete in 2ms
Connecting to jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM
Enter username for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM: ferdinand
Enter password for jdbc:hive2://localhost:10000/default;principal=hive/ip-172-31-7-61.eu-central-1.compute.internal@IBRAHIM.COM: ********
Connected to: Apache Hive (version 1.1.0-cdh5.8.3)
Driver: Hive JDBC (version 1.1.0-cdh5.8.3)
Transaction isolation: TRANSACTION_REPEATABLE_READ
0: jdbc:hive2://localhost:10000/default> show tables;
INFO  : Compiling command(queryId=hive_20171019123434_77f04b14-4aae-4b21-8034-5f28e90c686c): show tables
INFO  : Semantic Analysis Completed
INFO  : Returning Hive schema: Schema(fieldSchemas:[FieldSchema(name:tab_name, type:string, comment:from deserializer)], properties:null)
INFO  : Completed compiling command(queryId=hive_20171019123434_77f04b14-4aae-4b21-8034-5f28e90c686c); Time taken: 0.055 seconds
INFO  : Executing command(queryId=hive_20171019123434_77f04b14-4aae-4b21-8034-5f28e90c686c): show tables
INFO  : Starting task [Stage-0:DDL] in serial mode
INFO  : Completed executing command(queryId=hive_20171019123434_77f04b14-4aae-4b21-8034-5f28e90c686c); Time taken: 0.101 seconds
INFO  : OK
+------------+--+
|  tab_name  |
+------------+--+
| sample_07  |
+------------+--+
1 row selected (0.247 seconds)
````

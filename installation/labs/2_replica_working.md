mysql> CHANGE MASTER TO MASTER_HOST='ip-172-31-4-12.eu-central-1.compute.internal.', MASTER_USER='replica', MASTER_PASSWORD='azerty', MASTER_LOG_FILE='mysql_binary_log.000003', MASTER_LOG_POS=1401;
Query OK, 0 rows affected (0.00 sec)

mysql> start slave;
Query OK, 0 rows affected (0.00 sec)

mysql> show slave status \G
*************************** 1. row ***************************
Slave_IO_State: Waiting for master to send event
Master_Host: ip-172-31-4-12.eu-central-1.compute.internal.
Master_User: replica
Master_Port: 3306
Connect_Retry: 60
Master_Log_File: mysql_binary_log.000003
Read_Master_Log_Pos: 1401
Relay_Log_File: mysqld-relay-bin.000002
Relay_Log_Pos: 260
Relay_Master_Log_File: mysql_binary_log.000003
Slave_IO_Running: Yes
Slave_SQL_Running: Yes
Replicate_Do_DB:
Replicate_Ignore_DB:
Replicate_Do_Table:
Replicate_Ignore_Table:
Replicate_Wild_Do_Table:
Replicate_Wild_Ignore_Table:
Last_Errno: 0
Last_Error:
Skip_Counter: 0
Exec_Master_Log_Pos: 1401
Relay_Log_Space: 417
Until_Condition: None
Until_Log_File:
Until_Log_Pos: 0
Master_SSL_Allowed: No
Master_SSL_CA_File:
Master_SSL_CA_Path:
Master_SSL_Cert:
Master_SSL_Cipher:
Master_SSL_Key:
Seconds_Behind_Master: 0
Master_SSL_Verify_Server_Cert: No
Last_IO_Errno: 0
Last_IO_Error:
Last_SQL_Errno: 0
Last_SQL_Error:
Replicate_Ignore_Server_Ids:
Master_Server_Id: 1
1 row in set (0.00 sec)

The replication is working
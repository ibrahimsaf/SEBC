
[centos@ip-172-31-4-12 /]$ sudo -u hdfs hdfs dfs /user/ibrahim/ 
[centos@ip-172-31-4-12 /]$ sudo -u hdfs hdfs dfs /user/ibrahim/source
[centos@ip-172-31-4-12 /]$ sudo -u hdfs hdfs dfs /user/ibrahim/destination
[centos@ip-172-31-4-12 /]$ sudo -u hdfs hdfs dfs -chown centos /user/ibrahim/source
[centos@ip-172-31-4-12 /]$ sudo -u hdfs hdfs dfs -chown centos /user/ibrahim/destination


Create a 500MB file using teragen : The execution duration is ~8seconds

[centos@ip-172-31-4-12 /]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen 5000000 /user/ibrahim/source/file_500MB
real    0m8.845s
user    0m13.849s
sys     0m0.497s

Copying the file using distcp tooks ~8seconds:

[centos@ip-172-31-4-12 /]$ time hadoop distcp /user/ibrahim/source/file_500MB /user/ibrahim/destination/file_500MB
real    0m8.834s
user    0m10.893s
sys     0m1.070s




Results from the copy with distcp:

[centos@ip-172-31-4-12 ~]$ hdfs fsck /user/ibrahim/source/file_500MB -files -blocks
Connecting to namenode via http://ip-172-31-7-61.eu-central-1.compute.internal:50070
FSCK started by centos (auth:SIMPLE) from /172.31.4.12 for path /user/ibrahim/source/file_500MB at Tue Oct 17 20:27:09 UTC 2017
/user/ibrahim/source/file_500MB <dir>
/user/ibrahim/source/file_500MB/_SUCCESS 0 bytes, 0 block(s):  OK

/user/ibrahim/source/file_500MB/part-m-00000 500000000 bytes, 4 block(s):  OK
0. BP-338852138-172.31.7.61-1508249049861:blk_1073742877_2053 len=134217728 Live_repl=3
1. BP-338852138-172.31.7.61-1508249049861:blk_1073742878_2054 len=134217728 Live_repl=3
2. BP-338852138-172.31.7.61-1508249049861:blk_1073742880_2056 len=134217728 Live_repl=3
3. BP-338852138-172.31.7.61-1508249049861:blk_1073742881_2057 len=97346816 Live_repl=3

Status: HEALTHY
 Total size:    500000000 B
 Total dirs:    1
 Total files:   2
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 125000000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Oct 17 20:27:09 UTC 2017 in 2 milliseconds


The filesystem under path '/user/ibrahim/source/file_500MB' is HEALTHY

[centos@ip-172-31-4-12 ~]$ hdfs fsck /user/ibrahim/destination/file_500MB -files -blocks
Connecting to namenode via http://ip-172-31-7-61.eu-central-1.compute.internal:50070
FSCK started by centos (auth:SIMPLE) from /172.31.4.12 for path /user/ibrahim/destination/file_500MB at Tue Oct 17 20:28:32 UTC 2017
/user/ibrahim/destination/file_500MB <dir>
/user/ibrahim/destination/file_500MB/_SUCCESS 0 bytes, 0 block(s):  OK

/user/ibrahim/destination/file_500MB/part-m-00000 500000000 bytes, 4 block(s):  OK
0. BP-338852138-172.31.7.61-1508249049861:blk_1073742887_2063 len=134217728 Live_repl=3
1. BP-338852138-172.31.7.61-1508249049861:blk_1073742888_2064 len=134217728 Live_repl=3
2. BP-338852138-172.31.7.61-1508249049861:blk_1073742889_2065 len=134217728 Live_repl=3
3. BP-338852138-172.31.7.61-1508249049861:blk_1073742891_2067 len=97346816 Live_repl=3

Status: HEALTHY
 Total size:    500000000 B
 Total dirs:    1
 Total files:   2
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 125000000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Tue Oct 17 20:28:32 UTC 2017 in 2 milliseconds


The filesystem under path '/user/ibrahim/destination/file_500MB' is HEALTHY



Result from the copy with BDR:
Using the cloudera manager, I create a scheduling task with immediate  execution to the /user/ibrahim/destinationBDR destination folder:

Connecting to namenode via http://ip-172-31-7-61.eu-central-1.compute.internal:50070
FSCK started by centos (auth:SIMPLE) from /172.31.4.12 for path /user/ibrahim/destinationBDR/ at Wed Oct 18 07:58:42 UTC 2017
/user/ibrahim/destinationBDR/ <dir>
/user/ibrahim/destinationBDR/source <dir>
/user/ibrahim/destinationBDR/source/file_500MB <dir>
/user/ibrahim/destinationBDR/source/file_500MB/_SUCCESS 0 bytes, 0 block(s):  OK

/user/ibrahim/destinationBDR/source/file_500MB/part-m-00000 500000000 bytes, 4 block(s):  OK
0. BP-338852138-172.31.7.61-1508249049861:blk_1073744046_3222 len=134217728 Live_repl=3
1. BP-338852138-172.31.7.61-1508249049861:blk_1073744047_3223 len=134217728 Live_repl=3
2. BP-338852138-172.31.7.61-1508249049861:blk_1073744048_3224 len=134217728 Live_repl=3
3. BP-338852138-172.31.7.61-1508249049861:blk_1073744049_3225 len=97346816 Live_repl=3

Status: HEALTHY
 Total size:    500000000 B
 Total dirs:    3
 Total files:   2
 Total symlinks:                0
 Total blocks (validated):      4 (avg. block size 125000000 B)
 Minimally replicated blocks:   4 (100.0 %)
 Over-replicated blocks:        0 (0.0 %)
 Under-replicated blocks:       0 (0.0 %)
 Mis-replicated blocks:         0 (0.0 %)
 Default replication factor:    3
 Average block replication:     3.0
 Corrupt blocks:                0
 Missing replicas:              0 (0.0 %)
 Number of data-nodes:          3
 Number of racks:               1
FSCK ended at Wed Oct 18 07:58:42 UTC 2017 in 2 milliseconds


The filesystem under path '/user/ibrahim/destinationBDR/' is HEALTHY

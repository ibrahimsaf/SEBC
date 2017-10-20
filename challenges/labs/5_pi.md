
Lunch pi programm with siwicki user
````
[root@ip-172-31-27-185 ~]# su - siwicki
Last failed login: Fri Oct 20 10:18:02 UTC 2017 on pts/0
There was 1 failed login attempt since the last successful login.
[siwicki@ip-172-31-27-185 ~]$ klist
klist: No credentials cache found (filename: /tmp/krb5cc_3000)
[siwicki@ip-172-31-27-185 ~]$ kinit siwicki@IBRAHIMSAF.CO.UK
Password for siwicki@IBRAHIMSAF.CO.UK:
[siwicki@ip-172-31-27-185 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_3000
Default principal: siwicki@IBRAHIMSAF.CO.UK

Valid starting       Expires              Service principal
10/20/2017 10:18:41  10/21/2017 10:18:41  krbtgt/IBRAHIMSAF.CO.UK@IBRAHIMSAF.CO.UK
        renew until 10/27/2017 10:18:41
[siwicki@ip-172-31-27-185 ~]$ hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-mapreduce-examples-*.jar pi  3 3
Number of Maps  = 3
Samples per Map = 3
Wrote input for Map #0
Wrote input for Map #1
Wrote input for Map #2
Starting Job
17/10/20 10:18:55 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-19-162.eu-central-1.compute.internal/172.31.19.162:8032
17/10/20 10:18:55 INFO hdfs.DFSClient: Created token for siwicki: HDFS_DELEGATION_TOKEN owner=siwicki@IBRAHIMSAF.CO.UK, renewer=yarn, realUser=, issueDate=1508494735846, maxDate=1509099535846, sequenceNumber=2, masterKeyId=2 on 172.31.19.162:8020
17/10/20 10:18:55 INFO security.TokenCache: Got dt for hdfs://ip-172-31-19-162.eu-central-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.19.162:8020, Ident: (token for siwicki: HDFS_DELEGATION_TOKEN owner=siwicki@IBRAHIMSAF.CO.UK, renewer=yarn, realUser=, issueDate=1508494735846, maxDate=1509099535846, sequenceNumber=2, masterKeyId=2)
17/10/20 10:18:56 INFO input.FileInputFormat: Total input paths to process : 3
17/10/20 10:18:56 INFO mapreduce.JobSubmitter: number of splits:3
17/10/20 10:18:56 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508493476083_0002
17/10/20 10:18:56 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.19.162:8020, Ident: (token for siwicki: HDFS_DELEGATION_TOKEN owner=siwicki@IBRAHIMSAF.CO.UK, renewer=yarn, realUser=, issueDate=1508494735846, maxDate=1509099535846, sequenceNumber=2, masterKeyId=2)
17/10/20 10:18:56 INFO impl.YarnClientImpl: Submitted application application_1508493476083_0002
17/10/20 10:18:56 INFO mapreduce.Job: The url to track the job: http://ip-172-31-19-162.eu-central-1.compute.internal:8088/proxy/application_1508493476083_0002/
17/10/20 10:18:56 INFO mapreduce.Job: Running job: job_1508493476083_0002
17/10/20 10:19:04 INFO mapreduce.Job: Job job_1508493476083_0002 running in uber mode : false
17/10/20 10:19:04 INFO mapreduce.Job:  map 0% reduce 0%
17/10/20 10:19:11 INFO mapreduce.Job:  map 33% reduce 0%
17/10/20 10:19:14 INFO mapreduce.Job:  map 100% reduce 0%
17/10/20 10:19:20 INFO mapreduce.Job:  map 100% reduce 100%
17/10/20 10:19:20 INFO mapreduce.Job: Job job_1508493476083_0002 completed successfully
17/10/20 10:19:21 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=55
                FILE: Number of bytes written=500392
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=912
                HDFS: Number of bytes written=215
                HDFS: Number of read operations=15
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Job Counters
                Launched map tasks=3
                Launched reduce tasks=1
                Data-local map tasks=3
                Total time spent by all maps in occupied slots (ms)=21310
                Total time spent by all reduces in occupied slots (ms)=3315
                Total time spent by all map tasks (ms)=21310
                Total time spent by all reduce tasks (ms)=3315
                Total vcore-seconds taken by all map tasks=21310
                Total vcore-seconds taken by all reduce tasks=3315
                Total megabyte-seconds taken by all map tasks=21821440
                Total megabyte-seconds taken by all reduce tasks=3394560
        Map-Reduce Framework
                Map input records=3
                Map output records=6
                Map output bytes=54
                Map output materialized bytes=100
                Input split bytes=558
                Combine input records=0
                Combine output records=0
                Reduce input groups=2
                Reduce shuffle bytes=100
                Reduce input records=6
                Reduce output records=0
                Spilled Records=12
                Shuffled Maps =3
                Failed Shuffles=0
                Merged Map outputs=3
                GC time elapsed (ms)=90
                CPU time spent (ms)=2610
                Physical memory (bytes) snapshot=1552187392
                Virtual memory (bytes) snapshot=6369886208
                Total committed heap usage (bytes)=1784152064
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=354
        File Output Format Counters
                Bytes Written=97
Job Finished in 25.468 seconds
Estimated value of Pi is 3.55555555555555555556

````


Realm name : IBRAHIMSAF.CO.UK


un the terasort program as ernest using /user/ernest/tgen512m
````
[ernest@ip-172-31-27-185 ~]$ kinit ernest@IBRAHIMSAF.CO.UK
Password for ernest@IBRAHIMSAF.CO.UK:
[ernest@ip-172-31-27-185 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_2000
Default principal: ernest@IBRAHIMSAF.CO.UK

Valid starting       Expires              Service principal
10/20/2017 10:05:03  10/21/2017 10:05:03  krbtgt/IBRAHIMSAF.CO.UK@IBRAHIMSAF.CO.UK
        renew until 10/27/2017 10:05:03

[ernest@ip-172-31-27-185 ~]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/ernest/tgen512m /user/ernest/tgen512m_result
17/10/20 10:12:48 INFO terasort.TeraSort: starting
17/10/20 10:12:50 INFO hdfs.DFSClient: Created token for ernest: HDFS_DELEGATION_TOKEN owner=ernest@IBRAHIMSAF.CO.UK, renewer=yarn, realUser=, issueDate=1508494370077, maxDate=1509099170077, sequenceNumber=1, masterKeyId=2 on 172.31.19.162:8020
17/10/20 10:12:50 INFO security.TokenCache: Got dt for hdfs://ip-172-31-19-162.eu-central-1.compute.internal:8020; Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.19.162:8020, Ident: (token for ernest: HDFS_DELEGATION_TOKEN owner=ernest@IBRAHIMSAF.CO.UK, renewer=yarn, realUser=, issueDate=1508494370077, maxDate=1509099170077, sequenceNumber=1, masterKeyId=2)
17/10/20 10:12:50 INFO input.FileInputFormat: Total input paths to process : 6
Spent 321ms computing base-splits.
Spent 4ms computing TeraScheduler splits.
Computing input splits took 326ms
Sampling 10 splits of 156
Making 6 from 100000 sampled records
Computing parititions took 807ms
Spent 1135ms computing partitions.
17/10/20 10:12:51 INFO client.RMProxy: Connecting to ResourceManager at ip-172-31-19-162.eu-central-1.compute.internal/172.31.19.162:8032
17/10/20 10:12:51 INFO mapreduce.JobSubmitter: number of splits:156
17/10/20 10:12:51 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_1508493476083_0001
17/10/20 10:12:51 INFO mapreduce.JobSubmitter: Kind: HDFS_DELEGATION_TOKEN, Service: 172.31.19.162:8020, Ident: (token for ernest: HDFS_DELEGATION_TOKEN owner=ernest@IBRAHIMSAF.CO.UK, renewer=yarn, realUser=, issueDate=1508494370077, maxDate=1509099170077, sequenceNumber=1, masterKeyId=2)
17/10/20 10:12:52 INFO impl.YarnClientImpl: Submitted application application_1508493476083_0001
17/10/20 10:12:52 INFO mapreduce.Job: The url to track the job: http://ip-172-31-19-162.eu-central-1.compute.internal:8088/proxy/application_1508493476083_0001/
17/10/20 10:12:52 INFO mapreduce.Job: Running job: job_1508493476083_0001
17/10/20 10:13:01 INFO mapreduce.Job: Job job_1508493476083_0001 running in uber mode : false
17/10/20 10:13:01 INFO mapreduce.Job:  map 0% reduce 0%
17/10/20 10:13:10 INFO mapreduce.Job:  map 1% reduce 0%
17/10/20 10:13:18 INFO mapreduce.Job:  map 2% reduce 0%
17/10/20 10:13:19 INFO mapreduce.Job:  map 6% reduce 0%
17/10/20 10:13:26 INFO mapreduce.Job:  map 7% reduce 0%
17/10/20 10:13:27 INFO mapreduce.Job:  map 8% reduce 0%
17/10/20 10:13:28 INFO mapreduce.Job:  map 9% reduce 0%
17/10/20 10:13:29 INFO mapreduce.Job:  map 11% reduce 0%
17/10/20 10:13:30 INFO mapreduce.Job:  map 12% reduce 0%
17/10/20 10:13:34 INFO mapreduce.Job:  map 13% reduce 0%
17/10/20 10:13:38 INFO mapreduce.Job:  map 15% reduce 0%
17/10/20 10:13:39 INFO mapreduce.Job:  map 16% reduce 0%
17/10/20 10:13:40 INFO mapreduce.Job:  map 17% reduce 0%
17/10/20 10:13:42 INFO mapreduce.Job:  map 18% reduce 0%
17/10/20 10:13:45 INFO mapreduce.Job:  map 19% reduce 0%
17/10/20 10:13:47 INFO mapreduce.Job:  map 20% reduce 0%
17/10/20 10:13:48 INFO mapreduce.Job:  map 21% reduce 0%
17/10/20 10:13:49 INFO mapreduce.Job:  map 22% reduce 0%
17/10/20 10:13:50 INFO mapreduce.Job:  map 23% reduce 0%
17/10/20 10:13:54 INFO mapreduce.Job:  map 24% reduce 0%
17/10/20 10:13:56 INFO mapreduce.Job:  map 26% reduce 0%
17/10/20 10:13:57 INFO mapreduce.Job:  map 27% reduce 0%
17/10/20 10:13:59 INFO mapreduce.Job:  map 28% reduce 0%
17/10/20 10:14:02 INFO mapreduce.Job:  map 29% reduce 0%
17/10/20 10:14:03 INFO mapreduce.Job:  map 30% reduce 0%
17/10/20 10:14:05 INFO mapreduce.Job:  map 32% reduce 0%
17/10/20 10:14:09 INFO mapreduce.Job:  map 34% reduce 0%
17/10/20 10:14:10 INFO mapreduce.Job:  map 35% reduce 0%
17/10/20 10:14:15 INFO mapreduce.Job:  map 36% reduce 0%
17/10/20 10:14:16 INFO mapreduce.Job:  map 37% reduce 0%
17/10/20 10:14:17 INFO mapreduce.Job:  map 38% reduce 0%
17/10/20 10:14:19 INFO mapreduce.Job:  map 39% reduce 0%
17/10/20 10:14:20 INFO mapreduce.Job:  map 40% reduce 0%
17/10/20 10:14:23 INFO mapreduce.Job:  map 41% reduce 0%
17/10/20 10:14:24 INFO mapreduce.Job:  map 43% reduce 0%
17/10/20 10:14:25 INFO mapreduce.Job:  map 44% reduce 0%
17/10/20 10:14:29 INFO mapreduce.Job:  map 46% reduce 0%
17/10/20 10:14:31 INFO mapreduce.Job:  map 47% reduce 0%
17/10/20 10:14:33 INFO mapreduce.Job:  map 48% reduce 0%
17/10/20 10:14:34 INFO mapreduce.Job:  map 49% reduce 0%
17/10/20 10:14:37 INFO mapreduce.Job:  map 50% reduce 0%
17/10/20 10:14:38 INFO mapreduce.Job:  map 51% reduce 0%
17/10/20 10:14:39 INFO mapreduce.Job:  map 52% reduce 0%
17/10/20 10:14:41 INFO mapreduce.Job:  map 53% reduce 0%
17/10/20 10:14:42 INFO mapreduce.Job:  map 54% reduce 0%
17/10/20 10:14:46 INFO mapreduce.Job:  map 56% reduce 0%
17/10/20 10:14:49 INFO mapreduce.Job:  map 57% reduce 0%
17/10/20 10:14:50 INFO mapreduce.Job:  map 58% reduce 0%
17/10/20 10:14:51 INFO mapreduce.Job:  map 60% reduce 0%
17/10/20 10:14:53 INFO mapreduce.Job:  map 61% reduce 0%
17/10/20 10:14:58 INFO mapreduce.Job:  map 62% reduce 0%
17/10/20 10:14:59 INFO mapreduce.Job:  map 64% reduce 0%
17/10/20 10:15:00 INFO mapreduce.Job:  map 65% reduce 0%
17/10/20 10:15:02 INFO mapreduce.Job:  map 66% reduce 0%
17/10/20 10:15:05 INFO mapreduce.Job:  map 67% reduce 0%
17/10/20 10:15:08 INFO mapreduce.Job:  map 68% reduce 0%
17/10/20 10:15:09 INFO mapreduce.Job:  map 70% reduce 0%
17/10/20 10:15:10 INFO mapreduce.Job:  map 71% reduce 0%
17/10/20 10:15:12 INFO mapreduce.Job:  map 72% reduce 0%
17/10/20 10:15:16 INFO mapreduce.Job:  map 73% reduce 0%
17/10/20 10:15:18 INFO mapreduce.Job:  map 74% reduce 0%
17/10/20 10:15:19 INFO mapreduce.Job:  map 76% reduce 0%
17/10/20 10:15:20 INFO mapreduce.Job:  map 78% reduce 0%
17/10/20 10:15:27 INFO mapreduce.Job:  map 79% reduce 0%
17/10/20 10:15:28 INFO mapreduce.Job:  map 81% reduce 0%
17/10/20 10:15:30 INFO mapreduce.Job:  map 82% reduce 0%
17/10/20 10:15:31 INFO mapreduce.Job:  map 83% reduce 0%
17/10/20 10:15:34 INFO mapreduce.Job:  map 84% reduce 0%
17/10/20 10:15:35 INFO mapreduce.Job:  map 85% reduce 0%
17/10/20 10:15:37 INFO mapreduce.Job:  map 86% reduce 0%
17/10/20 10:15:39 INFO mapreduce.Job:  map 87% reduce 0%
17/10/20 10:15:43 INFO mapreduce.Job:  map 87% reduce 3%
17/10/20 10:15:44 INFO mapreduce.Job:  map 87% reduce 7%
17/10/20 10:15:45 INFO mapreduce.Job:  map 87% reduce 11%
17/10/20 10:15:46 INFO mapreduce.Job:  map 87% reduce 21%
17/10/20 10:15:47 INFO mapreduce.Job:  map 88% reduce 22%
17/10/20 10:15:48 INFO mapreduce.Job:  map 88% reduce 23%
17/10/20 10:15:49 INFO mapreduce.Job:  map 88% reduce 24%
17/10/20 10:15:52 INFO mapreduce.Job:  map 88% reduce 25%
17/10/20 10:15:53 INFO mapreduce.Job:  map 89% reduce 25%
17/10/20 10:15:54 INFO mapreduce.Job:  map 90% reduce 25%
17/10/20 10:16:00 INFO mapreduce.Job:  map 92% reduce 25%
17/10/20 10:16:04 INFO mapreduce.Job:  map 92% reduce 26%
17/10/20 10:16:06 INFO mapreduce.Job:  map 93% reduce 26%
17/10/20 10:16:07 INFO mapreduce.Job:  map 94% reduce 26%
17/10/20 10:16:12 INFO mapreduce.Job:  map 95% reduce 26%
17/10/20 10:16:14 INFO mapreduce.Job:  map 96% reduce 26%
17/10/20 10:16:17 INFO mapreduce.Job:  map 97% reduce 27%
17/10/20 10:16:22 INFO mapreduce.Job:  map 98% reduce 27%
17/10/20 10:16:23 INFO mapreduce.Job:  map 99% reduce 27%
17/10/20 10:16:27 INFO mapreduce.Job:  map 100% reduce 27%
17/10/20 10:16:28 INFO mapreduce.Job:  map 100% reduce 28%
17/10/20 10:16:29 INFO mapreduce.Job:  map 100% reduce 37%
17/10/20 10:16:30 INFO mapreduce.Job:  map 100% reduce 42%
17/10/20 10:16:31 INFO mapreduce.Job:  map 100% reduce 53%
17/10/20 10:16:32 INFO mapreduce.Job:  map 100% reduce 57%
17/10/20 10:16:33 INFO mapreduce.Job:  map 100% reduce 63%
17/10/20 10:16:34 INFO mapreduce.Job:  map 100% reduce 66%
17/10/20 10:16:35 INFO mapreduce.Job:  map 100% reduce 69%
17/10/20 10:16:36 INFO mapreduce.Job:  map 100% reduce 71%
17/10/20 10:16:37 INFO mapreduce.Job:  map 100% reduce 74%
17/10/20 10:16:38 INFO mapreduce.Job:  map 100% reduce 77%
17/10/20 10:16:39 INFO mapreduce.Job:  map 100% reduce 84%
17/10/20 10:16:40 INFO mapreduce.Job:  map 100% reduce 87%
17/10/20 10:16:41 INFO mapreduce.Job:  map 100% reduce 90%
17/10/20 10:16:42 INFO mapreduce.Job:  map 100% reduce 91%
17/10/20 10:16:43 INFO mapreduce.Job:  map 100% reduce 93%
17/10/20 10:16:44 INFO mapreduce.Job:  map 100% reduce 96%
17/10/20 10:16:45 INFO mapreduce.Job:  map 100% reduce 98%
17/10/20 10:16:49 INFO mapreduce.Job:  map 100% reduce 100%
17/10/20 10:16:49 INFO mapreduce.Job: Job job_1508493476083_0001 completed successfully
17/10/20 10:16:49 INFO mapreduce.Job: Counters: 49
        File System Counters
                FILE: Number of bytes read=2271720378
                FILE: Number of bytes written=4515608772
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=5120024492
                HDFS: Number of bytes written=5120000000
                HDFS: Number of read operations=486
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=12
        Job Counters
                Launched map tasks=156
                Launched reduce tasks=6
                Data-local map tasks=156
                Total time spent by all maps in occupied slots (ms)=1178368
                Total time spent by all reduces in occupied slots (ms)=381762
                Total time spent by all map tasks (ms)=1178368
                Total time spent by all reduce tasks (ms)=381762
                Total vcore-seconds taken by all map tasks=1178368
                Total vcore-seconds taken by all reduce tasks=381762
                Total megabyte-seconds taken by all map tasks=1206648832
                Total megabyte-seconds taken by all reduce tasks=390924288
        Map-Reduce Framework
                Map input records=51200000
                Map output records=51200000
                Map output bytes=5222400000
                Map output materialized bytes=2223497972
                Input split bytes=24492
                Combine input records=0
                Combine output records=0
                Reduce input groups=51200000
                Reduce shuffle bytes=2223497972
                Reduce input records=51200000
                Reduce output records=51200000
                Spilled Records=102400000
                Shuffled Maps =936
                Failed Shuffles=0
                Merged Map outputs=936
                GC time elapsed (ms)=16040
                CPU time spent (ms)=737940
                Physical memory (bytes) snapshot=79228538880
                Virtual memory (bytes) snapshot=256227586048
                Total committed heap usage (bytes)=91273822208
        Shuffle Errors
                BAD_ID=0
                CONNECTION=0
                IO_ERROR=0
                WRONG_LENGTH=0
                WRONG_MAP=0
                WRONG_REDUCE=0
        File Input Format Counters
                Bytes Read=5120000000
        File Output Format Counters
                Bytes Written=5120000000
17/10/20 10:16:49 INFO terasort.TeraSort: done

real    4m1.980s
user    0m8.497s
sys     0m0.314s


````



[centos@ip-172-31-4-12 /]$ sudo -u hdfs hdfs dfs /user/ibrahim/ 
[centos@ip-172-31-4-12 /]$ sudo -u hdfs hdfs dfs /user/ibrahim/source
[centos@ip-172-31-4-12 /]$ sudo -u hdfs hdfs dfs /user/ibrahim/destination
[centos@ip-172-31-4-12 /]$ sudo -u hdfs hdfs dfs -chown centos /user/ibrahim/source
[centos@ip-172-31-4-12 /]$ sudo -u hdfs hdfs dfs -chown centos /user/ibrahim/destination


Create a 500MB file using teragen : The execution duration is ~8seconds

[centos@ip-172-31-4-12 /]$ time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen 5000000 /user/ibrahim/source/file_500MB
17/10/17 20:00:12 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
17/10/17 20:00:12 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
17/10/17 20:00:12 INFO terasort.TeraSort: Generating 5000000 using 1
17/10/17 20:00:12 INFO mapreduce.JobSubmitter: number of splits:1
17/10/17 20:00:12 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local308530447_0001
17/10/17 20:00:12 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
17/10/17 20:00:12 INFO mapreduce.Job: Running job: job_local308530447_0001
17/10/17 20:00:12 INFO mapred.LocalJobRunner: OutputCommitter set in config null
17/10/17 20:00:12 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/17 20:00:12 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.mapreduce.lib.output.FileOutputCommitter
17/10/17 20:00:12 INFO mapred.LocalJobRunner: Waiting for map tasks
17/10/17 20:00:12 INFO mapred.LocalJobRunner: Starting task: attempt_local308530447_0001_m_000000_0
17/10/17 20:00:13 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/17 20:00:13 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/17 20:00:13 INFO mapred.MapTask: Processing split: org.apache.hadoop.examples.terasort.TeraGen$RangeInputFormat$RangeInputSplit@4a030114
17/10/17 20:00:13 INFO mapreduce.Job: Job job_local308530447_0001 running in uber mode : false
17/10/17 20:00:13 INFO mapreduce.Job:  map 0% reduce 0%
17/10/17 20:00:18 INFO mapred.LocalJobRunner:
17/10/17 20:00:18 INFO mapred.Task: Task:attempt_local308530447_0001_m_000000_0 is done. And is in the process of committing
17/10/17 20:00:18 INFO mapred.LocalJobRunner:
17/10/17 20:00:18 INFO mapred.Task: Task attempt_local308530447_0001_m_000000_0 is allowed to commit now
17/10/17 20:00:18 INFO output.FileOutputCommitter: Saved output of task 'attempt_local308530447_0001_m_000000_0' to hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/source/file_500MB/_temporary/0/task_local308530447_0001_m_000000
17/10/17 20:00:18 INFO mapred.LocalJobRunner: map
17/10/17 20:00:18 INFO mapred.Task: Task 'attempt_local308530447_0001_m_000000_0' done.
17/10/17 20:00:18 INFO mapred.LocalJobRunner: Finishing task: attempt_local308530447_0001_m_000000_0
17/10/17 20:00:18 INFO mapred.LocalJobRunner: map task executor complete.
17/10/17 20:00:18 INFO mapreduce.Job:  map 100% reduce 0%
17/10/17 20:00:18 INFO mapreduce.Job: Job job_local308530447_0001 completed successfully
17/10/17 20:00:18 INFO mapreduce.Job: Counters: 21
        File System Counters
                FILE: Number of bytes read=276333
                FILE: Number of bytes written=562581
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=0
                HDFS: Number of bytes written=500000000
                HDFS: Number of read operations=4
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=3
        Map-Reduce Framework
                Map input records=5000000
                Map output records=5000000
                Input split bytes=82
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=77
                Total committed heap usage (bytes)=232259584
        org.apache.hadoop.examples.terasort.TeraGen$Counters
                CHECKSUM=10735710707299981
        File Input Format Counters
                Bytes Read=0
        File Output Format Counters
                Bytes Written=500000000

real    0m8.845s
user    0m13.849s
sys     0m0.497s

Copying the file using distcp tooks ~8seconds:

[centos@ip-172-31-4-12 /]$ time hadoop distcp /user/ibrahim/source/file_500MB /user/ibrahim/destination/file_500MB
17/10/17 20:06:19 INFO tools.DistCp: Input Options: DistCpOptions{atomicCommit=false, syncFolder=false, deleteMissing=false, ignoreFailures=false, overwrite=false, skipCRC=false, blocking=true, numListstatusThreads=0, maxMaps=20, mapBandwidth=100, sslConfigurationFile='null', copyStrategy='uniformsize', preserveStatus=[], preserveRawXattrs=false, atomicWorkPath=null, logPath=null, sourceFileListing=null, sourcePaths=[/user/ibrahim/source/file_500MB], targetPath=/user/ibrahim/destination/file_500MB, targetPathExists=false, filtersFile='null'}
17/10/17 20:06:19 INFO Configuration.deprecation: session.id is deprecated. Instead, use dfs.metrics.session-id
17/10/17 20:06:19 INFO jvm.JvmMetrics: Initializing JVM Metrics with processName=JobTracker, sessionId=
17/10/17 20:06:19 INFO tools.SimpleCopyListing: Paths (files+dirs) cnt = 3; dirCnt = 1
17/10/17 20:06:19 INFO tools.SimpleCopyListing: Build file listing completed.
17/10/17 20:06:19 INFO Configuration.deprecation: io.sort.mb is deprecated. Instead, use mapreduce.task.io.sort.mb
17/10/17 20:06:19 INFO Configuration.deprecation: io.sort.factor is deprecated. Instead, use mapreduce.task.io.sort.factor
17/10/17 20:06:19 INFO tools.DistCp: Number of paths in the copy list: 3
17/10/17 20:06:19 INFO tools.DistCp: Number of paths in the copy list: 3
17/10/17 20:06:20 INFO jvm.JvmMetrics: Cannot initialize JVM Metrics with processName=JobTracker, sessionId= - already initialized
17/10/17 20:06:20 INFO mapreduce.JobSubmitter: number of splits:1
17/10/17 20:06:20 INFO mapreduce.JobSubmitter: Submitting tokens for job: job_local1082368753_0001
17/10/17 20:06:20 INFO mapreduce.Job: The url to track the job: http://localhost:8080/
17/10/17 20:06:20 INFO tools.DistCp: DistCp job-id: job_local1082368753_0001
17/10/17 20:06:20 INFO mapreduce.Job: Running job: job_local1082368753_0001
17/10/17 20:06:20 INFO mapred.LocalJobRunner: OutputCommitter set in config null
17/10/17 20:06:20 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/17 20:06:20 INFO mapred.LocalJobRunner: OutputCommitter is org.apache.hadoop.tools.mapred.CopyCommitter
17/10/17 20:06:20 INFO mapred.LocalJobRunner: Waiting for map tasks
17/10/17 20:06:20 INFO mapred.LocalJobRunner: Starting task: attempt_local1082368753_0001_m_000000_0
17/10/17 20:06:20 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/17 20:06:20 INFO mapred.Task:  Using ResourceCalculatorProcessTree : [ ]
17/10/17 20:06:20 INFO mapred.MapTask: Processing split: file:/tmp/hadoop-centos/mapred/staging/centos725671862/.staging/_distcp-1382958566/fileList.seq:0+656
17/10/17 20:06:20 INFO output.FileOutputCommitter: File Output Committer Algorithm version is 1
17/10/17 20:06:20 INFO mapred.CopyMapper: Copying hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/source/file_500MB to hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/destination/file_500MB
17/10/17 20:06:20 INFO mapred.CopyMapper: Copying hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/source/file_500MB/_SUCCESS to hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/destination/file_500MB/_SUCCESS
17/10/17 20:06:20 INFO mapred.RetriableFileCopyCommand: Creating temp file: hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/destination/file_500MB/.distcp.tmp.attempt_local1082368753_0001_m_000000_0
17/10/17 20:06:20 INFO mapred.CopyMapper: Copying hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/source/file_500MB/part-m-00000 to hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/destination/file_500MB/part-m-00000
17/10/17 20:06:20 INFO mapred.RetriableFileCopyCommand: Creating temp file: hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/destination/file_500MB/.distcp.tmp.attempt_local1082368753_0001_m_000000_0
17/10/17 20:06:21 INFO mapreduce.Job: Job job_local1082368753_0001 running in uber mode : false
17/10/17 20:06:21 INFO mapreduce.Job:  map 0% reduce 0%
17/10/17 20:06:26 INFO mapred.LocalJobRunner:
17/10/17 20:06:26 INFO mapred.Task: Task:attempt_local1082368753_0001_m_000000_0 is done. And is in the process of committing
17/10/17 20:06:26 INFO mapred.LocalJobRunner:
17/10/17 20:06:26 INFO mapred.Task: Task attempt_local1082368753_0001_m_000000_0 is allowed to commit now
17/10/17 20:06:26 INFO output.FileOutputCommitter: Saved output of task 'attempt_local1082368753_0001_m_000000_0' to file:/tmp/hadoop-centos/mapred/staging/centos725671862/.staging/_distcp-1382958566/_logs/_temporary/0/task_local1082368753_0001_m_000000
17/10/17 20:06:26 INFO mapred.LocalJobRunner: 100.0% Copying hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/source/file_500MB/part-m-00000 to hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/ibrahim/destination/file_500MB/part-m-00000 [476.8M/476.8M]
17/10/17 20:06:26 INFO mapred.Task: Task 'attempt_local1082368753_0001_m_000000_0' done.
17/10/17 20:06:26 INFO mapred.LocalJobRunner: Finishing task: attempt_local1082368753_0001_m_000000_0
17/10/17 20:06:26 INFO mapred.LocalJobRunner: map task executor complete.
17/10/17 20:06:26 INFO mapred.CopyCommitter: Cleaning up temporary work folder: file:/tmp/hadoop-centos/mapred/staging/centos725671862/.staging/_distcp-1382958566
17/10/17 20:06:26 INFO mapreduce.Job:  map 100% reduce 0%
17/10/17 20:06:26 INFO mapreduce.Job: Job job_local1082368753_0001 completed successfully
17/10/17 20:06:26 INFO mapreduce.Job: Counters: 23
        File System Counters
                FILE: Number of bytes read=1957481
                FILE: Number of bytes written=2264156
                FILE: Number of read operations=0
                FILE: Number of large read operations=0
                FILE: Number of write operations=0
                HDFS: Number of bytes read=500000000
                HDFS: Number of bytes written=500000000
                HDFS: Number of read operations=29
                HDFS: Number of large read operations=0
                HDFS: Number of write operations=5
        Map-Reduce Framework
                Map input records=3
                Map output records=0
                Input split bytes=160
                Spilled Records=0
                Failed Shuffles=0
                Merged Map outputs=0
                GC time elapsed (ms)=56
                Total committed heap usage (bytes)=239075328
        File Input Format Counters
                Bytes Read=692
        File Output Format Counters
                Bytes Written=8
        org.apache.hadoop.tools.mapred.CopyMapper$Counter
                BYTESCOPIED=500000000
                BYTESEXPECTED=500000000
                COPY=3

real    0m8.834s
user    0m10.893s
sys     0m1.070s




Results from the co^py with distcp^:

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













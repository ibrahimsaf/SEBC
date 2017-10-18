With default parameters:
````
[centos@ip-172-31-4-12 ~]$ ./yarntest.sh
Testing loop started on Wed Oct 18 14:51:02 UTC 2017
Teragen parameters: Dmapreduce.job.maps=8 mapreduce.map.memory.mb=512 Dmapreduce.map.java.opts.max.heap=409
real    1m21.934s
user    1m5.918s
sys     0m2.213s
Terasort parameters: Dmapreduce.job.maps=8 mapreduce.job.reduces=1 mapreduce.map.memory.mb=512 mapreduce.map.java.opts.max.heap=409 mapreduce.reduce.memory.mb=512 mapreduce.reduce.java.opts.max.heap=409

real    7m16.983s
user    6m11.886s
sys     0m31.966s
Deleted /results/tg-10GB-8-1-512
Deleted /results/ts-10GB-8-1-512
Teragen parameters: Dmapreduce.job.maps=8 mapreduce.map.memory.mb=1024 Dmapreduce.map.java.opts.max.heap=819

real    0m2.263s
user    0m3.545s
sys     0m0.199s
Terasort parameters: Dmapreduce.job.maps=8 mapreduce.job.reduces=1 mapreduce.map.memory.mb=1024 mapreduce.map.java.opts.max.heap=819 mapreduce.reduce.memory.mb=1024 mapreduce.reduce.java.opts.max.heap=819

real    6m55.462s
user    6m14.094s
sys     0m31.954s
Deleted /results/tg-10GB-8-1-1024
Deleted /results/ts-10GB-8-1-1024
Testing loop ended on Wed Oct 18 15:06:53 UTC 2017
````


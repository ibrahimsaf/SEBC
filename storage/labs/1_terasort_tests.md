Create user ibrahimsaf and password:
````
useradd ibrahimsaf
passwd ibrahimsaf
````

Create the HDFS home for the user
````
sudo -u hdfs hdfs dfs -mkdir /user/ibrahimsaf
sudo -u hdfs hdfs dfs -chown ibrahimsaf /user/ibrahimsaf
````

Connect with the user
````
su - ibrahimsaf
````

Create a 10Go, with 32Mo block, while limiting to 4 maps
````
time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar teragen -D dfs.block.size=33554432 -D mapred.map.tasks.maximum=4 100000000 /user/ibrahimsaf/file_10Go_2
Time:
real    2m23.820s
user    1m58.834s
sys     0m3.381s
````
 
Creating the same file without limiting maps tooks 1m48.798s
 
 
###### The terasort command:
````   
time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort  /user/ibrahimsaf/file_10Go_2  /user/ibrahimsaf/terasort_result
Execution time:
real    12m10.774s
user    14m17.996s
sys     0m56.457s
````	
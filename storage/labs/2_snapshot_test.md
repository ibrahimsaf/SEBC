Create a precious directory in HDFS and copy the ZIP course file into it:
````
sudo -u hdfs hdfs dfs -mkdir /user/precious
sudo -u hdfs hdfs dfs -chown centos /user/precious
hdfs dfs -put SEBC-master.zip /user/precious
````

Enable snapshots for precious
````
sudo -u hdfs hdfs dfsadmin -allowSnapshot /user/precious
````

Create a snapshot called sebc-hdfs-test
````
hdfs dfs -createSnapshot /user/precious sebc-hdfs-test
````

Delete the directory: It is not possible to delete a snapshottable folder, even the hdfs user cannot delete it
````
sudo -u hdfs hdfs dfs -rm -r /user/precious  
rm: Failed to move to trash: hdfs://ip-172-31-7-61.eu-central-1.compute.internal:8020/user/precious: The directory /user/precious cannot be deleted since /user/precious is snapshottable and already has snapshots
````

Delete the ZIP file
````
hdfs dfs -rm  /user/precious/*
````

Restore the deleted file
````
sudo -u hdfs hdfs dfs -cp /user/precious/.snapshot/sebc-hdfs-test/SEBC-master.zip /user/precious/
````

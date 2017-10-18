Explain any adjustments you make in
````
The HDFS DataNode uses a minimum of 1 core and about 1 GB of memory. The same requirements apply to the YARN NodeManager.  The same requirements apply to the Application manager. 

Impala, Hbase and solr are not used actually, so we did not allow ressources. Normally, we allocate at least 16 GB for the impala daemon. HBase RegionServer requires 12-16 GB of memory. Solr Server requires a minimum of 1 GB of memory.

````	



What criteria affects workload factor? What does a value of 1, 2, or 4 signify?
````

````




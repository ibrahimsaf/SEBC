What is ubertask optimization?
````
Ubertask optimization runs "sufficiently small" jobs sequentially within a single JVM. "Small" is defined by the mapreduce.job.ubertask.maxmaps, mapreduce.job.ubertask.maxreduces, and mapreduce.job.ubertask.maxbytes settings
````
Where in CM is the Kerberos Security Realm value displayed?
````
In the administration settings: Menu Administration -> Settings -> Kerberos Security Realm
````
Which CDH service(s) host a property for enabling Kerberos authentication?
````
Hive, zookeeper, Hue, oozie, HDFS, Yarn (in the search bar, we search for all services with kerberos principal parameter)
````
How do you upgrade the CM agents?
````
Once the cloudera manager is updated, he proposes automatically to update all agents.
Or Manually using : yum upgrade cloudera-manager-agent on all nodes
````
Give the tsquery statement used to chart Hue's CPU utilization?
````
select cpu_system_rate + cpu_user_rate where category=ROLE and serviceName=HUE
````
Name all the roles that make up the Hive service
````
Hive Metastore Server
WHCS WebHCat Server
HS2 HiveServer2
Gateway
````
What steps must be completed before integrating Cloudera Manager with Kerberos?
````
If we are Using AES-256 Encryption, Install the JCE Policy File. Then get or create a Kerberos Principal for the Cloudera Manager Server
Then we can integrate kerberos in cloudera manager by choosing in the cluster menu: "Enable Kerberos"
````
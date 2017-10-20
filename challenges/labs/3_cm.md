HDFS users dir
````
[root@ip-172-31-19-162 ~]# hdfs dfs -ls /user
Found 8 items
drwxr-xr-x   - admin   admin               0 2017-10-20 09:00 /user/admin
drwxr-xr-x   - ernest  ernest              0 2017-10-20 08:56 /user/ernest
drwxr-xr-x   - hdfs    supergroup          0 2017-10-20 08:59 /user/hdfs
drwxrwxrwx   - mapred  hadoop              0 2017-10-20 08:49 /user/history
drwxrwxr-t   - hive    hive                0 2017-10-20 08:50 /user/hive
drwxrwxr-x   - hue     hue                 0 2017-10-20 08:50 /user/hue
drwxrwxr-x   - oozie   oozie               0 2017-10-20 08:51 /user/oozie
drwxr-xr-x   - siwicki siwicki             0 2017-10-20 08:56 /user/siwicki
````

Output from the CM API call 
````
[root@ip-172-31-27-185 ~]# curl -u admin:admin  'http://localhost:7180/api/v14/hosts'
{
  "items" : [ {
    "hostId" : "i-03facdbc021738401",
    "ipAddress" : "172.31.19.141",
    "hostname" : "ip-172-31-19-141.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-27-185.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-03facdbc021738401",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "i-02d55536330fce318",
    "ipAddress" : "172.31.19.162",
    "hostname" : "ip-172-31-19-162.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-27-185.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-02d55536330fce318",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "i-0f9e680365c8d1831",
    "ipAddress" : "172.31.24.13",
    "hostname" : "ip-172-31-24-13.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-27-185.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-0f9e680365c8d1831",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "i-03d104281795e8105",
    "ipAddress" : "172.31.27.108",
    "hostname" : "ip-172-31-27-108.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-27-185.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-03d104281795e8105",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  }, {
    "hostId" : "i-03006e046ab58357d",
    "ipAddress" : "172.31.27.185",
    "hostname" : "ip-172-31-27-185.eu-central-1.compute.internal",
    "rackId" : "/default",
    "hostUrl" : "http://ip-172-31-27-185.eu-central-1.compute.internal:7180/cmf/hostRedirect/i-03006e046ab58357d",
    "maintenanceMode" : false,
    "maintenanceOwners" : [ ],
    "commissionState" : "COMMISSIONED",
    "numCores" : 4,
    "numPhysicalCores" : 2,
    "totalPhysMemBytes" : 15332438016
  } ]
}
````
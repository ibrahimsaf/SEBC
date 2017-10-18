

Stopping Hive:
````
[centos@ip-172-31-4-12 ~]$ curl -u ibrahimsaf:cloudera -X POST 'http://localhost:7180/api/v6/clusters/ibrahimsaf-SEBC/services/hive/commands/stop'
{
  "id" : 267,
  "name" : "Stop",
  "startTime" : "2017-10-18T09:59:04.100Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
}
````

Starting hive:
````
[centos@ip-172-31-4-12 ~]$curl -u ibrahimsaf:cloudera -X POST 'http://localhost:7180/api/v6/clusters/ibrahimsaf-SEBC/services/hive/commands/start'
{
  "id" : 270,
  "name" : "Start",
  "startTime" : "2017-10-18T09:59:24.717Z",
  "active" : true,
  "serviceRef" : {
    "clusterName" : "cluster",
    "serviceName" : "hive"
  }
````

Get Hive state:
````
[centos@ip-172-31-4-12 ~]$ curl -u ibrahimsaf:cloudera'http://localhost:7180/api/v1/clusters/ibrahimsaf-SEBC/services/hive'
{
  "name" : "hive",
  "type" : "HIVE",
  "clusterRef" : {
    "clusterName" : "cluster"
  },
  "serviceUrl" : "http://ip-172-31-4-12.eu-central-1.compute.internal:7180/cmf/serviceRedirect/hive",
  "serviceState" : "STARTED",
  "healthSummary" : "GOOD",
  "healthChecks" : [ {
    "name" : "HIVE_HIVEMETASTORES_HEALTHY",
    "summary" : "GOOD"
  }, {
    "name" : "HIVE_HIVESERVER2S_HEALTHY",
    "summary" : "GOOD"
  } ],
  "configStale" : false
}
````
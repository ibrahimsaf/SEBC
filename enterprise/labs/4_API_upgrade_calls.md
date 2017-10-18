Report the latest available version of the API
````
[centos@ip-172-31-4-12 ~]$ curl -u ibrahimsaf:cloudera 'http://localhost:7180/api/version'
v14
````
Report the CM version
````
[centos@ip-172-31-4-12 ~]$ curl -u ibrahimsaf:cloudera 'http://localhost:7180/api/v14/cm/version'
{
  "version" : "5.9.3",
  "buildUser" : "jenkins",
  "buildTimestamp" : "20170627-1506",
  "gitHash" : "23506bb4e114dd460bdac64c57a672e6be631907",
  "snapshot" : false
}
````
List all CM users
````
[centos@ip-172-31-4-12 ~]$ curl -u ibrahimsaf:cloudera 'http://localhost:7180/api/v14/users'
{
  "items" : [ {
    "name" : "admin",
    "roles" : [ "ROLE_LIMITED" ]
  }, {
    "name" : "ibrahimsaf",
    "roles" : [ "ROLE_ADMIN" ]
  }, {
    "name" : "minotaur",
    "roles" : [ "ROLE_CLUSTER_ADMIN" ]
  } ]
}
````
Report the database server in use by CM
````
[centos@ip-172-31-4-12 ~]$ curl -u ibrahimsaf:cloudera 'http://localhost:7180/api/v14/cm/scmDbInfo'
{
  "scmDbType" : "MYSQL",
  "embeddedDbUsed" : false
}
````

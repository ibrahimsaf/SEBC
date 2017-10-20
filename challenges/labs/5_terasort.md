Realm name : IBRAHIMSAF.CO.UK


````
[ernest@ip-172-31-27-185 ~]$ kinit ernest@IBRAHIMSAF.CO.UK
Password for ernest@IBRAHIMSAF.CO.UK:
[ernest@ip-172-31-27-185 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_2000
Default principal: ernest@IBRAHIMSAF.CO.UK

Valid starting       Expires              Service principal
10/20/2017 10:05:03  10/21/2017 10:05:03  krbtgt/IBRAHIMSAF.CO.UK@IBRAHIMSAF.CO.UK
        renew until 10/27/2017 10:05:03



[ernest@ip-172-31-27-185 ~]$  time hadoop jar /opt/cloudera/parcels/CDH/jars/hadoop-examples.jar terasort /user/ernest/tgen512m /user/ernest/tgen512m_result 

````

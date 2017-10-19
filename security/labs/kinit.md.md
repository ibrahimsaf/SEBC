The kinit command you use to authenticate my test user ibrahimsaf:
````
[ibrahimsaf@ip-172-31-4-12 ~]$  kinit ibrahimsaf@IBRAHIM.COM
Password for ibrahimsaf@IBRAHIM.COM:
````
The output from a klist command listing your credentials and ticket lifetime:
````
[ibrahimsaf@ip-172-31-4-12 ~]$ klist
Ticket cache: FILE:/tmp/krb5cc_1001
Default principal: ibrahimsaf@IBRAHIM.COM

Valid starting       Expires              Service principal
10/19/2017 09:29:42  10/20/2017 09:29:42  krbtgt/IBRAHIM.COM@IBRAHIM.COM
        renew until 10/26/2017 09:29:42

````
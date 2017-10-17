[centos@ip-172-31-41-84 ~]$ sysctl vm.swappiness
vm.swappiness = 60


[centos@ip-172-31-45-108 ~]$ sysctl vm.swappiness
vm.swappiness = 60

[centos@ip-172-31-38-98 ~]$ sysctl vm.swappiness
vm.swappiness = 60

[centos@ip-172-31-43-182 ~]$  sysctl vm.swappiness
vm.swappiness = 60

[centos@ip-172-31-45-234 ~]$ sysctl vm.swappiness
vm.swappiness = 60



To set the swapiness to 1, on all machines:

sysctl vm.swappiness=1
Edit the /etc/sysctl.conf file and add at the end: "vm.swappiness=1"
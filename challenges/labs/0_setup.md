List the cloud provider you are using (AWS, GCE, Azure, other)
````
AWS: 5 virtual machine m3.xlarge
````
List the Linux release you have chosen
````
Centos 7.2
````
Show that the disk space on each node is at least 30 GB
````
All virtual machines are identical:
[root@ip-172-31-19-162 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1      100G 1016M   99G   1% /
devtmpfs        7.3G     0  7.3G   0% /dev
tmpfs           7.2G     0  7.2G   0% /dev/shm
tmpfs           7.2G   17M  7.2G   1% /run
tmpfs           7.2G     0  7.2G   0% /sys/fs/cgroup
tmpfs           1.5G     0  1.5G   0% /run/user/1000

````
List the command and output for yum repolist enabled
````
[root@ip-172-31-19-162 ~]# yum repolist enabled
Loaded plugins: fastestmirror
Loading mirror speeds from cached hostfile
 * base: mirror.23media.de
 * extras: mirror.imt-systems.com
 * updates: ftp.antilo.de
repo id                                                                         repo name                                                                         status
base/7/x86_64                                                                   CentOS-7 - Base                                                                   9,591
extras/7/x86_64                                                                 CentOS-7 - Extras                                                                   227
updates/7/x86_64                                                                CentOS-7 - Updates                                                                  741
repolist: 10,559
````

Creating users and groups on all machines:
````
[root@ip-172-31-27-185 ~]# useradd -u 2000 ernest
[root@ip-172-31-27-185 ~]# useradd -u 3000 siwicki
[root@ip-172-31-27-185 ~]# groupadd usa
[root@ip-172-31-27-185 ~]# groupadd emea
[root@ip-172-31-27-185 ~]# usermod -g usa ernest
[root@ip-172-31-27-185 ~]#  usermod -g emea siwicki
````

List the /etc/passwd entries for ernest and siwicki in your setup file
````
[root@ip-172-31-27-185 ~]# cat /etc/passwd | grep ernest
ernest:x:2000:3001::/home/ernest:/bin/bash
[root@ip-172-31-27-185 ~]# cat /etc/passwd | grep siwicki
siwicki:x:3000:3002::/home/siwicki:/bin/bash
````

List the /etc/group entries for usa and emea in your setup file
````
[root@ip-172-31-27-185 ~]# cat /etc/group | grep usa
usa:x:3001:
[root@ip-172-31-27-185 ~]# cat /etc/group | grep emea
emea:x:3002:
````

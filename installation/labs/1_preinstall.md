##  Check the swapiness using this command: 

[centos@ip-172-31-4-12 ~]$ sysctl vm.swappiness
vm.swappiness = 30
---
To set the swapiness to 1, on all machines:
Edit the /etc/sysctl.conf file and add at the end: "vm.swappiness=1"
echo "vm.swappiness=1" >> /etc/sysctl.conf
sysctl vm.swappiness=1

---
[root@ip-172-31-4-12 ~]# df -h
Filesystem      Size  Used Avail Use% Mounted on
/dev/xvda1      100G  878M  100G   1% /
devtmpfs        7.8G     0  7.8G   0% /dev
tmpfs           7.7G     0  7.7G   0% /dev/shm
tmpfs           7.7G   17M  7.7G   1% /run
tmpfs           7.7G     0  7.7G   0% /sys/fs/cgroup
tmpfs           1.6G     0  1.6G   0% /run/user/1000


---

##  Disable transparent hugepage support   

echo never > /sys/kernel/mm/transparent_hugepage/enabled
---
To disable THP, add the following lines to the end of /etc/rc.local before the exit line (if present), and reboot the affected servers:
---
echo never > /sys/kernel/mm/transparent_hugepage/enabled
echo never > /sys/kernel/mm/transparent_hugepage/defrag
echo 0 > /sys/kernel/mm/transparent_hugepage/khugepaged/defrag
echo no > /sys/kernel/mm/transparent_hugepage/khugepaged/defrag
echo never > /sys/kernel/mm/redhat_transparent_hugepage/enabled
echo never > /sys/kernel/mm/redhat_transparent_hugepage/defrag
echo 0 > /sys/kernel/mm/redhat_transparent_hugepage/khugepaged/defrag
echo no > /sys/kernel/mm/redhat_transparent_hugepage/khugepaged/defrag


---

##  Verify DNS and reverse DNS configuration avec nslookup 

yum -y install bind-utils
---
[root@ip-172-31-4-12 ~]# nslookup 172.31.4.12
Server:         172.31.0.2
Address:        172.31.0.2#53
---
Non-authoritative answer:
12.4.31.172.in-addr.arpa        name = ip-172-31-4-12.eu-central-1.compute.internal.
---
Authoritative answers can be found from:
---
[root@ip-172-31-4-12 ~]# nslookup ip-172-31-4-12.eu-central-1.compute.internal.
Server:         172.31.0.2
Address:        172.31.0.2#53
---
Non-authoritative answer:
Name:   ip-172-31-4-12.eu-central-1.compute.internal
Address: 172.31.4.12
---
---

##  Network interfaces: 

---
[root@ip-172-31-4-12 ~]# ip a
1: lo: <LOOPBACK,UP,LOWER_UP> mtu 65536 qdisc noqueue state UNKNOWN
    link/loopback 00:00:00:00:00:00 brd 00:00:00:00:00:00
    inet 127.0.0.1/8 scope host lo
       valid_lft forever preferred_lft forever
    inet6 ::1/128 scope host
       valid_lft forever preferred_lft forever
2: eth0: <BROADCAST,MULTICAST,UP,LOWER_UP> mtu 9001 qdisc pfifo_fast state UP qlen 1000
    link/ether 0a:e2:c2:5c:c3:c0 brd ff:ff:ff:ff:ff:ff
    inet 172.31.4.12/20 brd 172.31.15.255 scope global dynamic eth0
       valid_lft 3375sec preferred_lft 3375sec
    inet6 fe80::8e2:c2ff:fe5c:c3c0/64 scope link
       valid_lft forever preferred_lft forever
---
	   
##  NTP and NSCD services: 

---
yum -y install nscd ntp
---
[root@ip-172-31-4-12 ~]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
[root@ip-172-31-4-12 ~]#  service nscd start
Redirecting to /bin/systemctl start  nscd.service
[root@ip-172-31-4-12 ~]# sudo service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
[root@ip-172-31-4-12 ~]# service ntpd start
Redirecting to /bin/systemctl start  ntpd.service
[root@ip-172-31-4-12 ~]# service nscd status
Redirecting to /bin/systemctl status  nscd.service
● nscd.service - Name Service Cache Daemon
   Loaded: loaded (/usr/lib/systemd/system/nscd.service; disabled; vendor preset: disabled)
   Active: active (running) since Tue 2017-10-17 12:37:24 UTC; 21s ago
  Process: 9376 ExecStart=/usr/sbin/nscd $NSCD_OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 9377 (nscd)
   CGroup: /system.slice/nscd.service
           └─9377 /usr/sbin/nscd
---
Oct 17 12:37:24 ip-172-31-4-12 nscd[9377]: 9377 monitoring directory `/etc` (2)
Oct 17 12:37:24 ip-172-31-4-12 nscd[9377]: 9377 monitoring file `/etc/resolv.c...)
Oct 17 12:37:24 ip-172-31-4-12 nscd[9377]: 9377 monitoring directory `/etc` (2)
Oct 17 12:37:24 ip-172-31-4-12 nscd[9377]: 9377 monitoring file `/etc/services...)
Oct 17 12:37:24 ip-172-31-4-12 nscd[9377]: 9377 monitoring directory `/etc` (2)
Oct 17 12:37:24 ip-172-31-4-12 nscd[9377]: 9377 disabled inotify-based monitor...y
Oct 17 12:37:24 ip-172-31-4-12 nscd[9377]: 9377 stat failed for file `/etc/net...y
Oct 17 12:37:24 ip-172-31-4-12 nscd[9377]: 9377 Access Vector Cache (AVC) started
Oct 17 12:37:24 ip-172-31-4-12 systemd[1]: Started Name Service Cache Daemon.
Oct 17 12:37:43 ip-172-31-4-12 nscd[9377]: 9377 checking for monitored file `/...y
Hint: Some lines were ellipsized, use -l to show in full.
[root@ip-172-31-4-12 ~]#  service ntpd status
Redirecting to /bin/systemctl status  ntpd.service
● ntpd.service - Network Time Service
   Loaded: loaded (/usr/lib/systemd/system/ntpd.service; disabled; vendor preset: disabled)
   Active: active (running) since Tue 2017-10-17 12:37:38 UTC; 15s ago
  Process: 9417 ExecStart=/usr/sbin/ntpd -u ntp:ntp $OPTIONS (code=exited, status=0/SUCCESS)
 Main PID: 9418 (ntpd)
   CGroup: /system.slice/ntpd.service
           └─9418 /usr/sbin/ntpd -u ntp:ntp -g
---
Oct 17 12:37:38 ip-172-31-4-12 ntpd[9418]: Listen and drop on 1 v6wildcard :: ...3
Oct 17 12:37:38 ip-172-31-4-12 ntpd[9418]: Listen normally on 2 lo 127.0.0.1 U...3
Oct 17 12:37:38 ip-172-31-4-12 ntpd[9418]: Listen normally on 3 eth0 172.31.4....3
Oct 17 12:37:38 ip-172-31-4-12 ntpd[9418]: Listen normally on 4 lo ::1 UDP 123
Oct 17 12:37:38 ip-172-31-4-12 ntpd[9418]: Listen normally on 5 eth0 fe80::8e2...3
Oct 17 12:37:38 ip-172-31-4-12 ntpd[9418]: Listening on routing socket on fd #...s
Oct 17 12:37:38 ip-172-31-4-12 ntpd[9418]: 0.0.0.0 c016 06 restart
Oct 17 12:37:38 ip-172-31-4-12 ntpd[9418]: 0.0.0.0 c012 02 freq_set kernel 0.0...M
Oct 17 12:37:38 ip-172-31-4-12 ntpd[9418]: 0.0.0.0 c011 01 freq_not_set
Oct 17 12:37:45 ip-172-31-4-12 ntpd[9418]: 0.0.0.0 c614 04 freq_mode
Hint: Some lines were ellipsized, use -l to show in full.









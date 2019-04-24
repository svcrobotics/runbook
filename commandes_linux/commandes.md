
# Commandes Linux



```
df -h
```

    Sys. de fichiers Taille Utilisé Dispo Uti% Monté sur
    udev               1,9G       0  1,9G   0% /dev
    tmpfs              393M     13M  381M   4% /run
    /dev/sda1           71G     16G   52G  24% /
    tmpfs              2,0G    8,0M  2,0G   1% /dev/shm
    tmpfs              5,0M       0  5,0M   0% /run/lock
    tmpfs              2,0G       0  2,0G   0% /sys/fs/cgroup
    tmpfs              393M     12K  393M   1% /run/user/130
    tmpfs              393M    120K  393M   1% /run/user/0



```
ps aux
```

```
top
```


```
who
```

    root     :1           2019-04-23 21:14 (:1)



```python
!uptime
```

     00:39:01 up  3:24,  1 user,  load average: 0,10, 0,16, 0,17



```python
!fdisk -l
```

    [1mDisk /dev/sda: 80 GiB, 85899345920 bytes, 167772160 sectors
    [0mDisk model: VMware Virtual S
    Units: sectors of 1 * 512 = 512 bytes
    Sector size (logical/physical): 512 bytes / 512 bytes
    I/O size (minimum/optimal): 512 bytes / 512 bytes
    Disklabel type: dos
    Disk identifier: 0xa8f4a4fd
    
    [1mDevice[0m     [1mBoot[0m [1m    Start[0m [1m      End[0m [1m  Sectors[0m [1mSize[0m [1mId[0m [1mType[0m
    /dev/sda1  *         2048 150996991 150994944  72G 83 Linux
    /dev/sda2       150999038 167770111  16771074   8G  5 Extended
    /dev/sda5       150999040 167770111  16771072   8G 82 Linux swap / Solaris



```python
!free -mt
```

                  total        used        free      shared  buff/cache   available
    Mem:           3924        2749         320          56         854         882
    Swap:          8188          99        8089
    Total:        12113        2848        8410



```python
!ping -c 3 svcrobotics.com
```

    PING svcrobotics.com (172.16.76.209) 56(84) bytes of data.
    64 bytes from svcrobotics.com (172.16.76.209): icmp_seq=1 ttl=64 time=1.45 ms
    64 bytes from svcrobotics.com (172.16.76.209): icmp_seq=2 ttl=64 time=1.40 ms
    64 bytes from svcrobotics.com (172.16.76.209): icmp_seq=3 ttl=64 time=1.46 ms
    
    --- svcrobotics.com ping statistics ---
    3 packets transmitted, 3 received, 0% packet loss, time 6ms
    rtt min/avg/max/mdev = 1.399/1.438/1.462/0.027 ms



```python
!vmstat
```

    procs -----------memory---------- ---swap-- -----io---- -system-- ------cpu-----
     r  b   swpd   free   buff  cache   si   so    bi    bo   in   cs us sy id wa st
     1  0 101632 289020  74680 798516    0    2    21    23  237  426  1  2 97  0  0



```python
!netstat
```


```python
!traceroute kali.org
```

    traceroute to kali.org (192.124.249.10), 30 hops max, 60 byte packets
     1  _gateway (172.16.76.1)  3.064 ms  3.082 ms  3.237 ms
     2  172.16.0.1 (172.16.0.1)  5.954 ms  6.154 ms  6.291 ms
     3  192.168.19.2 (192.168.19.2)  6.341 ms  6.441 ms  6.491 ms
     4  * * *
     5  * * *
     6  * * *
     7  * * *
     8  * * *
     9  * * *
    10  * * *
    11  * * *
    12  * * *
    13  * * *
    14  * * *
    15  * * *
    16  * * *
    17  * * *
    18  * * *
    19  * * *
    20  * * *
    21  * * *
    22  * * *
    23  * * *
    24  * * *
    25  * * *
    26  * * *
    27  * * *
    28  * * *
    29  * * *
    30  * * *



```python

```


## runbook/troubleshooting/wordpress_is_down.md

Si la sonde **PING WordPress Server** affiche:

```
CRITICAL - Plugin timed out
```

Alors allez sur le serveur **svcrobotics.com**

- login: root
- passwd: Victor@1972

et faire un **ifconfig** pour récuperer l'adresse ip du serveur, puis entrez l'adresse ip dans le fichiers **/etc/hosts** du serveur Nagios.

```
root@svcrobotics:~# ifconfig
eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 172.16.140.209  netmask 255.255.255.0  broadcast 172.16.140.255
        inet6 fe80::20c:29ff:fe84:9421  prefixlen 64  scopeid 0x20<link>
        ether 00:0c:29:84:94:21  txqueuelen 1000  (Ethernet)
        RX packets 30800  bytes 41975199 (40.0 MiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 16782  bytes 1023346 (999.3 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
        inet 127.0.0.1  netmask 255.0.0.0
        inet6 ::1  prefixlen 128  scopeid 0x10<host>
        loop  txqueuelen 1000  (Boucle locale)
        RX packets 20  bytes 1116 (1.0 KiB)
        RX errors 0  dropped 0  overruns 0  frame 0
        TX packets 20  bytes 1116 (1.0 KiB)
        TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
```


```bash
%%bash

cat /etc/hosts
```

    127.0.0.1	localhost
    127.0.1.1	kali
    172.16.90.209 svcrobotics.com
    
    # The following lines are desirable for IPv6 capable hosts
    ::1     localhost ip6-localhost ip6-loopback
    ff02::1 ip6-allnodes
    ff02::2 ip6-allrouters


Après modification:


```bash
%%bash

cat /etc/hosts
```

    127.0.0.1	localhost
    127.0.1.1	kali
    172.16.140.209 svcrobotics.com
    
    # The following lines are desirable for IPv6 capable hosts
    ::1     localhost ip6-localhost ip6-loopback
    ff02::1 ip6-allnodes
    ff02::2 ip6-allrouters


Redémarrer le serveur Nagios


```bash
%%bash

systemctl restart nagios.service
```

Problème résolu si Nagios affiche

```
PING OK - Paquets perdus = 0%, RTA = 1.54 ms
```

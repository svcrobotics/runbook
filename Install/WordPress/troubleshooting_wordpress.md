# Identifions les sources de ralentissement de notre site web WordPress

## Axes de recherche, causes possibles

1. Problèmes liés à Apache2

   - Vérifions l'état du serveur

   ```bash
   root@svcrobotics:~# systemctl status apache2
   ● apache2.service - The Apache HTTP Server
      Loaded: loaded (/lib/systemd/system/apache2.service; enabled; vendor preset: 
      Active: active (running) since Thu 2019-04-25 21:18:55 CEST; 3h 12min ago
        Docs: https://httpd.apache.org/docs/2.4/
     Process: 4392 ExecStart=/usr/sbin/apachectl start (code=exited, status=0/SUCCE
    Main PID: 4536 (apache2)
       Tasks: 12 (limit: 4655)
      Memory: 131.6M
      CGroup: /system.slice/apache2.service
              ├─4536 /usr/sbin/apache2 -k start
              ├─4583 /usr/sbin/apache2 -k start
              ├─4587 /usr/sbin/apache2 -k start
              ├─4588 /usr/sbin/apache2 -k start
              ├─4590 /usr/sbin/apache2 -k start
              ├─4591 /usr/sbin/apache2 -k start
              ├─4592 /usr/sbin/apache2 -k start
              ├─6995 /usr/sbin/apache2 -k start
              ├─6996 /usr/sbin/apache2 -k start
              ├─6997 /usr/sbin/apache2 -k start
              ├─6998 /usr/sbin/apache2 -k start
              └─6999 /usr/sbin/apache2 -k start
   
   avril 25 21:18:55 svcrobotics.com systemd[1]: Starting The Apache HTTP Server...
   lines 1-23
   
   ```

   

2. Problèmes liés à Mysql

   - Pouvons-nous nous connecter à la base de données?

   ```bash
   root@svcrobotics:~# mysql -h localhost -u wordpress -pVictor@1972 wordpress
   Reading table information for completion of table and column names
   You can turn off this feature to get a quicker startup with -A
   
   Welcome to the MariaDB monitor.  Commands end with ; or \g.
   Your MariaDB connection id is 307
   Server version: 10.3.13-MariaDB-2 Debian buildd-unstable
   
   Copyright (c) 2000, 2018, Oracle, MariaDB Corporation Ab and others.
   
   Type 'help;' or '\h' for help. Type '\c' to clear the current input statement.
   
   MariaDB [wordpress]> 
   
   ```

   

3. Problèmes liés à WordPress

   - Vérifions les faiblesses de notre site (scan de vulnérabilités)

   ```bash
   root@svcrobotics:~# wpscan --url http://svcrobotics.com
   _______________________________________________________________
           __          _______   _____
           \ \        / /  __ \ / ____|
            \ \  /\  / /| |__) | (___   ___  __ _ _ __ ®
             \ \/  \/ / |  ___/ \___ \ / __|/ _` | '_ \
              \  /\  /  | |     ____) | (__| (_| | | | |
               \/  \/   |_|    |_____/ \___|\__,_|_| |_|
   
           WordPress Security Scanner by the WPScan Team
                          Version 3.5.1
             Sponsored by Sucuri - https://sucuri.net
         @_WPScan_, @ethicalhack3r, @erwan_lr, @_FireFart_
   _______________________________________________________________
   
   [+] URL: http://svcrobotics.com/
   [+] Started: Fri Apr 26 01:13:00 2019
   
   Interesting Finding(s):
   
   [+] http://svcrobotics.com/
    | Interesting Entry: Server: Apache/2.4.38 (Debian)
    | Found By: Headers (Passive Detection)
    | Confidence: 100%
   
   [+] http://svcrobotics.com/xmlrpc.php
    | Found By: Direct Access (Aggressive Detection)
    | Confidence: 100%
    | References:
    |  - http://codex.wordpress.org/XML-RPC_Pingback_API
    |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_ghost_scanner
    |  - https://www.rapid7.com/db/modules/auxiliary/dos/http/wordpress_xmlrpc_dos
    |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_xmlrpc_login
    |  - https://www.rapid7.com/db/modules/auxiliary/scanner/http/wordpress_pingback_access
   
   [+] http://svcrobotics.com/readme.html
    | Found By: Direct Access (Aggressive Detection)
    | Confidence: 100%
   
   [+] http://svcrobotics.com/wp-cron.php
    | Found By: Direct Access (Aggressive Detection)
    | Confidence: 60%
    | References:
    |  - https://www.iplocation.net/defend-wordpress-from-ddos
    |  - https://github.com/wpscanteam/wpscan/issues/1299
   
   [+] WordPress version 5.0.3 identified (Insecure, released on 2019-01-09).
    | Detected By: Rss Generator (Passive Detection)
    |  - http://svcrobotics.com/index.php/feed/, <generator>https://wordpress.org/?v=5.0.3</generator>
    |  - http://svcrobotics.com/index.php/comments/feed/, <generator>https://wordpress.org/?v=5.0.3</generator>
    |
    | [!] 1 vulnerability identified:
    |
    | [!] Title: WordPress 3.9-5.1 - Comment Cross-Site Scripting (XSS)
    |     Fixed in: 5.04
    |     References:
    |      - https://wpvulndb.com/vulnerabilities/9230
    |      - https://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2019-9787
    |      - https://github.com/WordPress/WordPress/commit/0292de60ec78c5a44956765189403654fe4d080b
    |      - https://wordpress.org/news/2019/03/wordpress-5-1-1-security-and-maintenance-release/
    |      - https://blog.ripstech.com/2019/wordpress-csrf-to-rce/
   
   [+] WordPress theme in use: twentynineteen
    | Location: http://svcrobotics.com/wp-content/themes/twentynineteen/
    | Last Updated: 2019-02-21T00:00:00.000Z
    | Readme: http://svcrobotics.com/wp-content/themes/twentynineteen/readme.txt
    | [!] The version is out of date, the latest version is 1.3
    | Style URL: http://svcrobotics.com/wp-content/themes/twentynineteen/style.css?ver=1.2
    | Style Name: Twenty Nineteen
    | Style URI: https://github.com/WordPress/twentynineteen
    | Description: Our 2019 default theme is designed to show off the power of the block editor. It features custom sty...
    | Author: the WordPress team
    | Author URI: https://wordpress.org/
    |
    | Detected By: Css Style (Passive Detection)
    |
    | Version: 1.2 (80% confidence)
    | Detected By: Style (Passive Detection)
    |  - http://svcrobotics.com/wp-content/themes/twentynineteen/style.css?ver=1.2, Match: 'Version: 1.2'
   
   [+] Enumerating All Plugins (via Passive Methods)
   
   [i] No plugins Found.
   
   [+] Enumerating Config Backups (via Passive and Aggressive Methods)
    Checking Config Backups - Time: 00:00:00 <========> (21 / 21) 100.00% Time: 00:00:00
   
   [i] Config Backup(s) Identified:
   
   [+] http://svcrobotics.com/wp-config.php~
    | Detected By: Direct Access (Aggressive Detection)
   
   
   [+] Finished: Fri Apr 26 01:13:01 2019
   [+] Requests Done: 24
   [+] Cached Requests: 34
   [+] Data Sent: 4.771 KB
   [+] Data Received: 6.942 KB
   [+] Memory used: 161.969 MB
   [+] Elapsed time: 00:00:01
   root@svcrobotics:~# 
   ```

   

4. Problèmes liés à PHP

   - Version de PHP?

   ```bash
   root@svcrobotics:~# php -v
   PHP 7.3.3-1 (cli) (built: Mar  7 2019 19:43:34) ( NTS )
   Copyright (c) 1997-2018 The PHP Group
   Zend Engine v3.3.3, Copyright (c) 1998-2018 Zend Technologies
       with Zend OPcache v7.3.3-1, Copyright (c) 1999-2018, by Zend Technologies
   root@svcrobotics:~# 
   ```

   

5. Problèmes liées au DNS

   - La résolution de nom de domaines fonctionne t-elle?

   ```bash
   root@svcrobotics:~# nslookup kali.org
   Server:		172.16.188.1
   Address:	172.16.188.1#53
   
   Non-authoritative answer:
   Name:	kali.org
   Address: 192.124.249.10
   
   ```

   

6. Problèmes liés à la machine

   - Quantité de RAM utilisée?

   ```bash
   root@svcrobotics:~# free -m
                 total        used        free      shared  buff/cache   available
   Mem:           3924        1240        1606          37        1077        2381
   Swap:          8188           0        8188
   
   ```


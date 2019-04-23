
# Installer WordPress sur une Kali Linux


```
apt update
apt install wordpress curl apache2 mariadb-server
```

### Secure your MySQL installation with this command 

```
root@kali:~# mysql_secure_installation

NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none): 
ERROR 2002 (HY000): Can't connect to local MySQL server through socket '/var/run/mysqld/mysqld.sock' (2)
Enter current password for root (enter for none): 
Aborting!

Cleaning up...
root@kali:~# systemctl status mariadb
● mariadb.service - MariaDB 10.3.13 database server
   Loaded: loaded (/lib/systemd/system/mariadb.service; disabled; vendor preset: disabled)
   Active: inactive (dead)
     Docs: man:mysqld(8)
           https://mariadb.com/kb/en/library/systemd/
root@kali:~# systemctl enable mariadb
Created symlink /etc/systemd/system/mysql.service → /lib/systemd/system/mariadb.service.
Created symlink /etc/systemd/system/mysqld.service → /lib/systemd/system/mariadb.service.
Created symlink /etc/systemd/system/multi-user.target.wants/mariadb.service → /lib/systemd/system/mariadb.service.
root@kali:~# systemctl start mariadb
root@kali:~# mysql_secure_installation

NOTE: RUNNING ALL PARTS OF THIS SCRIPT IS RECOMMENDED FOR ALL MariaDB
      SERVERS IN PRODUCTION USE!  PLEASE READ EACH STEP CAREFULLY!

In order to log into MariaDB to secure it, we'll need the current
password for the root user.  If you've just installed MariaDB, and
you haven't set the root password yet, the password will be blank,
so you should just press enter here.

Enter current password for root (enter for none): 
OK, successfully used password, moving on...

Setting the root password ensures that nobody can log into the MariaDB
root user without the proper authorisation.

Set root password? [Y/n] Y
New password: 
Re-enter new password: 
Password updated successfully!
Reloading privilege tables..
 ... Success!


By default, a MariaDB installation has an anonymous user, allowing anyone
to log into MariaDB without having to have a user account created for
them.  This is intended only for testing, and to make the installation
go a bit smoother.  You should remove them before moving into a
production environment.

Remove anonymous users? [Y/n] Y
 ... Success!

Normally, root should only be allowed to connect from 'localhost'.  This
ensures that someone cannot guess at the root password from the network.

Disallow root login remotely? [Y/n] Y
 ... Success!

By default, MariaDB comes with a database named 'test' that anyone can
access.  This is also intended only for testing, and should be removed
before moving into a production environment.

Remove test database and access to it? [Y/n] Y
 - Dropping test database...
 ... Success!
 - Removing privileges on test database...
 ... Success!

Reloading the privilege tables will ensure that all changes made so far
will take effect immediately.

Reload privilege tables now? [Y/n] Y
 ... Success!

Cleaning up...

All done!  If you've completed all of the above steps, your MariaDB
installation should now be secure.

Thanks for using MariaDB!
root@kali:~# 
```



### Basic Installation guide

#### Create a site

```
nano /etc/apache2/sites-available/wp.conf
```

Add this content, and replace **example.com** by your own domain: 

```
<VirtualHost *:80>
        ServerName svcrobotics.com

        ServerAdmin webmaster@example.com
        DocumentRoot /usr/share/wordpress

        Alias /wp-content /var/lib/wordpress/wp-content
        <Directory /usr/share/wordpress>
            Options FollowSymLinks
            AllowOverride Limit Options FileInfo
            DirectoryIndex index.php
            Require all granted
        </Directory>
        <Directory /var/lib/wordpress/wp-content>
            Options FollowSymLinksa2
            Require all granted
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined

</VirtualHost>
```

#### Disable default Virtual Host, and enable the site


```
a2dissite 000-default
a2ensite wp
```

Reload the webserver

```
systemctl reload apache2
```

Create `/etc/wordpress/config-$DM.php`. `$DM` is the domain name e.g. if the fully qualified domain name is `svcrobotics.com`, create one of the following files: 

- `/etc/wordpress/config-svcrobotics.com.php` (this is the default, use it if you are unsure) 


WordPress  searches in the above order and uses the first configuration file it  can find. The domain name is taken from the HTTP-Request of your  browser. That way you may be able to define different configuration  files for different domains you are hosting. 

```
nano /etc/wordpress/config-svcrobotics.com.php
```

Add this content:- 

Afficher/masquer les numéros de lignes

```
   1 <?php
   2 define('DB_NAME', 'wordpress');
   3 define('DB_USER', 'wordpress');
   4 define('DB_PASSWORD', 'Victor@1972');
   5 define('DB_HOST', 'localhost');
   6 define('WP_CONTENT_DIR', '/var/lib/wordpress/wp-content');
   7 ?>
```

![<!>](https://wiki.debian.org/htdocs/debwiki/img/attention.png) replace `password` with a suitably secure password 

Create a file to hold the database creation instructions 

```
nano ~/wp.sql
```

Add this content:- 

Afficher/masquer les numéros de lignes

```
   1 CREATE DATABASE wordpress;
   2 GRANT SELECT,INSERT,UPDATE,DELETE,CREATE,DROP,ALTER
   3 ON wordpress.*
   4 TO wordpress@localhost
   5 IDENTIFIED BY 'password';
   6 FLUSH PRIVILEGES;
```

![<!>](https://wiki.debian.org/htdocs/debwiki/img/attention.png) replace `password` with your "suitably secure password" 

Create the database:- 

```
cat ~/wp.sql | mysql --defaults-extra-file=/etc/mysql/debian.cnf
```

Navigate to the wordpress directory in browser e.g.:- `http://svcrobotics.com/wp` which redirects to `http://svcrobotics.com/wp/wp-admin/install.php` where you'll see the "classic" wordpress 5 minute install page (actually a 5 second install thanks to the Debian packaging) 



```python

```

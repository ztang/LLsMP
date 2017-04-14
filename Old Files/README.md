## LLsMP 0.6

### About

This LLsMP version is created by the original maintainer(@w0w.me). Now he has already stopped this project.

Here is all the source codes from Google Codes.

Source: https://code.google.com/archive/p/llsmp/

### Installation

#### CentOS

PHP 5.2:

```shell
wget http://llsmp.googlecode.com/files/llsmp0.6_centos.tar.gz;tar zxvf llsmp0.6_centos.tar.gz;cd centos;sh install.sh
```

PHP 5.3:

```shell
wget http://llsmp.googlecode.com/files/llsmp0.6_centos.tar.gz;tar zxvf llsmp0.6_centos.tar.gz;cd centos;sh install.sh php5.3
```

#### Debian

PHP 5.2:

```shell
wget http://llsmp.googlecode.com/files/llsmp0.6_debian.tar.gz;tar zxvf llsmp0.6_debian.tar.gz;cd debian;sh install.sh
```

PHP 5.3:

```shell
wget http://llsmp.googlecode.com/files/llsmp0.6_debian.tar.gz;tar zxvf llsmp0.6_debian.tar.gz;cd debian;sh install.sh php5.3
```

#### Ubuntu

PHP 5.2:

```shell
wget http://llsmp.googlecode.com/files/llsmp0.6_ubuntu.tar.gz;tar zxvf llsmp0.6_ubuntu.tar.gz;cd ubuntu;sh install.sh
```

PHP 5.3:

```shell
wget http://llsmp.googlecode.com/files/llsmp0.6_ubuntu.tar.gz;tar zxvf llsmp0.6_ubuntu.tar.gz;cd ubuntu;sh install.sh php5.3
```

### Addon

- Install eAccelerator : sh /root/llsmp/eaccelerator.sh
- Install Zend Optimizer : sh /root/llsmp/zend_optimizer.sh
- Install ionCube Loader : sh /root/llsmp/ioncube.sh
- Install Google Performace Tools : sh /root/llsmp/perftools.sh
- Install FTP(vsftpd) : sh /root/llsmp/vsftpd.sh
- Install Nginx front end : sh /root/llsmp/nginx.sh

### Command

- Create Litespeed Virtual Host : sh /root/llsmp/vhost.sh
- Add FTP account : sh /root/llsmp/vsftpd.sh
- **IMPORTANT** Modify the permission of virtual host: chown -R nobody:nobody /home/wwwroot/域名/html
- Create Nginx Virtual Host : sh /root/llsmp/nginx.sh
- Backup : sh /root/llsmp/backup.sh
- Restart Litespeed : /etc/init.d/lsws restart
- Restart MySQL : /etc/init.d/mysql(d) restart
- Restart Nginx : /etc/init.d/nginx restart

### Directory

- Litespeed web manager : http://{ip}:7080
- phpMyAdmin : http://{ip}/phpmyadmin/
- php.ini directory : /usr/local/lsws/lsphp5/lib/php.ini
- MySQL configuration file my.cnf : /etc/my.cnf (Centos) | /etc/mysql/my.cnf (Debian/Ubuntu)
- Nginx configuration directory: /etc/nginx/nginx.conf 及 /etc/nginx/conf.d/下
- Virtual host directory: /home/wwwroot
- LLsMP installation log: /root/llsmp/install.log

### Known Issue

#### 1. Can not install LLsMP on Debian over KVM

```shell
cp: cannot create regular file `/usr/local/lsws/DEFAULT/html/installlog.html': No such file or directory
sed: can't read /usr/local/lsws/DEFAULT/html/installlog.html: No such file or directory
sed: can't read /usr/local/lsws/DEFAULT/html/installlog.html: No such file or directory
sed: can't read /usr/local/lsws/DEFAULT/html/installlog.html: No such file or directory
sed: can't read /usr/local/lsws/DEFAULT/html/installlog.html: No such file or directory
```

#### 2. 2002 Error

Please restart MySQL manually:

```shell
/etc/init.d/mysql start
```

#### 3. Litespeed and MySQL do not start with system reboot

Solutions:

Debian/Ubuntu:

```shell
update-rc.d lsws defaults
update-rc.d mysql defaults
```

CentOS:

```shell
chkconfig –level 345 lsws on
chkconfig –level 345 mysql on
```

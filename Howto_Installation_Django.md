# How to Set-Up a Basic Python-Django Stack
----------------------------------------------------------------

## Make Sure Your System is Up to Date

**In this tutorial we were using a remote server with Debian 10 installed**

```Shell Session
sudo apt-get update
```

## Install Apache2 Plus Mod-WSGI Module

```Shell Session
$ sudo apt install apache2 apache2-dev
$ sudo apt-get install libapache2-mod-wsgi-py3
```

## Check Apache
 ### Start Apache
```Shell Session
$ sudo service apache2 start
```
###Check Server External IP to see if Apache is Running
```Shell Session
$ sudo service apache2 stop
```

## Install Python & Pip
**Debian 10 already has Python 3, so we just needed to update and install pip**
```Shell Session
$ sudo apt install python3-pip
```

## Check Pip Version
```Shell Session
$ sudo pip3 version
```

##Install Django
```Shell Session
$ sudo pip3 install django --upgrade
$ sudo python3 -m django --version
```

##Install MariaDB
**The first shell command (apt-get install) installs mariadb and necessary modules.**
** The second command helps check database security by helping create a root password (make sure to save this) and checking security items**
```Shell Session
$ sudo apt-get install mariadb-server libmariadbclient-dev libssl-dev
$ sudo mysql_secure_installation
```

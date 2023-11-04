# MySQL - TCP 3306

## Pre Enumeration

### Nmap Scanning

```
nmap -sV -Pn -vv --script=mysql-audit,mysql-databases,mysql-dump-hashes,mysql-empty-password,mysql-enum,mysql-info,mysql-query,mysql-users,mysql-variables,mysql-vuln-cve2012-2122 $ip -p 3306
```

```
nmap -sV -Pn -vv -script=mysql* $ip -p 3306
```

### If can access

**If Mysql is running as root and you have access, you can run commands:**

```
mysql> select do_system('id');
mysql> \! sh
```

### Always test root:root credential

```
mysql --host=$ip -u root -p
mysql -h $ip -u wpmaster@localhost -p
mysql -h $ip -u root@localhost
mysql -h $ip -u ""@localhost
telnet $ip 3306
```

### Username Enumeration

```
nmap –script=mysql-enum –script-args userdb=<username lists> $ip
```

### Connection

```
mysql -h $ip -P 3306
mysql -u <user> -p <password>
mysql -u root -p
```

## SQL Command

**Cheatsheet :**&#x20;

{% embed url="https://www.mysqltutorial.org/mysql-cheat-sheet.aspx" %}

## Post Enumeration

### MySQL server configuration file&#x20;

**1 .** **Unix**

```
my.cnf
/etc/mysql
/etc/my.cnf
/etc/mysql/my.cnf
/var/lib/mysql/my.cnf
~/.my.cnf
/etc/my.cnf
```

**2 . Windows**

```
config.ini
my.ini
windows\my.ini
winnt\my.ini
<InstDir>/mysql/data/
```

### Command History

```
~/.mysql.history
```

### Log Files

```
connections.log
update.log
common.log
```

### Finding Passwords to MySQL

* You might gain access to a shell by uploading a reverse-shell. And then you need to escalate your privilege.
* Look into the database and see what users and passwords that are available.

```
/var/www/html/configuration.php
```

### Getting all the information from inside the database

```
mysqldump -u admin -p admin --all-databases --skip-lock-tables 
```


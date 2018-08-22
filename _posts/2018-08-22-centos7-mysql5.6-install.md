---
layout: post
title: "mysql5.6的安装"
description: ""
category: linux
tags: [shell]
theme :
    name: leopardpan
---
{% include JB/setup %}

### CENTOS7使用yum安装mysql5.6

#####一、检查系统是否安装其他版本的MYSQL数据

```
#yum list installed | grep mysql
#yum -y remove mysql-libs.x86_64
```

#####二、安装及配置

```
# wget http://repo.mysql.com/mysql-community-release-el6-5.noarch.rpm
# rpm -ivh mysql-community-release-el6-5.noarch.rpm
# yum repolist all | grep mysql
```

#####安装mysql
```
# yum install mysql-community-server -y
```

#####设置开机启动
```
# chkconfig --list | grep mysqld
# chkconfig mysqld on
```

#####设置远程root
```
# service mysqld start
# mysql_secure_installation
# mysql -uroot -p
# mysql> GRANT ALL PRIVILEGES ON *.* TO 'root'@'%' IDENTIFIED BY '你设置的密码' WITH GRANT OPTION;
# mysql> flush privileges;
```



---
layout: post
title: "CentOS下如何完全干净卸载MySQL"
description: ""
category: linux
tags: [mysql]
theme :
    name: leopardpan
---
{% include JB/setup %}

### CentOS下如何完全干净卸载MySQL

##### yum方式安装的MySQL
```
#yum remove mysql mysql-server mysql-libs compat-mysql51
#rm -rf /var/lib/mysql
#rm /etc/my.cnf

#rpm -qa|grep mysql
#yum remove + 【名字】
```

#### rpm方式安装的MySQL
```
#rpm -qa | grep -i mysql
#MySQL-server-5.6.17-1.el6.i686
#MySQL-client-5.6.17-1.el6.i686

#rpm -e MySQL-server-5.6.17-1.el6.i686
#rpm -e MySQL-client-5.6.17-1.el6.i686

#chkconfig --list | grep -i mysql
#chkconfig --del mysql

#whereis mysql 或者 find / -name mysql
#rm -rf /usr/lib/mysql
#rm -rf /usr/share/mysql
#rm -rf /usr/my.cnf
```
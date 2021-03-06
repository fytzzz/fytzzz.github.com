---
layout: post
title: "脚本控制两个tomcat的重启"
description: ""
category: linux
tags: [shell]
theme :
    name: leopardpan
---
{% include JB/setup %}

### Tomcat的重启shell脚本

```
    #!/bin/bash
    if [ $# -lt 1 ];then
    echo "你输入的命令不正确，请出入 ./startup.sh -h 查看命名。"
    exit -1
    fi
    
    if [ $1 = "-h" ]; then
    cat<<HELP
          ren -- '命令帮助提示''
    
          USAGE: ./startup.sh -h  #帮助命令
          USAGE: ./startup.sh -s tomcat1 #启动tomcat1-8686
          USAGE: ./startup.sh -s tomcat2 #启动tomcat2-8585
          USAGE: ./startup.sh -s nginx #启动nginx
          USAGE: ./startup.sh -s nginx #启动nginx
          USAGE: ./startup.sh -s all #启动全部
    HELP
          exit 0
    fi
    
    if [ $# -eq 1 ];then
    echo "你输入的命令不正确，请出入 ./startup.sh -h 查看命名。"
    exit -1
    fi
    
    #checkPID("tomcat")
    
    tomcat1_home=/usr/local/apache-tomcat-6.0.29
    tomcat2_home=/usr/local/apache-tomcat-6.0.29_backup
    nginx_home=/usr/local/nginx
    
    function all(){
        #命令1-启动系统
        tomcat1
        tomcat2
    }
    
    function tomcat1(){
        #命令2-重启tomcat1-8686
        pidlist=`ps -ef|grep apache-tomcat-6.0.29|grep -v "grep"|awk '{print $2}'`
        if [ "$pidlist" = "" ]
        then
            echo "no tomcat pid alive!"
        else
            echo "tomcat Id list :$pidlist"
            kill -9 $pidlist
            echo "KILL $pidlist:"
            echo "service stop success"
        fi
        echo "start tomcat1"
        #删除tomcat的临时目录
        rm -rf $tomcat1_home/work/*
        $tomcat1_home/bin/startup.sh;
        #tail -f $tomcat1_home/logs/catalina.out
        echo "tomcat1-8686重启完成..."
    }
    
    function tomcat2(){
        #命令2-重启tomcat1-8585
        pidlist=`ps -ef|grep apache-tomcat-6.0.29_backup|grep -v "grep"|awk '{print $2}'`
        if [ "$pidlist" = "" ]
        then
            echo "no tomcat pid alive!"
        else
            echo "tomcat Id list :$pidlist"
            kill -9 $pidlist
            echo "KILL $pidlist:"
            echo "service stop success"
        fi
        echo "start tomcat2"
        #删除tomcat的临时目录
        rm -rf $tomcat2_home/work/*
        $tomcat2_home/bin/startup.sh;
        #tail -f $tomcat2_home/logs/catalina.out
        echo "tomcat1-8585重启完成..."
    }
    
    if [ $1 = '-s' ]; then
        if [ $2 = 'all' ];then
            all
        elif [ $2 = 'tomcat1' ]; then
            tomcat1
        elif [ $2 = 'tomcat2' ]; then
            tomcat2
        elif [ $2 = 'nginx' ]; then
            #命令4-nginx
            $nginx_home/sbin/nginx -s reload
            echo "nginx reload complete!"
        fi
    else
        echo "输入的命令格式不正确。"
    fi
    exit 0

```
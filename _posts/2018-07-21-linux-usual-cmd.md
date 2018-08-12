---
layout: post
title: "Linux 常用命令"
description: ""
category: linux
tags: [指令]
theme :
    name: leopardpan
---

### Linux 常用命令

Linux 系统常用命令格式：

command [option] [argument1] [argument2] ...

其中option以“-”开始，多个option可用一个“-”连起来，如“ls -l -a” 与“ls -la”的效果是一样的。 根据命令的不同，参数分为可选的或必须的；所有的命令从标准输入接受输入，输出 结果显示在标准输出，而错误信息则显示在标准错误输出设备。可使用重定向功能对 这些设备进行重定向。

命令在正常执行结果后返回一个0值，如果命令出错可未完全完成，则返回一个 非零值(在shell中可用变量$?查看)。 在shell script中可用此返回值作为控制逻辑 的一部分。

帮助命令:

man 获取相关命令的帮助信息

例如：man dir 可以获取关于dir的使用信息。

info 获取相关命令的详细使用方法

例如：info info 可以获取如何使用info的详细信息。

文件操作：

cat 显示文件内容和合并多个文件

clear 清屏

chattr 改变文件属性

chgrp 改变文件组权

chmod 改变文件或目录的权限

chown 改变文件的属权

comm 比较两个已排过序的文件

cp 将文件拷贝至另一文件

dd 从指定文件读取数据写到指定文件

df 报告磁盘空间使用情况

diff 比较两个文本文件，列出行不同之处

du 统计目录／文件所占磁盘空间的大小

file 辨识文件类型

emacs 功能强大的编辑环境

find 搜索文件并执行指定操作(find2)

grep 按给定模式搜索文件内容

head 显示指定文件的前若干行

less 按页显示文件

ln 创建文件链接

locate 查找符合条件的文件

more 在终端屏幕按帧显示文本文件

mv 文件或目录的移动或更名

rm/rmdir 删除文件／目录

sed 利用script来处理文本文件

sort 对指定文件按行进行排序

tail 显示指定文件的最后部分

touch 创建文件

tr 转换字符

vi 全屏编辑器

wc 显示指定文件中的行数，词数或字符数

which 在环境变量 $PATH 设置的目录里查找符合条件的文件

压缩与备份:

bzip2/bunzip2 .bz2文件的压缩/解压缩程序

cpio 备份文件

dump 备份文件系统

gzip/gunzip .gz文件的压缩/解压缩程序

gzexe 压缩可执行文件

restore 还原由倾倒(Dump)操作所备份下来的文件或整个文件系统(一个分区)

tar 将若干文件存档或读取存档文件

unarj 解压缩.arj文件

zip/unzip 压缩/解压缩 zip文件

zipinfo 列出zip压缩文件的详细信息

磁盘操作:

cd/pwd 切换目录/显示当前工作目录

df 显示磁盘的相关信息

du 显示目录或文件的大小

e2fsck 检查ext2/ext3文件系统的正确性

fdisk 对硬盘进行分区

fsck 检查文件系统并尝试修复错误

losetup 设置循环设备

ls 列出目录内容

mkdir 创建目录

mformat 对MS-DOS文件系统的磁盘进行格式化

mkbootdisk 建立目前系统的启动盘

mke2fs 建立ext2文件系统

mkisofs 制作iso光盘映像文件

mount/umount 加载文件系统/卸载文件系统

quota 显示磁盘已使用的空间与限制

sync 将内存缓冲区内的数据写入磁盘

tree 以树状图列出目录的内容

系统操作:

alias 设置指令的别名

chkconfig 检查，设置系统的各种服务

clock 调整 RTC 时间

date 显示或设置系统时间与日期

dmesg 显示开机信息

eval 重新运算求出参数的内容

exit 退出目前的shell

export 设置或显示环境变量

finger 查找并显示用户信息

free 显示内存状态

hostid 显示主机标识

hostname 显示主机名

id 显示用户标识

kill 删除执行中的程序或工作

last 列出目前与过去登入系统的用户相关信息

logout 退出系统

lsmod 显示已载入系统的模块

modprobe 自动处理可载入模块

passwd 设置用户密码

ps process status 报告程序状况

reboot 重启计算机

rhwo 查看系统用户

rlogin 远程登入

rpm 管理Linux各项套件的程序

shutdown 关机

su switch user 变更用户身份

top 显示，管理执行中的程序

uname 显示系统信息

useradd/userdel 添加用户 / 删除用户

userinfo 图形界面的修改工具

usermod 修改用户属性，包括用户的shell类型，用户组等，甚至还能改登录名

w 显示目前注册的用户及用户正运行的命令

whereis 确定一个命令的二进制执行码，源码及帮助所在的位置

who 列出正在使用系统的用户

whois 查找并显示用户信息

网络通信:

arp 网地址的显示及控制

ftp 文件传输

lftp 文件传输

mail 发送／接收电子邮件

mesg 允许或拒绝其他用户向自己所用的终端发送信息

mutt E-mail管理程序

ncftp 文件传输

netstat 显示网络连接、路由表和网络接口信息

pine 收发电子邮件，浏览新闻组

ping 向网络上的主机发送 icmp echo request 包

ssh 安全模式下的远程登录

telnet 远程登录

talk 与另一用户对话

traceroute 显示到达某一主机所经由的路径及所使用的时间

wget 从网络上自动下载文件

write 向其他用户的终端写信息
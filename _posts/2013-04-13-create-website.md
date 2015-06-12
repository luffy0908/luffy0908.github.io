---
author: chen
comments: true
date: 2013-04-13 02:00:26+00:00
layout: post
slug: create-website
title: CentOS6.2中通过PHP5+Apache2+MySQL快速建站
wordpress_id: 10
categories:
- 建站相关
---

一、安装MySQL

1、通过yum install命令安装MySQL，执行如下命令：

_#yum install mysql mysql-server_

2、根据提示安装完成之后，会提示Complete，接着启动MySQL的服务，执行命令：

_#service mysqld start_

3、修改root用户的密码，可以登陆数据库mysql实例的user表里直接修改，也可以通过**mysql_secure_installation**来修改，执行**mysql_secure_installation**命令，根据提示即可完成密码的修改：
#mysql_secure_installation

这样MySQL就安装完成了，接下来安装Apache2.

二、安装Apache2

1、通过yum install命令安装，执行如下命令：
_#yum install httpd_

2、Apache2安装完成后，将服务启动：
#service httpd start

接下来安装PHP5.

三、安装PHP5

1、执行如下命令进行PHP5的安装：
_#yum install php_

2、安装完成后，启动php服务：
_#service httpd start_

默认安装后的网站根目录为_/var/www/html_，可以在此目录下创建php文件，然后通过浏览器来访问，如果访问成功则说明安装成功，否则需要重新安装。
接下来需要整合PHP和MySQL。

四、整合PHP和MySQL以及PHP的一些组件

1、通过下面的命令可以查看PHP的组件包列表：
_#yum search php_

2、根据上面的列表选取需要安装的进行安装，执行命令：
_#yum install php-mysql php-gd php-imap php-ldap php-mbstring php-odbc php-pear php-xml php-xmlrpc_

3、安装完成后，重启Apache2的服务，重启时有可能会提示：_Could not reliably determine the server's fully qualified domain name, using 127.0.0.1 for ServerName，_这可以通过去掉httpd.conf文件中#ServerName www.example.com:80这行的注释解决。

之后我们就可以去下载[](http://wordpress.org/)，然后按照官方的[](http://codex.wordpress.org/zh-cn:%E5%AE%89%E8%A3%85WordPress)完成个人网站的搭建。



---
title: Win7下搭建Apache+PHP+MySQL环境
layout: post
guid: urn:uuid:76b015c2-1287-452c-c746-561g12fb70a1
tags:
  - Apache
  - PHP
  - MySQL
---

## 一、安装&配置php

### 1.下载php
到[php官网](http://windows.php.net/download#php-5.6)下载对应windows版本即可, 这里下载PHP 5.6 VC11 x86 Thread Safe版本。

### 2.配置php
解压下载的php安装包到指定目录, 找到php.ini-development改名为php.ini, 并修改配置如下:
修改php扩展包路径, 找到
> ; On windows:
> ; extension_dir = "ext"
改为
> ; On windows:
> extension_dir = "d:/php/ext"
开启MySQL支持, 找到
> ;extension=php_curl.dll
> ;extension=php_gd2.dll
> ;extension=php_mbstring.dll
> ;extension=php_mysql.dll
> ;extension=php_pdo_mysql.dll
> ;extension=php_pdo_odbc.dll
> ;extension=php_xmlrpc.dll
改为
> extension=php_curl.dll
> extension=php_gd2.dll
> extension=php_mbstring.dll
> extension=php_mysql.dll
> extension=php_pdo_mysql.dll
> extension=php_pdo_odbc.dll
> extension=php_xmlrpc.dll

## 二、安装&配置Apache

### 1.下载Apache
由于Apache官网只提供源码, 不提供编译好的二进制文件, 方便起见可以下载第三方提供的二进制文件, 有下面几种选择:

* [ApacheHaus](http://www.apachehaus.com/cgi-bin/download.plx)
* [Apache Lounge](http://www.apachelounge.com/download/)
* [BitNami WAMP Stack](https://bitnami.com/stack/wamp)
* [WampServer](http://www.wampserver.com)
* [XAMPP](https://www.apachefriends.org/index.html)

任意选择一个下载即可, 这里我们以ApacheHaus为例。

### 2.配置Apache
下载完成之后解压到指定目录, 然后打开conf目录下的httpd.conf配置文件, 修改配置如下:
要支持php, 需将
> DirectoryIndex index.html
改为
>
DirectoryIndex index.php index.html
另外, 找到
> #LoadModule vhost_alias_module modules/mod_vhost_alias.so
在这行下面添加php的支持(注意dll文件的路径)
> LoadModule php5_module "d:/php/php5apache2_4.dll"
> PHPIniDir "d:/php"
> AddType application/x-httpd-php .php .html .htm

## 三、安装MySQL
到[MySQL官网](http://dev.mysql.com/downloads/mysql/)下载MySQL Community版本即可。

## 四、测试
配置完成之后, 重启Apache服务, 并在htdocs目录下添加index.php文件, 内容如下:
> <?php phpinfo(); ?>
注意:htdocs默认在Apache安装目录下, 可以通过httpd.conf修改其路径。





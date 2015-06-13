---
title: WordPress固定链接设置
layout: post
guid: urn:uuid:76b015c2-1287-452c-a746-561d12fb70a1
tags:
  - WordPress
---

最近用wordpress3.5.1弄个人网站，在Settings->Permalinks中设置完固定链接的格式后，发现网站上所有的超链接都无法访问，在google中搜索后，发现问题在.htaccess文件和httpd.conf文件的配置问题，httpd.conf文件需要修改以下两个地方是:

    <Directory />
     Options FollowSymLinks
     #AllowOverride NONE 需要将NONE改为All
     AllowOverride All
    </Directory>

    <Directory "/var/www/html">
     Options Indexes FollowSymLinks
     #AllowOverride NONE 需要将NONE改为All
     AllowOverride All
    </Directory>

但是，按照上面修改后重启httpd后问题仍然存在，而且在_Settings->Permalinks_修改链接格式时，会提示需要手动更新，但是.htaccess文件的权限已经改为666，怎么会不可写呢？经过一番研究之后发现问题是.htaccess文件放置的路径不对导致的，网上的许多解答都没有提到此文件的路径，所以导致忽
略了这个问题。那么，.htaccess文件已经放在哪里呢？答案是：放到网站根目录，即/var/www/html，修改之后在_Settings->Permalinks_修改链接格式就会发现可以自动更新了


---
author: chen
comments: true
date: 2013-04-13 01:23:59+00:00
layout: post
slug: centos6-2-vpn%e7%8e%af%e5%a2%83%e5%bf%ab%e9%80%9f%e6%90%ad%e5%bb%ba
title: CentOS6.2 VPN环境快速搭建
wordpress_id: 5
categories:
- 建站相关
---

在CentOS6.2操作系统下，安装VPN步骤如下：

1、下载CentOS专用vpn安装包，可以直接通过wget命令获取：
_wget http://www.hi-vps.com/shell/vpn_centos6.sh_

2、执行vpn_centos6.sh，根据提示按1即可开始安装：
_bash vpn_centos6.sh_

3、安装完成后，会出现默认的vpn账号和密码，如需修改密码可在**/etc/ppp/chap-secrets**文件中修改即可。

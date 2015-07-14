---
title: Github Page的域名绑定
layout: post
guid: urn:uuid:b1e6cf54-b5e7-4da0-95b2-2529b6396a55
tags:
  - Github
---

大家都知道通过Github Page创建的博客域名都是xxx.github.io, 很不方便记忆, 那么怎么才能绑定自己申请的域名呢?
答案很简单, 只需要2步即可完成:

### 1.在github根目录建立CNAME文件, 加入你的域名如下:

> xxx.com

### 2.登陆域名提供商网站设置DNS解析即可. 本人是在[Godaddy]{https://www.godaddy.com}上注册的域名, 只需要登录Godaddy找到  DNS ZONE FILE页签, 增加两条记录即可, 其中Points To为对应github.io的ip地址, Ping下就知道了, 如下:

| Record Type | Host | Points To       |

| ---         | ---  | ---             |

| A           |  @   | xxx.xxx.xxx.xxx |

| A           | WWW  | xxx.xxx.xxx.xxx |


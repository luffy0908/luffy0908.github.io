---
title: Android ADB端口被占用
layout: post
guid: urn:uuid:f2c1873d-7b69-4618-bf37-1e6e4d5c7145
tags:
  - Android
---

最近在Windows下做Android软件开发, 经常遇到端口被占用的情况, 解决办法有以下两个:

### 1.自定义端口(推荐)
通过系统环境变量ANDROID_ADB_SERVER_PORT可以自定义端口。

### 2.关闭占用端口的进程
5037为ADB的默认端口, 通过在CMD下执行下面的命令可以找出占用此端口的进程PID:

> netstat -aon | findstr 5037

找出PID后再执行以下命令就可以找出对应的进程:

> tasklist | findstr "PID"

最后执行下面的命令杀掉进程即可:

> taskkill /pid "PID" /f

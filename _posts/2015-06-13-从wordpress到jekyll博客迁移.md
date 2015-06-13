---
title: 从wordpress到jekyll博客迁移
layout: post
guid: urn:uuid:618de5cf-2be6-425d-83f2-034c55205d8a
tags:
  - WordPress
---

最近在github上搭建了一个Blog，用的jekyll+Github Pages。那么问题来了，wordpress上的博客是否可以迁移过来呢？
答案是肯定的，步骤也是想当简单：

1. 从wordpress中导出所有的Blog，格式为xml;

2. 将xml转换为md(markdown)格式，这里需要用到一个工具[exitwp](https://github.com/thomasf/exitwp), 具体用法如下:

   * 先将clone下来exitwp, 将wordpress导出的Blog备份文件(xml)拷贝到wordpress-xml目录下
   * 执行python exitwp.py, 有可能会报依赖包缺失的错误，主要依赖PyYAML和BeautifulSoup
   * mac下先安装pip，执行_easy_install pip_
   * 安装yaml，执行_pip install -U pyyaml_
   * 安装Beautiful Soup, 执行_pip install beautifulsoup4_

3. 执行之后就可以在build目录下找到生成的md文件, 拷贝到_post目录部署即可

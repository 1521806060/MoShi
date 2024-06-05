---
created: 2024-11-19T15:25:03 (UTC +08:00)
date: 2024-12-01T15:25:03+08:00
tags: [Alist搭建, 网盘, 教程]
title: Alist安装教程，十分钟搭建一个属于自己的网盘系统
source: https://blog.csdn.net/weixin_44786530/article/details/129756740
author: 
---

# Alist安装教程，十分钟搭建一个属于自己的网盘系统_alist搭建教程-CSDN博客

> ## Excerpt
> 文章浏览阅读2.7w次，点赞4次，收藏47次。AList是一个支持多种存储，支持网页浏览和 WebDAV 的文件列表程序，由 gin 和 Solidjs 驱动。简单的来说就是能够帮助你管理各种网盘应用，类似于CloudDrive，AList除了支持网盘存储之外，还支持对象存储，本地存储，FTP等等。AList在部署配置上可能稍微有些麻烦，你可以看官方提供的文档，或者搜索相关的视频进行操作，如果你经常使用网盘等存储服务，相信它能帮助你提高不少效率。_alist搭建教程

---
![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/5b9cfdcdef5f363c5beda61af425e9e2.jpeg)

不想看文档的的，可以看bilibili上的视频教程：[网盘这样用，也太爽了！- 神器 AList 详细使用教程 | 网盘整合、在线播放、WebDAV\_哔哩哔哩\_bilibili](https://www.bilibili.com/video/BV1ut4y1u7SM/?spm_id_from=333.337.search-card.all.click&vd_source=f7cadf462a105b99d7d00efa1a09735e "网盘这样用，也太爽了！- 神器 AList 详细使用教程 | 网盘整合、在线播放、WebDAV_哔哩哔哩_bilibili")

官网地址：[https://alist.nn.ci/](https://alist.nn.ci/ "https://alist.nn.ci/")

AList是一个支持多种存储，支持网页浏览和 [WebDAV](https://so.csdn.net/so/search?q=WebDAV&spm=1001.2101.3001.7020) 的文件列表程序，由 gin 和 Solidjs 驱动。简单的来说就是能够帮助你管理各种网盘应用，类似于CloudDrive，AList除了支持网盘存储之外，还支持对象存储，本地存储，FTP等等。

AList在部署配置上可能稍微有些麻烦，你可以看官方提供的文档，或者搜索相关的视频进行操作，如果你经常使用网盘等存储服务，相信它能帮助你提高不少效率。

### 特点很多

支持多个存储提供商，包括本地存储、阿里云盘、OneDrive、Google Drive 等，且易于拓展。  
支持 WebDAV、暗黑模式、受保护的路由、文件预览、打包下载、文件编辑、HTML渲染、文件永久链接、Cloudflare Workers 代理等

### 使用起来也非常简单

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/980486267f0f6d17bef39d838c626d18.png)三步走原则： 安装，配置网盘，使用

### 下载安装

下载地址：[Releases · alist-org/alist · GitHub](https://github.com/alist-org/alist/releases "Releases · alist-org/alist · GitHub")

以Windows为例，下载指定版本的文件。

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/5b19312a88b5a7548141cc059e6c69e7.png)

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/199e1b98ca561c79e05c86431b141beb.png)解压文件并进入文件夹；运行CMD，并输入`.\alist.exe server`，运行程序；

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/5cb6f73d9c92f0c58032c66de477d4af.png)注意看start server@0.0.0.0:5244 的输出，之后没有报错，说明操作成功，最后也可以看到初始密码，用户名默认是admin：

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/0061aef10c413f76631f768fcce5e7b1.png)在浏览器中输入本地地址，加alist端口号，即可看到登陆页面了：

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/a5f2d5946793d59878b8a6a91cf0cbc6.png)

用户名默认是admin，输入用户名和刚才黑窗口的密码，就可以登陆成功了：

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/c0a7075b851fdd08c59d0ea6f3872977.png) 在管理里面，可以更改管理员信息，用户名和密码都可以改：![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/ac14d732bad4446a83dcc230bcbcd40b.png)

### 添加网盘

在官网的网盘配置列表里面有详细的不同的网盘配置文档，我只能说太详细了，什么网盘都有，简直无敌了：

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/904a1654ddece65c4597e21f072a6a39.png)

这里就以阿里网盘为例进行配置：获取Token，用阿里云盘APP扫码二维码获取

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/bb6c267825f1e9693a9492f8d7b664eb.png)

然后黏贴到这里：

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/c23ed70a4980aa24b253c208a93a24b1.png)

主义这个根文件夹ID，默认会把所有萎蔫加载进来，也可以修改为对应文件夹的id： 

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/e9f419fd04f675a5b5bc000d5cc5f8f2.png)

设置其他选项，最后添加，点击主页，即可看到云盘添加成功 ：

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/125675371374d732a7a05c9c3c7660a6.png)

#### PotPlayer挂载Alist

1、新建专辑

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/cab38bc5464028e372b4a55c3e3abad4.png)

2、填写专辑信息

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/15de542f4415d71c1e7b501c7ddddabb.png)

**专辑名称：** 用于显示在播放列表上；

**协议：** WebDav；

**主机/路径：** 如果在本机上配置就填：`127.0.0.1/dav`；如果在别的电脑上配置就填Alist所在电脑的IP地址；

**端口：** 配置Alist时的端口（原始默认是5244）；

**用户名：** 默认admin；

**密码：** 登录Alist的密码。

**注：** 如果是外网访问，[官网说明](https://alist.nn.ci/zh/guide/webdav.html "官网说明")，参考官网说明。

3、设置成功

![](Alist%E5%AE%89%E8%A3%85%E6%95%99%E7%A8%8B%EF%BC%8C%E5%8D%81%E5%88%86%E9%92%9F%E6%90%AD%E5%BB%BA%E4%B8%80%E4%B8%AA%E5%B1%9E%E4%BA%8E%E8%87%AA%E5%B7%B1%E7%9A%84%E7%BD%91%E7%9B%98%E7%B3%BB%E7%BB%9F_alist%E6%90%AD%E5%BB%BA%E6%95%99%E7%A8%8B-CSDN%E5%8D%9A%E5%AE%A2/4c7c4ed66e5b683ff6ae53a14818ce66.png)

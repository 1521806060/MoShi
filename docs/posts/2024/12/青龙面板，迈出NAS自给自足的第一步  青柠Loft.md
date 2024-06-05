---
post: true
title: 青龙面板，迈出NAS自给自足的第一步 | 青柠Loft
date: 2024-12-17T20:55:57+8:00
tags: [NAS,PT,mini主机,nas使用教程,nas安装使用教程,nas配置教程,pt开注提醒,pt教程,nas测评,mini主机测评,pt新手任务]
cover:
coveross:
categories:
- 教程
description:  
source: https://blog.qnloft.com/archives/QF8lIdsd
author: 
---

# 青龙面板，迈出NAS自给自足的第一步 | 青柠Loft


> **不要把青龙面板安装想的很复杂，其实它就分为这么几步：**
> 
> 1.  安装和配置Docker镜像
> 2.  初始化和登录青龙面板
> 3.  配置和依赖下载
> 4.  下载项目
> 5.  定时任务管理

## Docker安装

#### 镜像选择

> 以极空间NAS为例：

[![Pasted image 20240220005027](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240220005027.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240220005027.png)

## Docker配置

> 镜像文件夹映射  
> [![Pasted image 20240219165323](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240219165323.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240219165323.png)

> 配置端口号，自行定义！  
> [![Pasted image 20240219165340](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240219165340.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240219165340.png)

## 面板初始化

[![Pasted image 20240222140335](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222140335.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222140335.png)

#### 设置用户名密码

[![Pasted image 20240222140415](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222140415.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222140415.png)

#### 通知管理(可跳过)

[![Pasted image 20240222140449](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222140449.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222140449.png)

初始化完成后，在登录页面进行登录，恭喜你💐，青龙面板可以正常使用了！！！

## 配置和依赖

点击配置文件，找到 `RepoFileExtensions="js py"`，这表示现在只能拉取文件后缀为`js`和`py`代码，为了方便以后适应更多的项目，这里加上其他编程语言，改为：`RepoFileExtensions="js py sh ts"` **（该配置可忽略）**

#### **第一步：一键安装依赖环境**

点击左侧`脚本管理`，选择右上角加号`新建脚本`，创建名称为：`QLOneKeyDependency.sh`的脚本，点击确定，在弹窗的空白页里，将下方脚本内容粘贴进入，并保存退出。点击右上角【调试】进入调试运行模式，运行脚本  
[![Pasted image 20240220231800](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240220231800.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240220231800.png)

#### **第二步：安装依赖包**

**完成第一步后**，将下面的依赖依次复制到 `nodeJs`、`python`模块中，**注意选择拆分！！！**，然后点击安装即可！  
[![Pasted image 20240222140817](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222140817.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222140817.png)

nodeJs 依赖

python包

linux包

## 开启青龙之旅

> 这里就以 京东签到打卡做任务薅羊毛全能的 `jdpro` 项目为例子，[项目地址 传送门](https://github.com/6dylan6/jdpro)

#### 京东

**第一步：项目订阅**

[![111](https://oss.qnloft.com/ob-img/2024/02/23/111.png)](https://oss.qnloft.com/ob-img/2024/02/23/111.png)

填写完成后，点击一下运行，**📢注意：这里如果填写的是`github`地址，会出现无法下载问题，所以最好是看我这篇文章，将项目转移到 `gitea`上面去**

**第二步：定时任务设置**

> 我们可以将不需要的任务设置成禁用，同时，也可以自由的设置任务的执行时间！这里就需要用到Cron表达式了，[在线表达式生成传送门](https://cron.qqe2.com/)

[![Pasted image 20240222171331](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222171331.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222171331.png)

**第三步：电脑抓取cookie**

电脑使用 浏览器 —— F12打开开发者模式 ——访问[http://m.jd.com](http://m.jd.com/) ——选择手机验证码登陆—— 在网络项搜索关键字cookie或者pt\_key 找到对应项目：

> 建议选择手机验证码登陆，cookie时效较长，否则可能经常需要重新抓取

[![Pasted image 20240222151418](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222151418.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222151418.png)

**第四步：设置青龙面板cookie变量**

根据网上的教程抓完cookie之后，就可以点击左侧\*\*【环境变量】\*\*，配置对应的账号：

[![Pasted image 20240222151614](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222151614.png)](https://oss.qnloft.com/ob-img/2024/02/23/Pasted%20image%2020240222151614.png)

## 其它项目

-   京东自动带图 [项目地址 传送门](https://github.com/qnloft/auto_comment)
-   阿里云盘签到 [项目地址 传送门](https://github.com/mrabit/aliyundriveDailyCheck)
-   什么值得买签到+任务 [项目地址 传送门](https://github.com/hex-ci/smzdm_script)
-   bilibili任务和抽奖 [项目地址 传送门](https://github.com/RayWangQvQ/BiliBiliToolPro)
-   饿了么、美团、滴滴 领券 [项目地址 传送门](https://github.com/linbailo/zyqinglong)
-   全民K歌、有道云笔记、百度贴吧、BiliBili、V2EX、ACFUN、爱奇艺、什么值得买、阿里云盘、恩山无线论坛、i 茅台等合集 [项目地址 传送门](https://sitoi.github.io/dailycheckin/)

## 写在最后

> 其实青龙只是给我们提供一个定时任务处理的平台，我们还可以用它做很多的事情！  
> 比如：定时干某件事情，或者在指定的时间去指定的网站获取数据等等！

在这里我说几个我自己实现的例子：

-   PT网站自动打卡签到
-   电商商品监控
-   考试报名监控
-   招聘数据每日汇总

**PS：如果小伙伴有什么好的想法，奈何不会写代码的，可以私信我~！**

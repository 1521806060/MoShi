---
created: 2024-08-20T21:45:39 (UTC +08:00)
date: 2024-08-20T21:45:39+08:00
title: AutojsPro对接自建服务器的手机环境设置教程-五云学习
categories:
 - 教程
tags: [AutojsPro,JustTrustMe,Lsposed,Magisk,MT管理器,免登录,劫持hosts,报错解决,服务器对接,添加证书,环境设置,Autojs]
source: https://www.wuyunai.com/76.html
author: 76650234.6W+
---

# AutojsPro对接自建服务器的手机环境设置教程-五云学习

> ## Excerpt
> 学习如何使用AutojsPro在手机上对接自建服务器，并进行必要的环境设置，包括劫持hosts、添加证书以及解决报错问题，最终实现免登录进入AutojsPro。

---
## 要求

-   Magisk面具
    
-   Lsposed（或者其他xp）框架
    
-   MT管理器
    

## 开始

\[content\_hide\]

### 劫持hosts

1.打开Magisk面具，进入到设置界面，添加Systemless Hosts模块。如下图所示

![AutojsPro对接自建服务器的手机环境设置教程](AutojsPro%E5%AF%B9%E6%8E%A5%E8%87%AA%E5%BB%BA%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%9A%84%E6%89%8B%E6%9C%BA%E7%8E%AF%E5%A2%83%E8%AE%BE%E7%BD%AE%E6%95%99%E7%A8%8B-%E4%BA%94%E4%BA%91%E5%AD%A6%E4%B9%A0/WechatIMG121_1_post_8YymU2989.jpeg "AutojsPro对接自建服务器的手机环境设置教程")

![AutojsPro对接自建服务器的手机环境设置教程](AutojsPro%E5%AF%B9%E6%8E%A5%E8%87%AA%E5%BB%BA%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%9A%84%E6%89%8B%E6%9C%BA%E7%8E%AF%E5%A2%83%E8%AE%BE%E7%BD%AE%E6%95%99%E7%A8%8B-%E4%BA%94%E4%BA%91%E5%AD%A6%E4%B9%A0/WechatIMG122_1_post_sKNkG6462.jpeg "AutojsPro对接自建服务器的手机环境设置教程")

![AutojsPro对接自建服务器的手机环境设置教程](AutojsPro%E5%AF%B9%E6%8E%A5%E8%87%AA%E5%BB%BA%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%9A%84%E6%89%8B%E6%9C%BA%E7%8E%AF%E5%A2%83%E8%AE%BE%E7%BD%AE%E6%95%99%E7%A8%8B-%E4%BA%94%E4%BA%91%E5%AD%A6%E4%B9%A0/WechatIMG124_1_post_hyhvx38874.jpeg "AutojsPro对接自建服务器的手机环境设置教程")

添加完成后，重启手机。

2.用MT管理器，打开目录`/data/adb/modules/hosts/system/etc/`

![AutojsPro对接自建服务器的手机环境设置教程](AutojsPro%E5%AF%B9%E6%8E%A5%E8%87%AA%E5%BB%BA%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%9A%84%E6%89%8B%E6%9C%BA%E7%8E%AF%E5%A2%83%E8%AE%BE%E7%BD%AE%E6%95%99%E7%A8%8B-%E4%BA%94%E4%BA%91%E5%AD%A6%E4%B9%A0/WechatIMG125_1_post_I4iRM5280.jpeg "AutojsPro对接自建服务器的手机环境设置教程")

3.修改hosts文件，复制下面的到你的hosts，把 \`1.12.243.265\` 换成你自己的服务器ip

```
<span role="presentation">127.0.0.1 &nbsp; &nbsp; &nbsp; localhost</span>
<span role="presentation">::1 &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; &nbsp; ip6-localhost</span>
<span role="presentation"></span>
<span role="presentation">1.12.243.265 pro.autojs.org</span>
<span role="presentation"></span>
<span role="presentation">127.0.0.1 data.flurry.com</span>
<span role="presentation">127.0.0.1 c.sayhi.360.cn</span>
<span role="presentation">127.0.0.1 android.bugly.qq.com</span>
<span role="presentation">127.0.0.1 recaptcha.net</span>
<span role="presentation"></span>
```

保存即可，到这里劫持pro.autojs.org到你的服务器ip设置完成，重启一下手机，用手机自带浏览器，打开 AutojsPro 网站：[https://pro.autojs.org](https://www.wuyunai.com/?golink=aHR0cHM6Ly9wcm8uYXV0b2pzLm9yZw==) 跳转到的页面是你的服务器页面，说明成功了！

## 添加我们自己的.0证书

1.Magisk安装本文提供移动证书模块\[MoveCertificates\]，下载模块到手机里面，然后打开Magisk，选择模块界面 >>> 从本地安装 >>> 选择刚刚下载的模块 ，安装完后重启手机

2.用MT管理器，打开目录`/data/adb/modules/movecert/system/etc/security/cacerts`

![AutojsPro对接自建服务器的手机环境设置教程](AutojsPro%E5%AF%B9%E6%8E%A5%E8%87%AA%E5%BB%BA%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%9A%84%E6%89%8B%E6%9C%BA%E7%8E%AF%E5%A2%83%E8%AE%BE%E7%BD%AE%E6%95%99%E7%A8%8B-%E4%BA%94%E4%BA%91%E5%AD%A6%E4%B9%A0/WechatIMG126_1_post_uGJXj21849.jpeg "AutojsPro对接自建服务器的手机环境设置教程")

3.在MT管理器另一栏，打开你的.0证书所在目录并把.0证书移动到目录

4.重启手机，完成手机添加.0证书

## 尝试打开AutojsPro

### 报错

![AutojsPro对接自建服务器的手机环境设置教程](AutojsPro%E5%AF%B9%E6%8E%A5%E8%87%AA%E5%BB%BA%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%9A%84%E6%89%8B%E6%9C%BA%E7%8E%AF%E5%A2%83%E8%AE%BE%E7%BD%AE%E6%95%99%E7%A8%8B-%E4%BA%94%E4%BA%91%E5%AD%A6%E4%B9%A0/WechatIMG129_1_post_hhhZp1622.jpeg "AutojsPro对接自建服务器的手机环境设置教程")

### 解决方法

这时就要用到XP插件\[JustTrustMe\]，可以从本文直接下载

> JustTrustMe 是一个用来禁用、绕过 SSL 证书检查的基于 Xposed 模块。JustTrustMe 是将 APK 中所有用于校验 SSL 证书的 API 都进行了 Hook，从而绕过证书检查。

安装完后XP插件后，打开LSPosed，找到刚刚安装JustTrustMe，设置作用域 >>> AutojsPro。

![AutojsPro对接自建服务器的手机环境设置教程](AutojsPro%E5%AF%B9%E6%8E%A5%E8%87%AA%E5%BB%BA%E6%9C%8D%E5%8A%A1%E5%99%A8%E7%9A%84%E6%89%8B%E6%9C%BA%E7%8E%AF%E5%A2%83%E8%AE%BE%E7%BD%AE%E6%95%99%E7%A8%8B-%E4%BA%94%E4%BA%91%E5%AD%A6%E4%B9%A0/WechatIMG127_1_post_Lgwmi16216.jpeg "AutojsPro对接自建服务器的手机环境设置教程")

\[/content\_hide\]

把AutojsPro强制停止，打开，恭喜你成功免登录进入AutojsPro

## 附件讲解

xp插件 \[JustTrustMe\]

> JustTrustMe 是一个用来禁用、绕过 SSL 证书检查的基于 Xposed 模块。JustTrustMe 是将 APK 中所有用于校验 SSL 证书的 API 都进行了 Hook，从而绕过证书检查。

面具模块\[MoveCertificates\]

> 原理：安卓7.0以后默认不信任用户安装的证书，所以我们自己制作SSL证书是不被信任的。通过这个模块，安装完证书之后，重启就可自动拷贝用户证书到system目录下，实现信任我们的SSL证书

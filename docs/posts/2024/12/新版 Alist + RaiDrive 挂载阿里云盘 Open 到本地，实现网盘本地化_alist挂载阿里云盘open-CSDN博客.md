---
title: 新版 Alist + RaiDrive 挂载阿里云盘 Open 到本地，实现网盘本地化
date: 2024-11-19 15:25:19
created: 2024-11-19T15:25:19 (UTC +08:00)
tags: [alist挂载阿里云盘open]
source: https://blog.csdn.net/weixin_62726289/article/details/129755306
author: 
---

# 新版 Alist + RaiDrive 挂载阿里云盘 Open 到本地，实现网盘本地化_alist挂载阿里云盘open-CSDN博客

> ## Excerpt
> 文章浏览阅读3.2w次，点赞13次，收藏49次。文章介绍了如何通过Alist和RaiDrive软件将阿里云盘挂载到本地，步骤包括下载软件、配置Alist、获取刷新令牌以及使用RaiDrive进行挂载。这样可以实现网盘内容的本地访问，便于直接使用本地播放器播放视频或在录制时选择云盘存储。

---
#### 新版 Alist + RaiDrive 挂载[阿里云盘](https://so.csdn.net/so/search?q=%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98&spm=1001.2101.3001.7020) Open 到本地，实现网盘本地化

-   -   [1\. 下载 Alist 和 RaiDrive](https://blog.csdn.net/weixin_62726289/article/details/129755306#1__Alist__RaiDrive_2)
    -   [2\. 配置 Alist](https://blog.csdn.net/weixin_62726289/article/details/129755306#2__Alist_27)
    -   [3\. 填写挂载路径和刷新令牌](https://blog.csdn.net/weixin_62726289/article/details/129755306#3__49)
    -   [4\. 获取刷新令牌](https://blog.csdn.net/weixin_62726289/article/details/129755306#4__55)
    -   [5\. 使用 RaiDrive 挂载](https://blog.csdn.net/weixin_62726289/article/details/129755306#5__RaiDrive__67)

### 1\. 下载 Alist 和 RaiDrive

**下载地址**：[Alist + RaiDrive 安装](https://www.aliyundrive.com/s/8QLUuanPhrJ) 提取码: qu38

Alist 文档：[Introduction | AList文档 (nn.ci)](https://alist.nn.ci/zh/guide/)

```sh
# 运行程序 .\alist.exe server # 获得管理员信息 .\alist.exe admin
```

1.  选择一个文件夹，将 alist.exe 解压出来，打开 cmd（分享的网盘链接已解压好，直接保存）
    
    ![image-20230324141413531](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/ae0e9c97a82f475bff2d5b78a097d109.png)
    
2.  输入 `.\alist.exe admin` ，查看密码并复制
    
    ![image-20230324141833388](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/58f1a1fe013550a8218976692e31a3b3.png)
    
3.  在命令行中输入 `.\alist.exe server` ，启动 alist
    
    ![image-20230324141539796](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/30875b595732697941093b99df487b59.png)
    

### 2\. 配置 Alist

打开 http://localhost:5244/

用户名默认为 `admin` ，密码为之前复制的密码

![image-20230324142127330](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/de63fb108806c4e6b3a2ce5358ae3d83.png)

登录后选择 `管理`

![image-20230324142154376](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/f9d80710c34f65242bdf37fa823c348d.png)

选择 `存储` ，`添加`

![image-20230324142328715](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/f529f0857454012e8daf082bc3eb0589.png)

驱动选择 `阿里云盘Open`

> 阿里云盘的接口改了，现在使用 open

![image-20230324165958390](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/840a8e482f0b8eee6d93e8bccb2ad7a5.png)

### 3\. 填写挂载路径和刷新令牌

`挂载路径` 不固定，可以自己填，如 /aliyun，其他配置可以自行调整，如过期时间可以改小一点

![image-20230324142525326](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/1aeed1fef3c5731591a7d40922d874cc.png)

### 4\. 获取刷新令牌

`刷新令牌` 根据文档里的说明进行获取，访问下面地址，按下面图片操作

地址：[Get Aliyundrive Refresh Token | AList Docs (nn.ci)](https://alist.nn.ci/tool/aliyundrive/request)

![image-20230324173807812](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/4b380d3443b91a1ad2e09f71fc3ec176.png)

复制 token，粘贴到上面的刷新令牌处，点击保存

![image-20230324163403365](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/128c431f79ee3a15513d4b77a4bb245c.png)

### 5\. 使用 RaiDrive 挂载

开头提供的链接中有 RaiDrive 安装包，直接双击下载

下载过程点击下一步，安装路径可以自定义，下载完成后打开 RaiDrive

点击右上角【**添加**】，之后按图示操作

> 注意地址框要取消掉

![image-20230324164328352](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/1693af8b6093e4a63892cdc6b566b08b.png)

连接后就可以看到网盘挂载了

![image-20230324164538065](%E6%96%B0%E7%89%88%20Alist%20+%20RaiDrive%20%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98%20Open%20%E5%88%B0%E6%9C%AC%E5%9C%B0%EF%BC%8C%E5%AE%9E%E7%8E%B0%E7%BD%91%E7%9B%98%E6%9C%AC%E5%9C%B0%E5%8C%96_alist%E6%8C%82%E8%BD%BD%E9%98%BF%E9%87%8C%E4%BA%91%E7%9B%98open-CSDN%E5%8D%9A%E5%AE%A2/06b2b1129485b1034287ba09db0f3882.png)

挂载好后网盘的视频也可以用本地的播放器观看了，录视频也可以直接选择[云盘](https://so.csdn.net/so/search?q=%E4%BA%91%E7%9B%98&spm=1001.2101.3001.7020)，不需要手动转存了

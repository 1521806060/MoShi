---
post: true
title: 解决github上的提交说明中文乱码的问题_gitblit 中文乱码-CSDN博客
date: 2024-08-15T21:03:22+08:00
created: 2024-08-15T17:13:22 (UTC +08:00)
tags: [gitblit 中文乱码]
categories:
 - 教程
source: https://blog.csdn.net/fye700/article/details/112285591
author: 
---

# 解决github上的提交说明中文乱码的问题_gitblit 中文乱码-CSDN博客

> ## Excerpt
> github上的提交说明中文乱码通过pycharm提交代码到gibhub仓库，发现每次提交时的中文说明，在github上显示的是乱码，如下：虽然说不影响代码，但是作为一个github上脸面的一个存在（或者说有点强迫症），决定还是解决这个难看的问题。首先，得明白为什么会产生问题，这个显然是一个编码问题，github默认使用的编码格式是utf-8，而本地使用的编码格式是GB2313，提交代码的时候，使用的中文就是使用GB2313编码的格式，这样提交到github上，通过utf-8去解码当然解不了，所_gitblit 中文乱码

---

### [github](https://so.csdn.net/so/search?q=github&spm=1001.2101.3001.7020)上的提交说明中文乱码

  通过pycharm提交代码到gibhub仓库，发现每次提交时的中文说明，在github上显示的是乱码，如下：  
![在这里插入图片描述](%E8%A7%A3%E5%86%B3github%E4%B8%8A%E7%9A%84%E6%8F%90%E4%BA%A4%E8%AF%B4%E6%98%8E%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81%E7%9A%84%E9%97%AE%E9%A2%98_gitblit%20%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81-CSDN%E5%8D%9A%E5%AE%A2/5afd530e2ac376e961db09ae5c4dda46.png)  
  虽然说不影响代码，但是作为一个github上脸面的一个存在（或者说有点强迫症），决定还是解决这个难看的问题。

  首先，得明白为什么会产生问题，很明显这是一个编码问题，github默认使用的编码格式是utf-8，而本地使用的编码格式是GB2312，提交代码的时候，使用的中文就是使用GB2312编码的格式，这样提交到github上，通过utf-8去解码当然解不了，所以显示的是乱码。

**那如何去解决这个问题呢？**

  在网上也找了很多，但是都没有解决问题，后面自己去找到git安装目录下的etc\\gitconfig文件，用文本文件打开，发现log编码那里，编码方式是GB2312，  
![在这里插入图片描述](%E8%A7%A3%E5%86%B3github%E4%B8%8A%E7%9A%84%E6%8F%90%E4%BA%A4%E8%AF%B4%E6%98%8E%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81%E7%9A%84%E9%97%AE%E9%A2%98_gitblit%20%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81-CSDN%E5%8D%9A%E5%AE%A2/40c2046026f78cd815e558b007b4387a.png)

将编码格式改为utf-8，记得保存一下  
![在这里插入图片描述](%E8%A7%A3%E5%86%B3github%E4%B8%8A%E7%9A%84%E6%8F%90%E4%BA%A4%E8%AF%B4%E6%98%8E%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81%E7%9A%84%E9%97%AE%E9%A2%98_gitblit%20%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81-CSDN%E5%8D%9A%E5%AE%A2/c477502c5b9f889160c161b69812ee53.png)  
然后再次提交一次代码，加上中文说明，然后打开github个人主页（github.com），看一下刚刚提交的代码记录，发现说明文字已经正常显示为中文了。  
![在这里插入图片描述](%E8%A7%A3%E5%86%B3github%E4%B8%8A%E7%9A%84%E6%8F%90%E4%BA%A4%E8%AF%B4%E6%98%8E%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81%E7%9A%84%E9%97%AE%E9%A2%98_gitblit%20%E4%B8%AD%E6%96%87%E4%B9%B1%E7%A0%81-CSDN%E5%8D%9A%E5%AE%A2/a1ac18ff796c8709fa129c1e572ac044.png)

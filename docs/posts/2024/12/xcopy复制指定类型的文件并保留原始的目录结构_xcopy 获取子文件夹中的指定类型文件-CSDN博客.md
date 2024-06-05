---
created: 2024-09-06T14:01:10 (UTC +08:00)
date: 2024-09-06T14:01:10 (UTC +08:00)
title: xcopy复制指定类型的文件并保留原始的目录结构_xcopy 获取子文件夹中的指定类型文件-CSDN博客
tags: [xcopy 获取子文件夹中的指定类型文件]
source: https://blog.csdn.net/jszj/article/details/79610661
author: 
---

# xcopy复制指定类型的文件并保留原始的目录结构_xcopy 获取子文件夹中的指定类型文件-CSDN博客

> ## Excerpt
> 文章浏览阅读1.2w次，点赞4次，收藏3次。参考：https://bbs.csdn.net/topics/392023993，9楼我使用的是powershell执行此命令的，如下：xcopy *.dat d:\mybackup /S把当前目录及其子目录下的所有扩展名为 dat 的文件拷贝到 d:/mybackup 目录中，并保持它们原有的目录结构。比如我当前的目录中有文件：1.dat2018\01.dat2018\01.xls2018\02..._xcopy 获取子文件夹中的指定类型文件

---
![](xcopy%E5%A4%8D%E5%88%B6%E6%8C%87%E5%AE%9A%E7%B1%BB%E5%9E%8B%E7%9A%84%E6%96%87%E4%BB%B6%E5%B9%B6%E4%BF%9D%E7%95%99%E5%8E%9F%E5%A7%8B%E7%9A%84%E7%9B%AE%E5%BD%95%E7%BB%93%E6%9E%84_xcopy%20%E8%8E%B7%E5%8F%96%E5%AD%90%E6%96%87%E4%BB%B6%E5%A4%B9%E4%B8%AD%E7%9A%84%E6%8C%87%E5%AE%9A%E7%B1%BB%E5%9E%8B%E6%96%87%E4%BB%B6-CSDN%E5%8D%9A%E5%AE%A2/original.png)

[red-fly](https://blog.csdn.net/jszj "red-fly") ![](xcopy%E5%A4%8D%E5%88%B6%E6%8C%87%E5%AE%9A%E7%B1%BB%E5%9E%8B%E7%9A%84%E6%96%87%E4%BB%B6%E5%B9%B6%E4%BF%9D%E7%95%99%E5%8E%9F%E5%A7%8B%E7%9A%84%E7%9B%AE%E5%BD%95%E7%BB%93%E6%9E%84_xcopy%20%E8%8E%B7%E5%8F%96%E5%AD%90%E6%96%87%E4%BB%B6%E5%A4%B9%E4%B8%AD%E7%9A%84%E6%8C%87%E5%AE%9A%E7%B1%BB%E5%9E%8B%E6%96%87%E4%BB%B6-CSDN%E5%8D%9A%E5%AE%A2/newCurrentTime2.png) 于 2018-03-19 14:05:07 发布

[](https://so.csdn.net/so/search?q=&spm=1001.2101.3001.7020)参考：https://bbs.csdn.net/topics/392023993，9楼

我使用的是powershell执行此命令的，如下：

xcopy \*.dat d:\\mybackup /S

把当前目录及其子目录下的所有扩展名为 dat 的文件拷贝到 d:/mybackup 目录中，并保持它们原有的目录结构。

比如我当前的目录中有文件：

1.dat

2018\\01.dat

2018\\01.xls

2018\\02.dat

2017\\4\\1.dat

2017\\3\\

在当前目录执行 xcopy \*.dat d:\\mybackup /S 之后，d:\\mybackup 下的内容为：

1.dat

2018\\01.dat

2018\\02.dat

2017\\4\\1.dat

这个目录中只有 dat 文件，而且原始的一个窗口目录 2017\\3 也是不存在的，即空目录不会被拷贝过来  

xcopy的相关参数：

/E ： 同 /S 相比，则会把空目录也拷贝过来，如果使用 xcopy \*.dat d:\\mybackup /E，则 d:\\mybackup 目录下的内容为：

1.dat

2018\\01.dat

2018\\02.dat

2017\\4\\1.dat

2017\\3\\

最后一行红色的部分就是拷贝过来的空目录

需要注意的是，目标路径，应该采用“\\”分隔符而不是“/”，否则指定的目录名无效，比如我测试的时候使用 

xcopy \*.dat ../mybackup /E，结果所有的文件都以当前目录的上级目录为基础了，即相当于

xcopy \*.dat .. /E  

根据在拷贝过程中的观察，所谓不拷贝空目录，其实还是会先建立这个目录，如果发现这个目录中没有要拷贝的文件时，它会被删除掉，当然由于速度很快，我只观察到第一级目录，而其中的子目录则没有看到，不过我想应该也是会建立然后再删除这样的策略

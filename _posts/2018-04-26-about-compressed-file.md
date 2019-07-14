---
layout: post
title: 关于压缩文件
date: 2018-04-26
author: chtld
categories: 技术
tags: [压缩]

---

本文是关于文件压缩的格式的说明, 附有linux下的文件解压命令的说明.

<!--more-->

通常指的压缩其实包括了两个过程: (1)打包; (2)压缩;

- tar本身是一个文件打包工具, 自身没有压缩功能. 通常是先使用tar打包之后再调用其他压缩工具进行文件压缩. 优点是比较适合linux系统, 保持文件的权限状态、软硬链接能力强.
- zip是一种压缩算法, 压缩比相对不高. 是压缩后再加入打包封装容器.
- gz是zip的GNU实现.
- rar是带专利的商业算法, 压缩比较高. 是压缩后再加入打包封装容器.
- 7-zip是兼具压缩和打包封装功能的软件, 压缩比高, 默认压缩格式为lzma.


主要有下面的命令:

- *.tar 用 tar –xvf 解压
-  *.gz 用 gzip -d或者gunzip 解压*
- .tar.gz和*.tgz 用 tar –xzf 解压
- *.bz2 用 bzip2 -d或者用bunzip2 解压
- *.tar.bz2用tar –xjf 解压
- *.Z 用 uncompress 解压
- *.tar.Z 用tar –xZf 解压
- *.rar 用 unrar e解压
- *.zip 用 unzip 解压

```bash
tar -zxvf /usr/local/test.tar.gz
```

-z 有gzip属性的

-x 解压

-v 显示所有过程

-f 使用档案名字


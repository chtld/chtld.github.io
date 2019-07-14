---
layout: post
title: notes on learning dealii(1)
date: 2018-04-26
categories: 技术
tags: [c++, finite_element_methods]
---

本文记录了本人在学习使用 [dealii](http://www.dealii.org/)的过程, 如有错误还请与我联系, 万分感谢.

<!--more-->

#### dealii的安装

在ubuntu下:

- 首先下载安装包, 为.tar.gz结尾的文件(一般为源代码安装包, 需要先解压再经过编译、安装才能执行).

- 解压文件

  ```bash
  tar -zxvf dealii.tar.gz
  ```

- 进入解压后的目录

  ```bash
  cd dealii
  ```

- 使用下面的命令编译、安装dealii

  ```bash
  mkdir build
  cd build
  cmake -DCMAKE_INSTALL_PREFIX=/path/to/install/dir ../deal.II
  make install
  make test
  ```

  上面的命令是创建了一个cmake的编译目录，然后编译安装了dealii


---
layout: post
title: cmake 升级安装
date: 2018-10-05
categories: 技术
tags: [cmake, linux]
---
本文是 cmake 的安装升级过程，因为需要，所以纪录在此。
<!--more-->

### cmake的安装
在 ubuntu 下，使用如下默认命令可以安装 cmake， 但可能版本较低。安装后可使用命令查看 cmake 版本。
```bash
sudo apt-get install cmake
cmake --version
```
在[http://www.cmake.org/files](http://www.cmake.org/files) 上查看自己需要的版本号，然后使用下面的命令安装。
```bash
sudo apt-get install build-essential
wget http://www.cmake.org/files/v3.11/cmake-3.11.3.tar.gz
tar xf cmake-3.11.3
./configure
make
sudo make install
cmake --version
```
如果输出如下信息，则安装成功。
```
cmake version 3.11.3
CMake suite maintained and supported by Kitware (kitware.com/cmake).
```
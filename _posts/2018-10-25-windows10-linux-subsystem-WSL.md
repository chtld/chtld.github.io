---
layout: post
title: windows10开启linux子系统WSL
date: 2018-10-25
categories: 技术
tags: [linux, win10]
---
本文记录了在Windows10下开启linux子系统的过程。
<!--more--> 

#### 启用开发者模式
打开 windows 设置，进入设置-->更新和安全-->针对开发人员，打开开发人员模式。
![示意图1]({{site.url}}/images/2018-10-25-windows10-linux-subsystem-WSL/1.jpg)

#### 添加系统功能
打开控制面板-->程序-->启用和关闭windows功能，然后开启Hyper-V和适用于windows的linux子系统。
![示意图2]({{site.url}}/images/2018-10-25-windows10-linux-subsystem-WSL/2.jpg)
![示意图3]({{site.url}}/images/2018-10-25-windows10-linux-subsystem-WSL/3.jpg)

#### 开启cpu虚拟化支持
重启电脑进入bios设置，开启cpu虚拟化支持。


#### 安装ubuntu
使用windows+r键打开运行窗口，输入cmd，回车进入，输入bash，然后一路yes，设置用户名和密码，就安装成功了。也可直接进入windows商店，搜索ubuntu，然后选择自己喜欢的版本进行安装。
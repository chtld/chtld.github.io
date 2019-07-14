---
layout: post
title: Continuum-Mechanics
date: 2018-12-14
categories: peridynamic
mathjax: true
tags: [continuum mechanics]
---
本文是连续介质力学的读书笔记。
<!--more-->

### 一、物体的描述
#### 1. 构型 
   - $R_0$表示初始时刻物体的形状，称为参考构型(reference configuration);
   - $R$表示当前时刻$t$物体的形状，称为当前构型(currect configuration);
   
#### 2. 坐标 
   - $X$为初始时刻各物质点的坐标，称为物质坐标(material coordinates);
   - $x$为当前时刻各物质点的坐标，称为空间坐标(spatial coordinates);
   
#### 3. 变形与运动
   - 变形前的微元记作$dX$, 变形后的微元记作$dx$, 则形变梯度张量$F$反映了小变形下形状的变化$dx = FdX$, 则$det(F)$反映了体积的改变，即变形后与变形前的体积比。
   - $u(X, t) = x(X, t) - X$, 拉格朗日描述，物质点$X$在$t$时刻的位置减去初始时刻的位置，由于在固体力学中变形较小，故常采用此种描述方式，以物质点的初始位置为自变量对物体的运动进行刻画。
   - $u(x, t) = x - X(x, t)$, 欧拉描述，关注当前位置，用$x$这个位置减去占据这个位置的物质点$X$在$t$时刻之前的位置。
   - 位移的梯度$\frac{\partial u}{\partial x}$, 是相对当前构型的变形，称为真实变形
   - 位移关于物质坐标的梯度  
   $$
   \begin{aligned}
   \frac{\partial u}{\partial X} &= \frac{\partial u}{\partial x}\frac{\partial x}{\partial X} = \frac{\partial u}{\partial x}\frac{\partial (X + u)}{\partial X} \\
   &= \frac{\partial u}{\partial x}(I + \frac{\partial x}{\partial X}) \\
   &= \frac{\partial u}{\partial x} + \frac{\partial u}{\partial x}\frac{\partial u}{\partial x} + \frac{\partial u}{\partial x}\frac{\partial u}{\partial x}\frac{\partial x}{\partial X} \\
   &= \frac{\partial u}{\partial x} + \frac{\partial u}{\partial x}\frac{\partial u}{\partial x} + \frac{\partial u}{\partial x}\frac{\partial u}{\partial x}\frac{\partial u}{\partial x} + ...
   \end{aligned}
   $$
   在小变形假设下，$\frac{\partial u}{\partial X} \ll 1$, 真实变形近似于位移场在参考构型下的梯度，采用原始尺寸合理。
   
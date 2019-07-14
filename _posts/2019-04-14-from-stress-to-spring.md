---
layout: post
title: 从应力的概念看弹簧
date: 2019-04-14 21:59:18 +0800
categories: jekyll
---
##### 弹簧方程：$F = k\Delta x$
考虑一个一维的弹簧，一段固定，长度为$L$, 横截面积为 $A$, 杨氏模量为 $E$, 在右端受到力 $F$, 伸长量为 $\Delta L$ ,则    

- 应力 $\sigma = \frac{F}{A}$
- 应变 $\epsilon = \frac{\Delta L}{L}$

则由应力和应变之间的关系有
$$
\sigma = E\epsilon \\
\frac{F}{A} = E\frac{\Delta L}{L} \\
F = \frac{EA}{L}\Delta L
$$
从而得到
$$
k = \frac{EA}{L}
$$

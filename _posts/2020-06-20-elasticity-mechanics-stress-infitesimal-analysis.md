---
layout: post
title: Elasiticity-Mechanics-stress
date: 2020-06-20
categories: continuum mechanics
mathjax: true
tags: [continuum mechanics]
---
本文是连续介质力学的读书笔记。
<!--more-->
### 二、应力与平衡-微元体分析

#### 1、内力的刻画-应力
首先看看物体受到外力作用发生了什么，你是不是想说：我哪知道。好吧，那就先看看人受到外力会发生什么。

当你受到外界的压力的时候，你的内心会发生变化，变得焦虑，但这时你也就承受住了压力，说明你体内的内力场与外界的外力场平衡了。
物体受到压力的时候，物体发生了变形，改变了分子间距，物体内形成了一个内力场，当变形不再继续时，内外力场平衡。

用一个假想的曲面 $S$ 将物体分成内域外域两部分，外域对内域的作用可分为两部分：
- 通过曲面$S$作用，接触力，近程力
- 越过曲面$S$作用，相互体力，远程力
**欧拉-柯西应力原理认为物体各部分之间的相互体力可以忽略，外域对内域的作用可等价的用定义在曲面$S$上的应力场来代替。**

考虑一个处于平衡状态的物体 $B$ 中的任意一点 $P$, 在该处取一个正六面体微元，法线方向与坐标轴同向的三个面元称为正面，记为$dS_{i}, i = 1, 2, 3.$ 作用在 $dS_{i}$ 上的应力矢量为 $\boldsymbol{\sigma}_{i}$. 如图所示，



将其沿三个坐标轴方向分解，则有
$$
\begin{aligned}
\boldsymbol{\sigma}_{1} = \sigma_{11}\mathbf{e}_{1} + \sigma_{12}\mathbf{e}_{2} + \sigma_{13}\mathbf{e}_{3}, \\
\boldsymbol{\sigma}_{2} = \sigma_{21}\mathbf{e}_{1} + \sigma_{22}\mathbf{e}_{2} + \sigma_{23}\mathbf{e}_{3}, \\
\boldsymbol{\sigma}_{3} = \sigma_{31}\mathbf{e}_{1} + \sigma_{32}\mathbf{e}_{2} + \sigma_{33}\mathbf{e}_{3}, \\
\end{aligned}
$$
用张量记号
$$
\boldsymbol{\sigma}_{i} = \sigma_{ij}\mathbf{e}_{j}
$$

- $i = j$ 时，作用方向垂直于面元，正应力
- $i \neq j$ 时，作用方向平行于面元，剪应力

记
$$
\boldsymbol{\sigma} = 
\begin{pmatrix}
\sigma_{11} & \sigma_{12} & \sigma_{13}\\
\sigma_{11} & \sigma_{12} & \sigma_{13}\\
\sigma_{11} & \sigma_{12} & \sigma_{13}\\
\end{pmatrix}
$$
称 $\boldsymbol{\sigma}$ 为一点处的应力状态。

应力分量正向的规定为，正面与坐标轴同向为证，负面与坐标轴反向为正，受拉为正，受压为负。
#### 2、斜面应力公式
考虑下面的四面体微元



设斜面面积为$dS$, 斜面法向量为$\boldsymbol{\nu}$, 则其余各面的面积为
$$
\begin{aligned}
dS_{1} = \Delta PBC = \nu_{1}dS = (\boldsymbol{\nu}\cdot\mathbf{e}_{1})dS, \\
dS_{2} = \Delta PBC = \nu_{2}dS = (\boldsymbol{\nu}\cdot\mathbf{e}_{2})dS, \\
dS_{3} = \Delta PBC = \nu_{3}dS = (\boldsymbol{\nu}\cdot\mathbf{e}_{3})dS, \\
\end{aligned}
$$
四面体体积为
$$
V=\frac{1}{3}dhdS
$$
其中，$dh$ 是顶点到斜面的垂直距离，则四面体微元的平衡条件为
$$
-\boldsymbol{\sigma}_{1}dS_{1}-\boldsymbol{\sigma}_{2}dS_{2}-\boldsymbol{\sigma}_{3}dS_{3} + \boldsymbol{\sigma}_{\boldsymbol{\nu}}dS + \mathbf{f}(\frac{1}{3}dhdS) = 0.
$$
在上式两边同除以$dS$并让微元体的趋于零可得
$$
\begin{aligned}
\boldsymbol{\sigma}_{\boldsymbol{\nu}} &= (\boldsymbol{\nu}\cdot\mathbf{e}_{1})\boldsymbol{\sigma}_{1} + (\boldsymbol{\nu}\cdot\mathbf{e}_{2})\boldsymbol{\sigma}_{2} + (\boldsymbol{\nu}\cdot\mathbf{e}_{3})\boldsymbol{\sigma}_{3}\\
&=\boldsymbol{\nu}\cdot(\mathbf{e}_{1}\boldsymbol{\sigma}_{1} + \mathbf{e}_{2}\boldsymbol{\sigma}_{2} + \mathbf{e}_{1}\boldsymbol{\sigma}_{2})\\
&=\boldsymbol{\nu}\cdot(\mathbf{e}_{1}\sigma_{1j}\mathbf{e}_{j} + \mathbf{e}_{2}\sigma_{2j}\mathbf{e}_{j} + \mathbf{e}_{2}\sigma_{2j}\mathbf{e}_{j})\\
&=\boldsymbol{\nu}\cdot(\mathbf{e}_{i}\sigma_{ij}\mathbf{e}_{j})\\
&=\boldsymbol{\nu}\cdot\boldsymbol{\sigma}
\end{aligned}
$$
斜面应力有很多应用之处，可参见另外一篇文章，不再赘述。
#### 2、平衡方程
考虑正六面体微元的平衡状态，考虑$\mathbf{e}_{1}$方向的平衡状态，由于连续性假设，在正面处对应力泰勒展开，使用线性部分代替，则有
$$
\begin{aligned}
&(\sigma_{11}+\frac{\partial\sigma_{11}}{\partial x_1}dx_{1})dx_{2}dx_{3}-\sigma_{11}dx_{2}dx_{3}\\
+&(\sigma_{21}+\frac{\partial\sigma_{21}}{\partial x_2}dx_{2})dx_{3}dx_{1}-\sigma_{21}dx_{3}dx_{1}\\
+&(\sigma_{31}+\frac{\partial\sigma_{31}}{\partial x_3}dx_{3})dx_{1}dx_{2}-\sigma_{31}dx_{1}dx_{2}\\
+&f_{1}dx_{1}dx_{2}dx_{3}=0.
\end{aligned}
$$
然后除以微元的体积就有
$$
\frac{\partial\sigma_{11}}{\partial x_{1}} + \frac{\partial\sigma_{21}}{\partial x_{2}} + \frac{\partial\sigma_{31}}{\partial x_{3}} + f_{1} = 0.
$$
同理，有
$$
\begin{aligned}
\frac{\partial\sigma_{12}}{\partial x_{1}} + \frac{\partial\sigma_{22}}{\partial x_{2}} + \frac{\partial\sigma_{32}}{\partial x_{3}} + f_{2} = 0.\\
\frac{\partial\sigma_{13}}{\partial x_{1}} + \frac{\partial\sigma_{23}}{\partial x_{2}} + \frac{\partial\sigma_{33}}{\partial x_{3}} + f_{3} = 0.\\
\end{aligned}
$$
用张量记号
$$
\sigma_{ji,j}+f_{i} = 0.
$$
对于弹性动力学问题，根据达朗贝尔原理，把惯性力当做体力可直接导出运动方程
$$
\sigma_{ji,j}+f_{i} = \rho\frac{\partial^{2}u_{i}}{\partial t^2}.
$$

考虑微元体的力矩平衡，通过其形心，沿$\mathbf{e}_{3}$方向取矩。作用线通过形心或者方向同向的力对该轴的力矩均为零，由力矩平衡方程
$$
(\sigma_{12}dx_{2}dx_{3})dx_1 - (\sigma_{21}dx_{3}dx_{1})dx_2 = 0.
$$
所以有
$$
\sigma_{12} = \sigma_{21}.
$$
同理，沿$\mathbf{e}_{1}, \mathbf{e}_{2}$方向取矩
$$
\sigma_{23} = \sigma_{32}, \sigma_{13} = \sigma_{31}
$$
这就是剪应力互等定理，也叫应力张量的对称性。

**平衡方程也可由斜面应力方程导出:**

应用斜面应力公式于三个负面得
$$
\begin{aligned}
\boldsymbol{\sigma}_{-1} &= -\mathbf{e}_{1}\cdot\boldsymbol{\sigma}\\
\boldsymbol{\sigma}_{-2} &= -\mathbf{e}_{2}\cdot\boldsymbol{\sigma}\\
\boldsymbol{\sigma}_{-3} &= -\mathbf{e}_{3}\cdot\boldsymbol{\sigma}\\
\end{aligned}
$$
将三个正面处的应力场在三个负面处泰勒展开，只保留线性项，则有
$$
\begin{aligned}
\boldsymbol{\sigma}_{1} &= \mathbf{e}_{1}\cdot(\boldsymbol{\sigma} + \frac{\partial\boldsymbol{\sigma}}{\partial x_{1}}dx_{1})\\
\boldsymbol{\sigma}_{2} &= \mathbf{e}_{2}\cdot(\boldsymbol{\sigma} + \frac{\partial\boldsymbol{\sigma}}{\partial x_{2}}dx_{2})\\
\boldsymbol{\sigma}_{3} &= \mathbf{e}_{3}\cdot(\boldsymbol{\sigma} + \frac{\partial\boldsymbol{\sigma}}{\partial x_{3}}dx_{3})\\
\end{aligned}
$$
微元体的力平衡条件为
$$
(\boldsymbol{\sigma}_{-1} + \boldsymbol{\sigma}_{1})dx_2dx_3 + 
(\boldsymbol{\sigma}_{-2} + \boldsymbol{\sigma}_{2})dx_3dx_1 + 
(\boldsymbol{\sigma}_{-3} + \boldsymbol{\sigma}_{3})dx_1dx_2 + \mathbf{f}dx_1dx_2dx_3 = 0. 
$$
两边同除以微元体的体积，则有
$$
\mathbf{e}_{1}\cdot\frac{\partial\boldsymbol{\sigma}}{\partial x_1} + \mathbf{e}_{2}\cdot\frac{\partial\boldsymbol{\sigma}}{\partial x_2} + \mathbf{e}_{3}\cdot\frac{\partial\boldsymbol{\sigma}}{\partial x_3} + \mathbf{f} = 0.
$$
即
$$
\mathbf{e}_{i}\cdot\frac{\boldsymbol{\sigma}}{\partial x_i} + \mathbf{f} = 0.
$$
也就是
$$
\nabla\cdot\boldsymbol{\sigma} + \mathbf{f} = 0.
$$

内容参照 **陆明万，罗学富  弹性理论基础 第二版上册**。
---
layout: post
title: Elasiticity-Mechanics-
date: 2020-06-20
categories: continuum mechanics
mathjax: true
tags: [continuum mechanics]
---
本文是连续介质力学的读书笔记。
<!--more-->
### 二、应力与平衡
静力学观点下物体在外力作用下的平衡状态。

听着有些高大上，实际上是物体在静止的时候受到力的作用，用方程表示其平衡状态：内力=外力。

#### 1、内力的刻画-应力
首先看看物体受到外力作用发生了什么，你是不是想说：我哪知道。好吧，那就先看看人受到外力会发生什么。

当你受到外界的压力的时候，你的内心会发生变化，变得焦虑，但这时你也就承受住了压力，说明你体内的内力场与外界的外力场平衡了。
物体受到压力的时候，物体发生了变形，改变了分子间距，物体内形成了一个内力场，当变形不再继续时，内外力场平衡。

考虑一个处于平衡状态的物体 $B$, 用一个假想的曲面 $S$ 将物体分成内域外域两部分，在曲面上任取一点 $P$, $\boldsymbol{\nu}$是该点处的单位外法向量, 以 $P$ 为形心在 $S$ 上取一个面积为 $\Delta S$ 的微元，外域通过该微元作用到内域的合力为 $\Delta \mathbf{F}$, 则可定义作用在 $P$ 点处法线为 $\boldsymbol{\nu}$ 的面元上的应力矢量为
$$
\boldsymbol{\sigma}_{\boldsymbol{\nu}} := \lim_{\Delta S\rightarrow 0} \frac{\Delta \mathbf{F}}{\Delta S}
$$
- $\Delta S$ 是变形前的面积，工程应力，名义应力，用于小变形。
- $\Delta S$ 是变形后的面积，真实应力

那么问题来了，为什么就不能谈一点处的应力矢量，而非要指定一个作用面呢？我的个人理解是讨论一点处的平衡状态使得模型过于简化，不能完全描述物体在该点处内力的状态, 不能刻画剪切作用。 

为了谈论一点处的平衡状态需要谈论什么？平衡当然是指在任意一点处，任意作用面上的合力为零。由于任意一点处的法向都可以用三个基矢量表示，因此考虑过这一点处的三个作用面，法向分别为$\mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3$, 在三个方向上建立平衡方程就完全表达出了这一点出的平衡状态。

那么接下来的问题就是如何表示一点处沿着法向量为$\mathbf{\nu}$的作用面的内力？当然我们是不可能凭空知道的，假设已知这一点处，作用在法向为三个基矢量的面元上的应力矢量已知，分别为$\boldsymbol{\sigma}_{1}, \boldsymbol{\sigma}_{2}, \boldsymbol{\sigma}_{3}$，将这三个应力矢量按照基矢量的方向进行分解，
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
其中，$i = 1, 2, 3.$  对法向为 $\boldsymbol{\nu} = \nu_{i}\mathbf{e}_{i}$ 的作用面，作用在其上的应力矢量则可由三个基本的应力矢量表出
$$
\boldsymbol{\sigma}_{\boldsymbol{\nu}} = \nu_{i}\boldsymbol{\sigma}_{i} = \boldsymbol{\nu}\cdot(\mathbf{e}_{i}\boldsymbol{\sigma}_{i}) = \boldsymbol{\nu}\cdot(\mathbf{e}_{i}\sigma_{ij}\mathbf{e}_{j})=\boldsymbol{\nu}\cdot(\sigma_{ij}\mathbf{e}_{i}\mathbf{e}_{j}) = \boldsymbol{\nu}\cdot\boldsymbol{\sigma}
$$
其中，$\nu_{i} = cos(\boldsymbol{\nu},\mathbf{e}_{i})$, 这就是斜面应力公式(柯西公式)，也可由四面体微元的平衡条件导出。将斜面应力沿坐标轴方向分解
$$
\boldsymbol{\sigma}_{\boldsymbol{\nu}}=\nu_{i}\sigma_{ij}\mathbf{e}_{j} = \sigma_{\boldsymbol{\nu}j}\mathbf{e}_{j}
$$
则有
$$
\sigma_{\boldsymbol{\nu}j}=\nu_{i}\sigma_{ij}.
$$
柯西公式有两个重要的应用：

- 求斜面上的各种应力。

   - 斜面应力的大小：
   $$
   \sigma_{\boldsymbol{\boldsymbol{\nu}}}=\sqrt{\sigma_{\boldsymbol{\nu}j}\sigma_{\boldsymbol{\nu}j}}
   $$

   - 斜面应力的方向：
   $$
   cos(\boldsymbol{\sigma_{\boldsymbol{\nu}}},\mathbf{e}_{j}) = \frac{\sigma_{\boldsymbol{\nu}j}}{\sigma_{\boldsymbol{\nu}}}
   $$

   - 斜面正应力：斜面应力在斜面法方向的分量 
   $$
   \begin{aligned}
   \boldsymbol{\sigma}_{\mathbf{n}}=(\boldsymbol{\sigma}_{\boldsymbol{\nu}}\cdot\boldsymbol{\nu})\boldsymbol{\nu}=\sigma_{\mathbf{n}}\boldsymbol{\nu}\\
   \sigma_{\mathbf{n}}=\boldsymbol{\nu}\cdot\boldsymbol{\sigma}\cdot\boldsymbol{\nu}=\sigma_{ij}\nu_{i}\nu_{j}
   \end{aligned}
   $$

   - 斜面剪应力： 斜面应力在斜面上的分量
   $$
   \boldsymbol{\tau} = \boldsymbol{\sigma}_{\boldsymbol{\nu}}-\boldsymbol{\sigma}_{\mathbf{n}}
   $$

- 给定力边界条件

   若斜面是物体的边界面，给定面力 $\mathbf{p}$, 则可根据柯西公式表达出应力场的力边界条件
   $$
   p_{j}=\nu_{i}\sigma_{ij}.
   $$
#### 2、平衡方程
物体 $B$ 处于平衡状态时，则其中的任意有限体积 $V$ 也处于平衡状态, 则有
$$
\int_{\partial V}\mathbf{n}\cdot\boldsymbol{\sigma}dS + \int_{V}\mathbf{f}dV = \int_{V}\rho\ddot{\mathbf{u}}dV
$$
利用 $Gauss$ 散度定理，则有
$$
\int_{V}\nabla\cdot\boldsymbol{\sigma}dS + \int_{V}\mathbf{f}dV = \int_{V}\rho\ddot{\mathbf{u}}dV
$$
由于 $V$ 是任意的，因此有
$$
\nabla\cdot\boldsymbol{\sigma} + \mathbf{f} = \rho \ddot{\mathbf{u}}.
$$
考虑物体角动量变化是由外力引起的
$$
\dot{\mathbf{A}}(V) = \int_{V}(\mathbf{y}-\mathbf{y}_0)\times \mathbf{f}dV
$$
有限体积的角动量变化有
$$
\begin{aligned}
\dot{\mathbf{A}}(V) &= \frac{d}{dt}\int_{V}(\mathbf{y}-\mathbf{y}_0)\times \rho\dot{\mathbf{y}}dV\\
&=\int_{V}(\mathbf{y}-\mathbf{y}_0)\times \rho\ddot{\mathbf{y}}dV\\
&=\int_{V}(\mathbf{y}-\mathbf{y}_0)\times (\nabla\cdot\boldsymbol{\sigma}+\mathbf{f})dV\\
\end{aligned}
$$
则有
$$
\int_{V}(\mathbf{y}-\mathbf{y}_0)\times (\nabla\cdot\boldsymbol{\sigma})dV=0
$$
从而有
$$
\begin{aligned}
(\mathbf{y}-\mathbf{y}_0)\times (\nabla\cdot\boldsymbol{\sigma}) = 0\\
\end{aligned}
$$
从这里可以导出剪应力互等原理($\sigma_{ij} = \sigma_{ji}$).
内容参照 **陆明万，罗学富  弹性理论基础 第二版上册**。
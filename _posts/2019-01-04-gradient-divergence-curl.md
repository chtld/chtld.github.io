---
layout: post
title: 梯度-散度-旋度
date: 2019-01-04
categories: vector caculus
tags: [矢量微积分]
---
本文是矢量微积分笔记！
<!--more-->
### 一、场的定义  
场是空间位置的函数，之所以称为场是因为更在乎的是这个量的物理意义，反映了其在空间上每一个点的处处存在的特性，例如：
- $\phi: \mathbb{R}^3 \to R$, 标量场，标量函数
- $\mathbf{\Phi}: \mathbb{R}^3 \to \mathbb{R}^3$, 矢量场，矢量函数，即每一个分量都是空间位置的函数。  

诸如此类还可以定义张量场等。  
#### 电场
静电学本身依赖于三个实验事实：
- 电荷存在，正电荷、负电荷，任何物质都有电荷，正负电荷等量出现以至于物质的静电量为0.
- 库仑定律，力的大小与它们所带电量的乘积成正比，与它们之间距离的平方成反比，方向沿着点电荷的连线。
$$
\mathbf{F} = K\frac{qq_0}{r^2}\mathbf{\hat{u}},
$$
其中$\mathbf{\hat{u}}$ 是 q 指向 $q_0$ 的方向向量， $K = \frac{1}{4\pi\epsilon_0}$, $\epsilon_0$ 是真空介电常数。

- 叠加原理，静电力是矢量相加，两个带电粒子之间的力不会因为其他带电粒子的存在而改变。  

引入一个与位置相关的矢量函数，就是电场强度 $\mathbf{E(r)}$.
$$
\mathbf{E(r)} = \frac{\mathbf{F(r)}}{q_0}=K\frac{q}{r^2}\mathbf{\hat{u}},
$$
即点电荷 $q$ 在距离它 $\mathbf{r}$ 处产生的电场强度。  
假设有N个电荷$q_1, q_2, ..., q_N$, 其位置坐标为 $\mathbf{r}_1, \mathbf{r}_2, ..., \mathbf{r}_N$, 它们对 $\mathbf{r}$ 处的电荷 $q_0$ 的作用力为
$$
\mathbf{F(r)} = \sum_{l = 1}^N\frac{q_0q_l}{|\mathbf{r-r_l}|^2}\mathbf{\hat{u}}_l,
$$
其中，$\mathbf{\hat{u}}_l = \frac{\mathbf{r-r_l}}{|\mathbf{r-r_l}|}$, 则这些电荷在 $\mathbf{r}$ 处产生的电场强度为
$$
\mathbf{E(r)} = \sum_{l = 1}^N\frac{q_l}{|\mathbf{r-r_l}|^2}\mathbf{\hat{u}}_l,
$$
即是各个电荷的电场强度的叠加。引入静电场的好处有
- 可以根据已知电荷的分布来计算电场，而不必担心这些电荷对它们附近电荷的影响
- 可以计算一个已知的电场对点场内的电荷的影响而不必担心电场的电荷分布

和在定义质量密度是一样，认为质量的分布是均匀的。可以定义电荷密度，认为电荷是均匀分布的。
体积为$\Delta V$ 的空间区域内的电量为 $Q$, 定义电荷密度为
$$
\bar{\rho}_{\Delta V}=\frac{\Delta Q}{\Delta V},
$$
通过假设电荷是连续分布的，可以定义一点处的电荷密度
$$
\rho(x,y,z) = \lim_{\Delta V\to 0, in(x,y,z)}\frac{\Delta Q}{\Delta V} = \lim_{\Delta V\to 0, in(x,y,z)}\bar{\rho}_{\Delta V},
$$
从而
$$
Q=\iiint_V\rho(x,y,z)dV,
$$
电场强度则可表示为
$$
\mathbf{E(r)}=\frac{1}{4\pi\epsilon_0}\iiint_V\frac{\rho(\mathbf{r'})\hat{\mathbf{u}}(\mathbf{r'})}{|\mathbf{r-r'}|^2}dV'.
$$
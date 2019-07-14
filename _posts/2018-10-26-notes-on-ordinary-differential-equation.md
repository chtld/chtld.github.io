---
layout: post
title: 常微分方程笔记(1)
date: 2018-10-26
categories: 技术
tags: [微分方程]
---
本文记录了学习常微分方程的过程。
<!--more--> 

#### 一. Recall Fundamental Theorem of Calculus(FTC)
1. 由$f(x)$来找到其原函数(反导函数)

 $$F(x) = \int_a^xf(t)dt \Rightarrow F'(x) = f(x)$$
2. 利用任一$f(x)$的反导函数计算$f(x)$之定积分

 $$\int_a^bf(x)dx = F(b) - F(a)$$
 微积分基本定理反映了导函数与其反导函数之间的关系。那么我们提出的问题是$F(x)$与$f(x)$之间有没有什么类似与代数方程式的关系？
 考虑$f(x),F(x)$,令$X = f(x), Y = F(x)$,视$X,Y$为代数，则$X,Y$之代数方程式就是$F(x)$的微分方程式。
- 例如，$u(x)$满足$\dot{u}(x) = u(x)$, 一个函数的导函数是他本身，其解$u(x) = e^x + c$. There are infinitely many solutions. $u(x) = ae^x + c$也是它的解。
 实际生活中观察的现象只有一种，多解现象不太容易发生，所以希望有唯一解，因此需要加入其他条件。
 
- $$\begin{cases}
  u'(x) = u(x)\\
  u(0) = A\\
  \end{cases} 
  $$
 实际问题变化因素有很多，在什么时间，什么位置，初始的状态是什么，所以方程有很多。有很多种类的方程刻画不同的现象。

#### 二. Big Picture
for ODE
1. 应用问题.
2. 导出其数学模式(math model).
3. 分析此数学模式
  - 质：解的性质，qualitative analysis.
  - 量：正确解, quantative analysis.
4. 此数学模式是否是正确的，well-posed.
  - 解之存在(existence)
  - 解之唯一性(uniqueness), 观察到的现象只有一个
  - continuity，稳定性，初始条件差不多，观察到的现象应该也差不多
  - 不满足上面的问题称为ill-posed的问题，初始条件差不多，结果却相差很大，蝴蝶效应，混沌现象.
5. back to practical problem.
  从简单到复杂，从已知到未知。

#### 三. Some notations and some terminology to simplify our analysis
$$x\rightarrow f(x)$$
$$x\rightarrow f'(x)$$
$f\rightarrow f'$, functional, operator
from now on:
t: independent variable
y(t)
$y\rightarrow y'$, 微分算子
Example for operators：
- $y\rightarrow y'+y$
  $L = \frac{d}{dt}+I$
- $y'(t) + (t^2 - s)y(t)$
  $L = \frac{d}{dt}+g(t)I$

#### 四. 一阶微分算子与一阶微分方程
first order 方程式 $L[y] = b(t)$
first order means 只能包括$y,y'$
linear means 只能包括$y,y'$的一次方,eg. $L[y] = t(y')^{1/2} + 5y$ is nonlinear
$L[y] = A(t)y' + B(t)y=A(t)[y' + \frac{B(t)}{A(t)}y] = A(t)[y' + g(t)y]$
Now, a 1st order linear ode has the form
$L[y] = b(t)$, where $L[y] = y' + g(t)y = b(t)$
maybe written as
$y'(t) = a(t)y(t) + b(t)$.
线性化的关键：
linearity of 充要条件
Given any two constants p and q, then
$L[pu + qv] = pL[u] + qL[v]$
$u\rightarrow L[u]$
$v\rightarrow L[v]$
$pu+qv\rightarrow L[pu + qv] = ?$
$L[u] = u' + g(t)u$
$L[pu + qv] = pu' + pg(t)u + qv' + qg(t)v = pL[u] + qL[v]$
Example for first order nonlinear equation:
$N[y] = (y')^2+y$
$N[y+y^*]?=N[y]+N[y^*]$
we can obtain
$N[y+y^*]=(y'+y^{*'})^2+y+y^*=N[y]+N[y']+2y'y^{*'}$
##### 1st order linear equation
- $b(t)=0,L[y]=y'+g(t)y=0,or,y'=a(t)y$,named as 1st order,homogeneous linear equation
- $b(t)\neq 0,L[y]=y'+g(t)y=b(t),or,y'=a(t)y+b(t)$,named as 1st order,non-homogeneous linear equation
About homogeneous equation:
(1) 有何特质？
(2) 如何解？(existence of solutions)隐含着所有解之问题。
$L[y] = y + a(t)y=0$
(A) Linear Principle
任意两个解相加减仍是原方程的解。若$L[y_1] = 0,L[y_2] = 0$,then $L[y_1+y_2] = 0,L[ky_1] = 0.$
对于非齐次的情况则不成立，若$L[y_1] = b(t),L[y_2] = b(t)$,then $L[y_1+y_2] = 2b(t) \neq b(t)$
#### 五. 一阶微分方程解之技巧
- $$L[y] = y' + g(t)y = 0, y' = a(t)y$$
$$\frac{dy}{dt} = a(t)y$$
$$\frac{dy}{y} = a(t)dt$$
$$\int\frac{dy}{y}=\int a(t)dt \Rightarrow ln|y|+c = \int a(t)dt$$
$$e^{ln|y|+c} = e^{\int a(t)dt}$$
then we will obtain

$$|y| = e^{-c}e^{\int a(t)dt} = ke^{\int a(t)dt}$$
since $|y|\neq 0$ and $y$ is continuous, so either $y(t)>0$ or $y(t)<0$对所有的t都成立.
If $y>0$, $y = ke^{\int a(t)dt}$, if $y<0$, $y = -ke^{\int a(t)dt}$.
If $y = ke^{\int a(t)dt}$, for any k, then $L[y] = 0$, 即 $y' = a(t)y$.
Here, we found that if $L[y] = 0$, then all solutions $y(t) = ke^{A(t)}$, where $A(t)$ a particular anti-derive of $a(t)$.
A concrete example:
$y' = cos(t)y$,here $a(t) = cos(t)$, $A(t) = sin(t)$, then the general solution $y(t) = k e^{sin(t)}$, for any k.

- $L[y] = b(t)$(non-homogeneous), or $y' = a(t)y + b(t)$.
Recall "Linear Principle" is true for homogeneous equation, now , extended linearity principle for non-homogeneous equation.
If $L[y_1] = b(t)$ and $L[y_2] = b(t)$, then
(1) $L[y_h + y_1] = b(t)$, where $y_h$ satisfies $L[y_h]=0$.
(2) $L[y_1-y_2] = 0$.
the fact, from (1), (2),$\Rightarrow$ the general solution of $L[y] = b(t)$ are $y_h+y_1$.
proof: 
(1) $L[y_h + y_1] = L[y_h] + L[y_1] = b(t)$.
(2) $L[y_1 - y_2] = L[y_1] - L[y_2] = 0$.
Suppose y_h and y_2 are two solutions of $L[y] = b(t).$, then by (2), $y_1-y_2$ is a solution, say $y_h(t)$ of $L[y]=0$,$y_1 = y_h(t) + y_2$, 即$y_h(t) + y_p(t)$ is a general solution of $L[y] = b(t)$.
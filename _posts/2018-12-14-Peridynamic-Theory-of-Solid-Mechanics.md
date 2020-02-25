---
layout: post
title: Peridynamic-Theory-of-Solid-Mechanics
date: 2018-12-14
categories: peridynamic
mathjax: true
tags: [peridynamics]
---
本文是关于近场动力学的一篇总结性文章[Peridynamic-Theory-of-Solid-Mechanics](https://www.sciencedirect.com/science/article/pii/S0065215610440028)的读书笔记。
<!--more-->

### 1.Introduction
#### 1.1 近场动力学的目的
近场动力学理论试图统一连续介质、断裂、离散粒子的的数学模型于一个单一的框架。该理论是通过把经典的固体力学中的偏微分方程替换为积分方程或积分微分方程来达到这一目的的。这些方程是基于用有限范围的物质点之间的相互作用来刻画物体的内力建立的。
固体力学的经典理论是基于物体内的质量是连续分布的这一假设。它进一步假设内力是接触力[73]。对固体的数学描述伴随着这些假设, 并且由于使用了偏微分方程的工具就额外假设了变形的光滑性，在强形式和弱形式中体现。经典理论已经被证实在真实的材料响应的直到小尺度时提供了一个很好的近似，尤其在单晶体中，满足这些假设[52]. 尽管如此，但是科技的增长涉及到了在更小的尺度下设备的设计和制造，甚至到了原子尺度。因此，研究经典理论能否放松连续性假设，允许包括离散粒子的模型(比如原子)，能否允许对非局部力的刻画(已知对材料的行为有很大的影响)。  
类似的考虑应用到断裂和其他不连续问题上：经典理论的偏微分方程系统不能直接应用到一个裂纹或者是位错上，因为在这些点处的变形是不连续的。因此，断裂力学的技巧是介绍的关系是外来追加的到经典理论的场方程上的。例如，线弹性断裂力学考虑裂纹的发展是根据一个分离的本构模型依赖一些附近的条件来预测裂纹生长的多快？沿着什么方向？是否应该停止，分叉等等。尽管断裂力学的方法给许多应用提供了可靠的工具，但在什么程度上这个方法可以满足一般条件下复杂介质断裂刻画的需要是不确定的，尤其在小尺度下这个问题更加明显。类似的考虑也应用到位错动力学，位错的运动是由追加的关系确定的。  
在线弹性断裂力学和位错动力学中，缺陷的生长除了需要补充的本构方程之外，经典力学在奇异点的的附近预测到了非物理的特征。无界的应力和应变能密度是经典偏微分方程系统在理想情况通过假设其影响限制在裂尖附近的发生区域或在位错的核心处预测得到的[38]。然而，当条件和几何非常复杂的时候，按这种方式忽视奇异性之后的推理就变得更加麻烦。例如，当位错核心移动的靠近或跨过颗粒边界，它的能量是不变的并不清楚。能量核心的任何变换会影响在位错上的驱动力。  
分子动力学提供了一种在最小的尺度下理解材料的力学行为的方式，并在这些年取得了巨大的成功。然而，就算用最快的计算机，分子动力学也不能模拟相当尺寸的系统，来使得其成为连续介质力学可能的替代。  
基于这些考虑就催动了近场动力学的产生，它尝试用与连续变形相同的场方程来处理间断的演化问题。近场动力学有着使用相同的场方程来处理离散粒子与连续介质的目标。这个模型用相同的数学系统来处理宏观尺度和纳米尺度的问题，使得这个方法在发展多尺度以及原子到连续介质的方法方面是一个具有吸引力的框架。  
#### 1.2 Summary of the Literature
近场动力学首先出现在文献[60]中，源于希腊词根 "near" 和 "force" 。在[60]中，这个模型把连续固体中的内力看做成对的相互作用网，类似于弹簧。在这方面它类似于 Navier 的固体理论(见第6节)。在近场动力学模型中，弹簧可以是非线性的。弹簧的响应取决于它们在参考构型中的方向(导致了各向异性)和它的长度。两个物质点通过一个弹簧相互作用的最大距离称之为近场半径(horizon), 一个点不能'看到'超过近场半径的点。近场半径在[60]中是反映材料性质的常数。在最初的近场动力学理论中提出的运动方程为
$$
\rho(x)\ddot{u}(x,t) = \int_{\mathcal{H}}f(u(x',t)-u(x,t),x'-x)dV_{x'} + b(x,t)
\tag{1}
$$
其中$x$是物体$\mathcal{B}$的参考构型中的位置向量，$\rho$ 是密度，$u$ 是位移，$b$ 是体力密度. $\mathcal{H}$ 是 $x$ 的 $\delta$ 邻域，$\delta$ 是材料的近场半径。本构关系是由对力函数 $f(\eta,\xi)$ ($\xi = x'-x$ 是键，$\eta = u'-u$ 是相对位移)。$f$ 可以非线性的依赖于 $\eta$ ，而且没有假设参考构型中的键力是 0。$f$ 的单位是 $N/m^2$. 线性化运动方程得到的表达式形式上与 Kunin's 的非局部理论[46,47]相同, 尽管本构模型和其他层面是不同的，两个模型的比较在 6.5 节中讨论.  
已经有大量的文章对线性近场动力学的不同方面进行了研究。在文献[70]中考虑了一个无限长的杆的静力载荷. 得到的解(使用了傅里叶变换得到的)展示了有趣的特征，而这并没有在经典平衡方程中出现。其中振幅在远离载荷的地方衰减，是方程中非局部性的结果（这些特征的物理意义并不明确）. [60]中导出了各向同性材料的色散曲线、变分形式以及材料稳定性的一些方面。Zimmermann[80] 探究了理论的许多特征，包括波运动、材料的稳定性以及数值解的技巧等。Zimmermann 也研究了在这个理论下断裂生长的能量守恒。  
Weckner 和 Abeyaratne [75] 研究了一维杆的动力学并且得到了解得格林函数表示。他们同时位移场间断点演化的表达式。稳定的间断点(即，间断点不随着时间无限增长)在一定的初始数据下出现，甚至伴随着材料性质的良好表现。对其他材料，间断点随着时间无限增长，导致了材料的不稳定性。对于三维无界弹性各向同性固体的格林函数在[77]中考虑(对静力学和动力学问题)。这个工作同时也对线弹性固体的局部和近场动力学理论做了比较。  
Alali 和 Lipton [3]，Du 和 Zhou [18,19]，以及 Emmrich 和 Weckner [20,21]建立了线性近场动力学线动量守恒的各种存在性和唯一性结果。这些文章也刻画了与等经典线弹性方程弱解的等价性，和确切的说，它表明了近场动力学方程在非局部消失的极限条件下的适定性。 特别是在给定充分的边界数据和材料属性的正则性条件下，极限解与传统的弱解一致。 在非局部稳态扩散的物理背景下，Gunzburger 和 Lehoucq [35]引入了非局部高斯定理和非局部格林公式建立了非局部边值问题的适定性。  
[60]中概述的近场动力学理论在可以建模的材料行为的范围受到严重的限制，特别是对各向同性材料Possion比总是1/4。这就促使了重新思考整个近场动力学理论。结果是一个概念，它保留了在成对粒子之间的键携带力的想法。然而，在新方法中，每个键内的力并不能相互独立的确定。相反，每个键力取决于键的每个端点的家族内所有点的集体变形（可能还有变形的速率和历史）。由此产生的修正理论被称为基于状态(state-based)的，因为这个数学对象传达的键的集体变形的信息称为近场动力学态。本文中的技术讨论涉及的主要是基于态的理论，但是早期的基于键的理论被证明是一个基于态的特例。态基的理论在[67]中有更详细的讨论，其中包括一个特定的各向同性固体材料模型其中可以规定任何泊松比。  
在[67]中也显示，通过对变形梯度张量的非局部近似，任何经典理论中的弹性本构模型可以适用于近场动力学理论。应用这个技巧到应变硬化塑性模型中可见文献[74,27]。经典本构模型中的应力张量也用一种类似的方式映射到键力（见4.11节）。  
近场动力学应力张量在[48]中导出，之前在[83]中就讨论了一个类似的概念。近场动力学应力张量有着与经典理论中Piola应力张量类似的力学解释。它给出了通过任意虚拟的内部界面的单位面积的力。然而，在近场动力学的情况下，应力张量是非局部的：涉及的力是非局部键力，它从表面的一边倒另一边。对于内力密度的近场动力学算子可以准确表示为近场动力学应力张量场的散度. 因此，近场动力学运动方程就与经典方程形式上相同.  
键基近场动力学理论到经典弹性方程的收敛性由 Zimmermann [83]中论述，在各向同性线弹性固体的背景下则由Emmrich和Weckner[21]中给出. 在态基近场动力学本构建模的框架下，[68]中展示了如果变形是经典光滑的，对内力密度的近场动力学算子趋于经典算子，在$\delta\rightarrow 0$时(见6.3节)。这个极限过程产生了一个对Piola应力的经典本构模型，在$\delta\rightarrow 0$的情况下。在这种意义下，近场动力学理论收敛到经典理论。  
Sears 和 Lehoucq [58] 给出了近场动力学线动量平衡的统计力学基础。相互作用力的非局部性是本质的，源于分子间的相互作用。分析类似于Irving和Kirkwood[39]中里程碑式的工作，他们的目标是从随机物理中导出经典场方程。经典线动量守恒是更一般的近场动力学守恒的一个推论，当积分算子表示为应力张量的散度。在对势的重要特殊情况，Noll[58,49]实际上导出了近场动力学线动量守恒作为从随机力学原理导出经典守恒律的中间步骤。  
Gerstle et al. 推广了近场动力学模型到扩散过程，包括高电流密度引起的热传导和物种迁移[31]。他们应用了多物理机理的组合非局部方程，包括特殊的扩散，热传导，力学，电传导等，到一个演示由于电迁移导致的电子零件故障的模型问题当中。  
几乎所有的近场动力学模型的应用依赖于数值解。一个近似近场动力学场方程的数值技巧在[61]中提出。这个数值方法简单的把(1)中的体积积分替换为有限和：
$$
\frac{\rho_i}{h^2}(u_i^{n+1}-2u_i^n+u_i^{n-1}) = \sum_{j\in\mathcal{H}}f(u_j^n-u_i^n,x_j-x_i)V_i+b_i^n
$$
其中$i$是节点数，$n$是时间步数，$h$是时间步长，$V_i$是参考构型中节点$i$的体积. 这个数值方法是无网格的，因为离散节点之间没有几何上的联系。一维情况下离散方法的自适应细分和收敛性在[11]中讨论。  
通过导致相互作用节点之间的键被不可逆的破坏，损伤被纳入数值方法中。尽管破坏在所有键之间独立的出现，但它们的破坏倾向于沿着称为裂缝的二维表面自组织。裂缝自主的发展：它们的发展仅由场方程和本构模型在键的层面确定。并没有附加的关系来表明裂纹的生长。特别的，没有用到应力强度因子。由于方程的非局部特性，裂尖附近的场的数值结果是有界的。一个对于Kalthoff-Winkler问题的计算机的解决方案在[61]中给出，这是在计算断裂力学中重要的基准问题。额外的例子以及数值方法的细节在[65,76]中讨论。  
### 2.Balance Laws
本章以更系统的方式导出了近场动力学中的守恒律(线动量守恒，角动量守恒)，并阐述了在一个物体的子区域内的整体能量守恒，从而导出了局部能量守恒。能量守恒包括了热传导功率和机械功率。整体能量守恒考虑到了子区域的吸收功率(absorbed power)和输入功率(supplied power). 一个重要的结果是根据这些功率定义的内能是一个增量，从而导出了有意义的内能密度的概念。
线动量守恒，角动量守恒，能量守恒是以一种规范的结构展示的，我们称之为主平衡律(master balance law). 主平衡律表示了子区域内增量的变化来自于内外点的相互作用加上源项的贡献。物质点之间的相互作用是积分算子中的被积函数，被积函数的反对称性允许把积分算子写为非局部流量的散度的积分。
#### 2.1 Balance of Linear Momentum
$\mathcal{B}$表示物体，参考构型，是一个有界闭区域，密度为$\rho$. $y(\cdot,\cdot)$表示物体的运动，$y(x,t)$是$t\ge 0$时物质点$x\in\mathcal{B}$的位置，$\mathcal{B}$在变形后记为$\mathcal{B}_t$. 定义速度场为
$$
v(x,t)=\dot{y}(x,t), \forall x\in\mathcal{B}, t\ge 0
$$
$b$是外载荷力密度场。令$L(x,t)$表示在(x,t)处的由于$x$与其他粒子相互作用产生的力密度。在一个子区域$\mathcal{P}\subset\mathcal{B}$内的力向量是
$$
\int_{\mathcal{P}}(L+b)dV,
$$
注意积分是在参考构型上进行的。对这个子区域使用牛顿第二定律有
$$
\frac{d}{dt}\int_{\mathcal{P}}\rho\dot{y}dV = \int_{\mathcal{P}}\rho \ddot{y}dV = \int_{\mathcal{P}}(L+b)dV,\tag{2}
$$
即，通过局部化，运动方程为
$$
\rho(x)\ddot{y}(x,t) = L(x,t) + b(x,t),\forall x\in\mathcal{B},t\ge 0.\tag{3}
$$
对整个物体$\mathcal{B}$使用牛顿第二定律有
$$
\frac{d}{dt}\int_{\mathcal{B}}\rho\dot{y}dV = \int_{\mathcal{B}}bdV.\tag{4}
$$
在$(2)$中令$\mathcal{P} = \mathcal{B}$,再与$(4)$中结果比较则有$L$一定是自平衡的：
$$
\int_{\mathcal{B}}L(x,t)dV_x=0,\forall t\ge 0.
$$
令$f(\cdot,\cdot,\cdot)$是向量值函数使得
$$
L(x,t) = \int_{B}f(x',x,t)dV_{x'}, \forall x\in\mathcal{B},t\ge 0.\tag{5}
$$
并且$f$是反对称的：
$$
f(x,x',t) = -f(x',x,t),\forall x,x'\in\mathcal{B},t\ge 0.\tag{6}
$$
对于给定的$L$，这样的$f$总能找到，例如：
$$
f(x,x',t) = \frac{1}{V}(L(x,t) - L(x',t)) \tag{7}
$$
其中$V$是$\mathcal{B}$在参考构型中的体积. 函数$f$在近场动力学中扮演着重要的角色, 称为对偶力密度(dual force density), 单位是$N/m^{-6}$.一般向量$f(x',x,t)$和$f(x,x',t)$不与向量$y(x't)-y(x,t)$平行。$(7)$中$f$的选择并没有什么实际意义，只不过说明了对于给定的$L$，这样的$f$存在. 在实际应用中，$f$由变形通过本构关系确定.
利用$f$的反对称性就可以把在一个子区域上的线动量守恒表示为$f$仅连接$\mathcal{P}$内部的点与其外部$\mathcal{B} \ \mathcal{P}$的点。由于$f$的反对称性
$$
\int_{\mathcal{P}}\int_{\mathcal{P}}f(x',x,t)dV_{x'}dV_x = 0.\tag{8}
$$
由$(2),(5),(8)$则有
$$
\frac{d}{dt}\int_{\mathcal{P}}\rho\dot{y}(x,t)dV = \int_{\mathcal{P}}\int_{\mathcal{B}\setminus \mathcal{P}}f(x,x',t)dV_{x'}dV_x + \int_{\mathcal{P}}b(x,t)dV_x.\tag{9}
$$
下面说明$(9)$对任意区域$\mathcal{P}\subset\mathcal{B}$成立$\Leftrightarrow (6)$成立。前面已经说明了反方向的箭头是成立的，因此下面只需说明反方向的箭头也成立即可。
对任意子区域$\mathcal{N}\subset\mathcal{B}$和$\mathcal{N}'\subset{B}$, 满足$\mathcal{N}\cup\mathcal{N'}=\varnothing$. 定义$\mathcal{R}\ (\mathcal{N}\cup\mathcal{N}')$. 因为$\mathcal{B\setminus N=N'+R}, \mathcal{B\setminus N' = N + R}$, 因此不论$f$反对称与否都有
$$
[\int_{\mathcal{N}}\int_{\mathcal{B\setminus N}}+\int_{\mathcal{N'}}\int_{\mathcal{B\setminus N'}}-
\int_{\mathcal{N}}\int_{\mathcal{N'}}-\int_{\mathcal{N'}}\int_{\mathcal{N}}-\int_{\mathcal{N\cup N'}}\int_{\mathcal{R}}]f(x',x)dV_{x'}dV_x = 0.\tag{10}
$$
由于积分算子的线性性，则有
$$
[\int_{\mathcal{N}}+\int_{\mathcal{N'}}-\int_{\mathcal{N\cup N'}}](\rho\ddot{y}(x,t)-b(x,t))dV_x = 0,
$$
根据$(9)$式，则有
$$
[\int_{\mathcal{N}}\int_{\mathcal{B\setminus N}}+\int_{\mathcal{N'}}\int_{\mathcal{B\setminus N'}}-\int_{\mathcal{N\cup N'}}\int_{\mathcal{R}}](\rho\ddot{y}(x,t)-b(x,t))dV_x = 0.
$$
带入$(10)$则有
$$
[\int_{\mathcal{N}}\int_{\mathcal{N'}}+\int_{\mathcal{N'}}\int_{\mathcal{N}}]f(x,x') = 0.
$$
由于这个方程对任意不想交的$\mathcal{N, N'}$成立, 因此$(9)$蕴含着$(6)$.
为了方便，可以不准确的认为$f(x',x,t)$在物理上表示粒子$x'$对$x$的力向量$(N/m^6)$。这个解释不准确是因为粒子$x,x'$并没有直接的物理联系来产生力.例如，$L$给定，则由$(7)$可以生成$f$，并不论粒子$x,x'$之间有没有物理联系，比如弹簧。
对于给定的$f$场满足$(5),(6)$, 令$t(\cdot,\cdot,\cdot)$表示一个向量值函数满足
$$
f(x',x,t) = t(x',x,t)-t(x,x',t),\forall x,x'\in \mathcal{B},t\ge 0.\tag{11}
$$
这样的$t$函数总能找到。例如：
$$
t(x,x',t) = \frac{f(x',x,t)}{2},\forall x,x'\in\mathcal{B},t\ge 0.
$$
函数$t$称为键力密度(bond force density)，是近场动力学理论中由本构模型产生的基本量。
简化记号：
$$
t = t(x',x,t), t' = t(x,x',t),\\
f = f(x',x,t), f' = f(x,x',t),\\
y = y(x,t), y' = y(x',t),\\
\rho = \rho(x), b = b(x,t),\\
L = L(x,t),
dV = dV_x, dV' = dV_{x'}.
\tag{12}
$$
由$(5),(11)$有
$$
L = \int_{\mathcal{B}}(t'-t)dV'.\tag{13}
$$
由$(9),(11)$有, 对任意子区域$\mathcal{P\subset B}$
$$
\frac{d}{dt}\int_{\mathcal{P}}\rho\dot{y}dV = \int_{\mathcal{P}}\int_{\mathcal{B}\setminus \mathcal{P}}(t-t')dV_{x'}dV_x + \int_{\mathcal{P}}bdV_x.\tag{14}
$$
由$(3),(5)$, 局部的线动量守恒为
$$
\rho(x)\ddot{y} = \int_{B}fdV_{x'} + b,\forall x\in\mathcal{B},t\ge 0.\tag{15}
$$
或者等价的有
$$
\rho(x)\ddot{y} = \int_{\mathcal{B}}(t'-t)dV' + b,\forall x\in\mathcal{B},t\ge 0.\tag{16}
$$
局部的线动量守恒也被称为运动方程. 在$(16)$中令$\ddot{y} = 0$, 平衡方程就是
$$
\int_{\mathcal{B}}(t'-t)dV' + b = 0,\forall x\in\mathcal{B}.\tag{16}
$$
$(14)$中的双重积分表示通过$\mathcal{P}$的边界的线动量的非局部通量。这一项就类似于经典局部理论子区域上的接触力。方程$(14)$就是非局部平衡原理的一个例子，它的结构将在2.5节中讨论。
#### 2.2 Principle of Virtual Work
边界条件和初值条件可以整合到线动量守恒$(16)$中，通过形成变分问题[51].令 \\( \mathcal{B^{\*}\subset B} \\) 有非0体积. $\mathcal{B^{*}}$由运动被规定的粒子组成. 令 $w(\cdot, \cdot)$ 是物体 $\mathcal{B}$的一个运动，简化记号
$$
w = w(x,t), w' = w(x', t).
$$
则虚功原理如下所述：
$$
\int_{\mathcal{B}}\rho\ddot{y}\cdot wdV + \int_{\mathcal{B}}\int_{\mathcal{B}}t\cdot (w'-w)dV'dV = \int_{\mathcal{B}}b\cdot wdV,on\mathcal{B\setminus B^*}\\
\dot{y}(\cdot,0) = V_0(\cdot),on\mathcal{B\setminus B^*}\tag{17}
$$
对所有的运动$w$满足下式都成立
$$
w = 0,on\mathcal{B^*}.\tag{18}
$$
由下式(变量代换并改变求积顺序)
$$
\int_{\mathcal{B}}\int_{\mathcal{B}}t\cdot (w'-w)dV'dV =- \int_{\mathcal{B}}\int_{\mathcal{B}}(t-t')\cdot wdV'dV.\tag{19}
$$
则容易看出其与如下线动量守恒的初边值问题等价
$$
\begin{cases}
\rho\ddot{y} = \int_{\mathcal{B}}(t-t')dV'+b,on\mathcal{B\setminus B^*},\\
y = y^*, on\mathcal{B^*},\\
\dot{y}(\cdot,0)=v_0(\cdot),on\mathcal{B\setminus B^*}
\end{cases}
\tag{20}
$$
#### 2.3 Balance of Angular Momentum

### 3.Peridynamic States: Notion and Properties
$\mathcal{H_x} = \{x'\in \mathcal{B}|dist(x,x')< \delta\}$, 称为点$x$的家族，$\mathcal{H}=\{\mathbf{\xi}\in\mathbb{R^3\setminus 0}(\xi + x)\in\mathcal{H_x\cap B}\}$表示连接$x$的所有键组成的集合。  
态是定义在$\mathcal{H}$上的函数，用$\underline{A}<\cdot>$表示，其中尖括号中是一个向量$\xi\in\mathcal{H}$, 圆括号和方括号在后面会用来表示对其他量的依赖. 简单来说，态就是一个把向量映射为标量、向量、张量的函数.  
$\underline{A}<\xi>$标量，$\underline{A}$就是标量态，所有标量态的集合记作$\mathcal{S}$. e.g.:  
- $\underline{0}<\xi> = 0,\forall\xi\in\mathcal{H}$，零态  
- $\underline{1}<\xi> = 1,\forall\xi\in\mathcal{H}$，单位态  
- $\underline{a}<\xi> = 3\mathbf{c\cdot\xi},\forall\xi\in\mathcal{H},c$常向量  

$\underline{A}<\xi>$向量，$\underline{A}$就是向量态，所有向量态的集合记作$\mathcal{V}$. e.g.:  
- $\underline{\mathbf{0}}<\xi> = 0,\forall\xi\in\mathcal{H}$，空向量态  
- $\underline{\mathbf{X}}<\xi> = 1,\forall\xi\in\mathcal{H}$，恒等态  
- $\underline{\mathbf{A}}<\xi> =\mathbf{c+\xi},\forall\xi\in\mathcal{H},c$常向量
  
双态$\underline{\mathbb{A}}<\xi,\zeta>,\xi,\zeta\in\mathcal{H}$,是$\mathcal{H\times H}\rightarrow$二阶张量的映射，所有双态的集合记为$\mathcal{D}$.  
下面是定义的一些关于态的基本运算：$\underline{a}$,$\underline{b}$是标量态，$\underline{\mathbf{A}}$,$\underline{\mathbf{B}}$是向量态，$\mathbf{V}$是一个向量, 则对任意$\xi\in\mathcal{H}$，有
$$
(\underline{a}+\underline{b})<\xi> = \underline{a}<\xi> + \underline{b}<\xi>,\\
(\underline{ab})<\xi> = \underline{a}<\xi>\underline{b}<\xi>,\\
(\underline{a\mathbf{B}})<\xi> = \underline{a}<\xi>\underline{\mathbf{B}}<\xi>,\\
(\underline{\mathbf{A}}+\underline{\mathbf{B}})<\xi> = \underline{\mathbf{A}}<\xi> + \underline{\mathbf{B}}<\xi>,\\
(\underline{\mathbf{A}}\cdot\underline{\mathbf{B}})<\xi> = \underline{\mathbf{A}}<\xi>\cdot\underline{\mathbf{B}}<\xi>,\\
(\underline{\mathbf{A}}\otimes\underline{\mathbf{B}})<\xi> = \underline{\mathbf{A}}<\xi>\otimes\underline{\mathbf{B}}<\xi>,\\
(\underline{\mathbf{A}}\circ\underline{\mathbf{B}})<\xi> = \underline{\mathbf{A}}<\xi>\circ\underline{\mathbf{B}}<\xi>,\\
(\underline{\mathbf{A}}\cdot\mathbf{V})<\xi> = \underline{\mathbf{A}}<\xi>\cdot\mathbf{V}.\\
$$
$\cdot$表示标量积，$\otimes$表示张量积。  
定义标量态$|\underline{\mathbf{A}}|$为
$$
|\underline{\mathbf{A}}|<\xi> = |\underline{\mathbf{A}}<\xi>|
\tag{50}
$$
点积
$$
\underline{a}\bullet\underline{b} = \int_{\mathcal{H}}\underline{a}<\xi>\underline{b}<\xi>dV_{\xi},\\
\underline{\mathbf{A}}\bullet\underline{\mathbf{B}} = \int_{\mathcal{H}}\underline{\mathbf{A}}<\xi>\underline{\mathbf{B}}<\xi>dV_{\xi},
\tag{51}
$$
范数
$$
||\underline{a}||=\sqrt{\underline{a}\bullet\underline{a}},\\
||\underline{\mathbf{A}}||=\sqrt{\underline{\mathbf{A}}\bullet\underline{\mathbf{A}}}
\tag{52}
$$
由于近场动力学的本构关系涉及到了态函数，对于态函数的泛函的变分导数的引入也是十分有必要的，下面就是直接将变分导数的定义拿过来。  
若$\psi(\cdot):\mathcal{S}\rightarrow\mathbb{R}$是标量态，则其*Frechet derivative* $\nabla\psi$ 如果存在，定义为
$$
\psi(\underline{A}+\underline{a})=\psi(\underline{A})+\nabla\psi(\underline{A})\bullet\underline{a}+o(||\underline{a}||)
\tag{53}
$$
其中$\underline{A},\underline{a},\nabla\psi$是标量态.  
若$\psi(\cdot):\mathcal{S}\rightarrow\mathbb{R}$是向量态，则其*Frechet derivative* $\nabla\psi$ 如果存在，定义为
$$
\Psi(\underline{\mathbf{A}}+\underline{\mathbf{a}})=\Psi(\underline{\mathbf{A}})+\nabla\Psi(\underline{\mathbf{A}})\bullet\underline{\mathbf{a}}+o(||\underline{\mathbf{a}}||)
\tag{54}
$$
其中$\underline{\mathbf{A}},\underline{\mathbf{a}},\nabla\Psi$是向量态.  
对于以多个态为自变量的函数，如$\Psi(\underline{\mathbf{A}},\underline{\mathbf{B}})$, $\Psi_{\underline{\mathbf{A}}},\Psi_{\underline{\mathbf{B}}}$分别表示关于变量$\underline{\mathbf{A}},\underline{\mathbf{B}}$的 *Frechlet* 导数。并且有复合函数求导的链式法则：
$$
\frac{\partial}{\partial\underline{\mathbf{A}}}f(\psi(\underline{\mathbf{A}})) = f'(\psi(\underline{\mathbf{A}}))\nabla\psi(\underline{\mathbf{A}})
$$
注意上面的定义并没有排除模型的非线性表现。  
态场就是位置和时间的态值函数，用方括号表示，就是给定时间，位置就对应一个态函数：
$$
\underline{\mathbf{A}}[x,t],x\in\mathcal{B},t\ge 0.
$$
例如：
$$
\underline{a}[x,t]<\xi> = |\xi+x|t,\forall\xi\in\mathcal{H},x\in\mathcal{B},t\ge0.
$$
一个态值函数对其他态值函数的依赖用圆括号表示，例如
$$
\underline{\mathbf{A}}(\underline{\mathbf{B}}).
$$
向量态的态值函数的例子：
$$
\underline{a}(\underline{\mathbf{B}}) = |\underline{\mathbf{B}}|^3,
$$
i.e.,  
$$
\underline{a}(\underline{\mathbf{B}}<\xi>) = |\underline{\mathbf{B}}<\xi>|^3,\forall\xi\in\mathcal{H},x\in\mathcal{B},t\ge0.
$$
一个向量态就类似于一个张量，因为它把向量映射为向量，向量态不一定是向量的线性变换，这是非线性和非局部性导致的。  
经典理论中，本构模型是一个张量是其他张量的函数。  
近场动力学中，本构模型是一个向量态是其它向量态的函数。
### 4.Constitutive Modeling

### 5.Linear Theory
#### 5.4 Equations of Motion and Equilibrium
由于

$$
(\underline{\mathbb{K}}[x]\bullet\underline{\mathbf{U}}[x,t])<\xi> = \int_{\mathcal{H}}\underline{\mathbb{K}}[x]<\xi,\zeta>\underline{\mathbf{U}}[x,t]<\zeta>dV_{\zeta}
$$

所以

$$
\begin{aligned}
(\underline{\mathbb{K}}[x]\bullet\underline{\mathbf{U}}[x,t])<p-x> 
&= \int_{\mathcal{H}}\underline{\mathbb{K}}[x]<p-x,\zeta>\underline{\mathbf{U}}[x,t]<\zeta>dV_{\zeta}\\
&= \int_{\mathcal{B}}\underline{\mathbb{K}}[x]<p-x,q-x>\underline{\mathbf{U}}[x,t]<q-x>dV_{q}\\
&= \int_{\mathcal{B}}\underline{\mathbb{K}}[x]<p-x,q-x>(u(q,t)-u(x,t))dV_q\\
\end{aligned}
$$

即

$$
\begin{aligned}
(\underline{\mathbb{K}}[p]\bullet\underline{\mathbf{U}}[p,t])<x-p> 
&= \int_{\mathcal{B}}\underline{\mathbb{K}}[p]<x-p,\zeta>\underline{\mathbf{U}}[x,t]<\zeta>dV_{\zeta}\\
&= \int_{\mathcal{B}}\underline{\mathbb{K}}[p]<x-p,q-p>\underline{\mathbf{U}}[x,t]<q-x>dV_{q}\\
&= \int_{\mathcal{B}}\underline{\mathbb{K}}[p]<x-p,q-p>(u(x,t)-u(q,t)+u(q,t)-u(p,t))dV_q\\
&= -\int_{\mathcal{B}}\underline{\mathbb{K}}[p]<x-p,q-p>(u(q,t)-u(x,t))dV_q\\
&- \int_{\mathcal{B}}\underline{\mathbb{K}}[p]<x-p,q-p>(u(p,t)-u(q,t))dV_q\\
&= -\int_{\mathcal{B}}\underline{\mathbb{K}}[p]<x-p,q-p>(u(q,t)-u(x,t))dV_q\\
&+ \int_{\mathcal{B}}\underline{\mathbb{K}}[x]<p-x,q-p>(u(q,t)-u(x,t))dV_q\\
\end{aligned}
$$
### 6.Relation to Other Theories

### 7.Discrete Particles as Peridynamic Bodies

### 8.Damage and Fracture

### 9.Discussion

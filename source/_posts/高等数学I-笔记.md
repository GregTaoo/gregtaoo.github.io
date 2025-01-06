---
title: 高等数学I 笔记
date: 2024-11-16 22:41:20
tags:
---

### 逻辑符号

差集：$A \setminus B = \{x \in A | x \notin B\}$；直积：$A \times B = \{(a,b) | a \in A, b \in B\}$

对任意给定的 (for any given) : $\forall$；存在 (exist) : $\exist$；存在唯一 : $\exists!$

否定：
$$
\exist country,\forall city\in country,\exist month,\forall day\in month,Always\ rains\\
\forall country,\exist city\in country,\forall month,\exist day\in month,Never\ rains
$$
对于命题: $P\Rightarrow Q$; 逆命题: $Q\Rightarrow P$, $\neg P\Rightarrow \neg Q$; 逆否命题: $(P\Rightarrow Q)\Leftrightarrow(\neg Q\Rightarrow \neg P)$

反证法：即通过逆否命题证明

### 归纳法

1. $n=1$ 时， $P_1$ 成立
2. 假设 $n=k$ 时 $P_k$ 成立（强归纳：$\forall m\leq k, P_m$ 成立）
3. 证明当 $n=k+1$ 时 $P_{k+1}$ 成立

### 不等式

若 $\delta\in\mathbf{R}_+,x,a\in\mathbf{R}$, 则: $|x-a|<\delta\Leftrightarrow a-\delta<x<a+\delta$

若 $x,y\in\mathbf{R}$, 则: $|x\pm y|\leq|x|+|y|$, $|x\pm y|\geq ||x|-|y||$

$A-G$ 不等式: $\frac{1}{n}(x_1+x_2+\ldots+x_n)\geq\sqrt[n]{x_1x_2\ldots x_n}$, 证明：数学归纳法、二项式展开

Bernoulli 不等式: $(1+x)^n\geq 1+nx$, 证明：直接展开或数学归纳法

### 上下确界

确界存在性定理：若非空数集 $E$ 有上/下界，则 $E$ 必有上/下确界（实数连续性）

在区间 $[a,b]$ 上定义的连续函数 $f(x)$ 有界，因此有确界。

### 函数 

映射：$f: A\rightarrow B$, 逆映射: $f^{-1}: B\rightarrow A$ (反函数)

单射 (injection): $\forall a,b\in A,a\neq b\Rightarrow f(a)\neq f(b)$

满射 (surjection): $\forall y\in B,\exist x\in A, f(x)=y$

双射 (bijection): 满足单射、满射

定义域 (domain)、值域 (range): $Dom(f)$ 或$D(f)$、$Range(f)$或$R(f)$; **注意：自然定义域**

复合映射：有映射$f:U\rightarrow Y$和$g:X\rightarrow V$, 当$R(g)\cap D(f)\ne\varnothing$时可定义复合映射 $f\circ g:X^*\rightarrow Y$
$$
(f\circ g)(x)=f[g(x)],x\in X^*=\{x|g(x)\in D(f),x\in X\}\subset X
$$

### 三角函数

正割余割：$\sec x=\frac{1}{\cos x}, \csc x=\frac{1}{\sin x}$

双曲函数
$$
\sinh x=\frac{e^x-e^{-x}}{2},\cosh x=\frac{e^x+e^{-x}}{2}\\
\cosh^2x-\sinh^2x=1
$$
和差化积
$$
\begin{aligned}
\sin\alpha+\sin\beta&=2\sin\frac{\alpha+\beta}{2}\cos\frac{\alpha-\beta}{2}\\
\sin\alpha-\sin\beta&=2\cos\frac{\alpha+\beta}{2}\sin\frac{\alpha-\beta}{2}\\
\cos\alpha+\cos\beta&=2\cos\frac{\alpha+\beta}{2}\cos\frac{\alpha-\beta}{2}\\
\cos\alpha-\cos\beta&=-2\sin\frac{\alpha+\beta}{2}\sin\frac{\alpha-\beta}{2}
\end{aligned}
$$

常用变换: $\tan x=\frac{1}{\cos^2x}-1,\cot x=\frac{1}{\sin^2x}-1$

### 数列极限

对数列 $\{x_n\}$, 若存在数 $A$, $\forall \epsilon>0,\exist N\in\mathbf{N}, \forall n>N$, 有 $|x_n-A|<\epsilon$, 则数列 $\{x_n\}$ 收敛于$A$ 

若$A$不存在，则称数列$\{x_n\}$发散/不收敛

保号性：在极限$A\ne 0$条件下，数列在某一项后均有$|x_n|>\frac{|A|}{2}$

**多项式公式**: $a^m-b^m=(a-b)(a^{m-1}+a^{m-2}b+\cdots+b^{m-1})$

**多项式公式2**: $1-a^m=(1-a)(1+a+a^2+\cdots+a^{m-1})$

习题课例题：求极限 $\lim_{x\to\infty}(1+x)(1+x^2)\cdots(1+x^{2^{n-1}})$，其中 $|x|\leq1$

分别讨论 $x=1,x=-1,|x|<1$ 情况，对于 $|x|<1$，分子分母同乘 $1-x$ 即可

某思路：可构造有理数列逼近无理数

### 夹逼定理

课本例2.15，求 $\lim_{n\to \infty}\frac{c^n}{n!},c>0$

当 $n>[c]+1$ 时，有 
$$
0\leq\frac{c^n}{n!}=\frac{c}{1}\cdot\frac{c}{2}\cdot\dots\cdot\frac{c}{[c]+1}\cdot\frac{c}{[c]+2}\cdot\dots\cdot\frac{c}{n}\leq\frac{c}{1}\cdot\frac{c}{2}\cdot\dots\cdot\frac{c}{[c]+1}\cdot\frac{c}{n}\leq c^{[c]+1}\frac{1}{n}
$$
夹逼可得极限为0

课本例2.16，证明 $\lim_{n\to\infty}\sqrt[n]{n}=1$（思路：构造 $x_n$，控制 $n$ 的范围以导出 $x_n$ 范围，夹逼）

设 $x_n=\sqrt[n]{n}-1$，当 $n\ge2$ 时，有 $n=(1+x_n)^n=1+C^1_nx_n+C^2_nx^2_n+\cdots+x^n_n>\frac{n(n-1)}{2}x^2_n$ （此处放缩只取第三项）；从而 $0\le x_n<\sqrt{\frac{2}{n-1}}$，夹逼定理易证 $\lim_{n\to\infty}x_n=\lim_{n\to\infty}\sqrt[n]{n}-1=0$，得证

### 递归数列

课本例2.21，$x_n=\sqrt{2+\sqrt{2+\cdots+\sqrt{2+\sqrt{2}}}}$  (n重根号), 求$\{x_n\}$极限

首先证明极限存在：**单调有界（注：可考虑归纳，可先在草稿纸求出极限再证明极限存在）**

设极限为$A$, 则因为$x_{n+1}=\sqrt{2+x_n}$, 得到 $A=\sqrt{2+A}$, 得$A=2$

### 区间套定理

若 $[a_{n+1},b_{n+1}]\subset[a_n,b_n],\forall n\in\mathbf{N}_+$，且有 $\lim_{n\to\infty}(b_n-a_n)=0$, 则存在唯一实数 $\xi,\forall n\in\mathbf{N}_+$, 有 $a_n\leq\xi\leq b_n$，换言之 
$$
\xi=\bigcap_{n=1}^{\infty}[a_n,b_n]
$$

### 函数极限

$f(x)$ 在 $\mathring{U}(a)$ 内有定义，若存在 $A\in\mathbb{R},\forall\epsilon>0,\exist\delta>0$，使得当 $0<|x-a|<\delta$ 时，$|f(x)-A|<\epsilon$，则$\lim_{x\to a}f(x)=A$

$f(x)$ 在 $(-\infty,-a)\cup(a,+\infty)(a>0)$ 内有定义，若存在 $A\in\mathbb{R},\forall\epsilon>0,\exist X>0(X>a)$，使得当 $|x|>X$ 时，$|f(x)-A|<\epsilon$，则 $\lim_{x\to\infty}f(x)=A$

TIP：欲证明 $\lim_{x\to x_0}f(x)=L$，通过 $f(x)-L$ 构造 $x-x_0$，以 $\epsilon$ 表示 $\delta$；先限定 $\delta<1$，再得到 $|x-A|<\delta<1$，得到 $x$ 范围，再进行放缩。最后注意例如：$\delta=\min\{3\epsilon,1\}$

例题 quiz1第一题：证明 $\lim_{x\to 2}x^2=4$

考虑 $|x-2|<\delta<1$，得出 $1<x<3$，构造 $x-2$，考虑因式分解
$$
|x^2-4|=|(x-2)(x+2)|<|5(x-2)|<\epsilon\\
\delta=\min\{\frac{\epsilon}{5},1\},0<|x-2|<\delta
$$
课本例2.26：证明 $\lim_{x\to 1}\ln x=0$

$|\ln x-0|<\epsilon$，想构造出 $|x-1|$ 形式。有 $e^{-\epsilon}-1<x-1<e^\epsilon-1$，易知 $e^{-\epsilon}-1<0$，则 $|x-1|<1-e^{-\epsilon}$，令 $\delta=1-e^{-\epsilon}$，则当 $0<|x-1|<\delta$ 时，满足 $-\delta<x-1<\delta<e^\epsilon-1$，得证

### Heine 海涅定理

$\lim_{x\to a}f(x)=A$ 充要条件：任一满足 $\lim_{n\to \infty}x_n=a, x_n\ne a$ 的数列均有 $\lim_{n\to \infty}f(x_n)=A$

一般用于证明极限不存在：可构造2个数列，极限为$a$，证明这两个数列对应的函数$f(x_n)$极限不相等

### 复合函数极限运算

$\lim_{u\to b}f(u)=A, \lim_{x\to a}\varphi(x)=b$，且当 $x\in \mathring{U}(a)$ 时，$\varphi(x)\ne b$，则 $\lim_{x\to a}f[\varphi(x)]=A$

### 无穷小/大量

某函数在a处极限为0，则称该函数在趋向于0时为无穷小量：$f(x)=o(1)$

若 $\forall G>0,\exist\delta>0$ 当 $0<|x-a|<\delta$ 时，有 $|f(x)|>G$，则称无穷大量（极限为无穷）

设 $\lim_{x\to a}\alpha(x)=0,\lim_{x\to a}\beta(x)=0,lim_{x\to a}\frac{\beta(x)}{\alpha(x)}=l\in\mathbf{R}$

$l=0$ 则 $x\rightarrow a$ 时 $\beta(x)$ 是比 $\alpha(x)$ 高阶无穷小，记为 $\beta(x)=o(\alpha(x))(x\rightarrow a)$

$l\ne0$ 则 $x\rightarrow a$ 时 $\beta(x)$ 是与 $\alpha(x)$ 同阶无穷小，记为 $\beta(x)=O(\alpha(x))(x\rightarrow a)$

$l=1$ 则 $x\rightarrow a$ 时 $\beta(x)$ 是与 $\alpha(x)$ 等价无穷小，记为 $\beta(x)\sim\alpha(x)(x\rightarrow a)$

$\exist c\ne 0,k>0, \lim_{x\to a}\frac{\alpha(x)}{(x-a)^k}=c$，则称 $\alpha(x)$ 是**标准无穷小** $x-a$ 的 $k$ 阶无穷小，且 $c(x-a)^k$ 为**主部**

可表示为 $\alpha(x)=c(x-a)^k+o((x-a)^k)$，一般判断直接选取次数最小/大的整个项即可

### 常见等价无穷小

$$
\begin{array}{lll}
\sin x\sim x& \tan x\sim x& \cos x\sim1-\frac{1}{2}x^2\\
\ln(1+x)\sim x& e^x\sim1+x& (1+x)^\alpha\sim1+\alpha x\\
\arcsin x\sim x& \arctan x\sim x& \ln(1+x)\sim x-\frac{1}{2}x^2\\
\sin x\sim x+\frac{1}{6}x^3& \arcsin x\sim x+\frac{1}{6}x^3& \tan x\sim x+\frac{1}{3}x^3\\
\arctan x\sim x-\frac{1}{3}x^3& a^x\sim1+x\ln a& \log_a(1+x)\sim\frac{x}{lna}
\end{array}
$$

### 函数连续性

函数$f$在点$x_0$的某邻域内有定义，若$\lim_{x\to x_0}f(x)=f(x_0)$，则称$f(x)$在$x_0$处连续，否则间断（$x_0$为间断点）

第一类

1. 可去/可移间断点：$f(x_0-0),f(x_0+0)$存在且相等，且$f(x)$在$x=x_0$处无定义或$\lim_{x\to x_0}f(x)\ne f(x_0)$
2. 跳跃间断点：$f(x_0-0),f(x_0+0)$存在但不相等

第二类

1. 无穷间断点：左极限或右极限为$\infty$
2. 振荡间断点：例如 $\sin\frac{1}{x}$

### 闭区间上连续函数性质

有界性定理：若 $f\in C[a,b]$，则 $f$ 在 $[a,b]$ 上有界（证明：区间套二分法反证）

最大值最小值定理：

- 由确界存在定理得有上下确界，设上确界为 $M$，反证法设 $f(x)$ 在 $[a,b]$ 都取不到 $M$
- 若构造 $\epsilon>0$ 使得 $f(x)\leq M-\epsilon$，即 $0<\epsilon\leq M-f(x)$（如果 $M-f(x)$ 可取到0，则 $\epsilon$ 不存在），则可证明与上确界矛盾。因此若 $f(x)$ 在 $[a,b]$ 都取不到 $M$, 则 $g(x)=\frac{1}{M-f(x)}$ 在 $[a,b]$ 连续，由于 $f$ 有界，则 $g$ 也有界，$\exist C>0, g(x)\leq C$，可取 $\epsilon=\frac{1}{C}$，与 $M$ 是上确界矛盾。因此 $\epsilon,g(x)$ 不存在。得证。

介值定理（零点存在定理）：

- 若 $f(x)\in C[a,b]$，且 $f(a)\ne f(b)$，则 $\forall c\in[f(a),f(b)], \exist\xi\in[a,b], f(\xi)=c$

- 构造函数 $F(x)=f(x)-c$，由零点存在定理可证

### 极限计算

课本P95 25.(10)：夹逼
$$
\lim_{x\to +\infty}\frac{x\cdot x^2\cdot\cdots\cdot x^n}{[(nx)^n+1]^{\frac{n+1}{2}}}\leq\lim_{x\to +\infty}\frac{(x+1)(x^2+1)\cdots(x^n+1)}{[(nx)^n+1]^{\frac{n+1}{2}}}\leq\lim_{x\to +\infty}\frac{(x+1)(x^2+1)\cdots(x^n+1)}{(nx)^{\frac{n(n+1)}{2}}}
$$

习题课上例题：**三角函数周期性**、有理化、等价无穷小
$$
\begin{aligned}
\lim_{n\to\infty}[nsin(2\pi\sqrt{n^2+1})]&=\lim_{n\to\infty}[nsin(2\pi\sqrt{n^2+1}-2n\pi)]\\
&=\lim_{n\to\infty}[nsin(2\pi\frac{1}{\sqrt{n^2+1}+n})]\\
&=\lim_{n\to\infty}\frac{2\pi}{\sqrt{1+\frac{1}{n^2}}+1}\\
&=\pi
\end{aligned}
$$


### 导数

若极限 $\lim_{\Delta x\to 0}\frac{f(x_0+\Delta x)-f(x_0)}{\Delta x}$ 存在，则称该极限为函数在 $x_0$ 处的导数/微商

可导必定连续，连续未必可导，如 $f(x)=|x|$

### 微分

设函数 $y=f(x)$ 在 $x_0$ 的邻域内有定义，$\Delta y=f(x_0+\Delta x)-f(x_0)=A\cdot\Delta x+o(\Delta x)$，则称可微，其中 $A\Delta x$ 为在 $x_0$ 处的微分

一元函数中，可导可微等价

### 基本微分公式

$$
\begin{array}{ll}
d(\tan x)=\sec^2xdx& d(\cot x)=-\csc^2xdx\\
d(\sec x)=\sec x\tan xdx& d(\csc x)=-\csc x\cot xdx\\
d(\arcsin x)=\frac{1}{\sqrt{1-x^2}}dx& d(\arccos x)=-\frac{1}{\sqrt{1-x^2}}dx\\
d(\arctan x)=\frac{1}{1+x^2}dx& d(\mathrm{arccot}\ x)=-\frac{1}{1+x^2}dx\\
d(\sinh x)=\cosh xdx& d(\cosh x)=\sinh xdx
\end{array}
$$

### 高阶导数莱布尼兹公式

$$
[u(x)v(x)]^{(n)}=\sum^{n}_{k=0}C^k_mu^{(k)}v^{(m-k)}
$$

证明：数学归纳法

### 隐函数求导

若存在隐函数 $F(x,y)=0$ 确定了隐函数 $y=y(x)$，将此式代入得 $F(x,y(x))=0$，在等式两边对 $x$ 求导

### 参数方程求导

$$
\left\{
\begin{array}{ll}
x=\varphi(t),\\
y=\psi(t)
\end{array}
\right.\quad(t\in I)\\
\frac{dy}{dx}=\frac{dy}{dt}\cdot\frac{dt}{dx}=\frac{\psi'(t)}{\varphi'(t)}
$$

### 反函数求导

例题：求 ${\rm arccosh}\ x$ 导数
$$
\frac{d({\rm arccosh}\ x)}{dx}=\frac{1}{\frac{dx}{d({\rm arccosh}\ x)}}=\frac{1}{\frac{d(\cosh({\rm arccosh}\ x))}{d({\rm arccosh}\ x)}}=\frac{1}{\sinh({\rm arccosh}\ x)}=\frac{1}{\sqrt{1-[\cosh({\rm arccosh}\ x)]^2}}=\frac{1}{\sqrt{1-x^2}}\\
y={\rm arccosh}\ x,x=\cosh y,\frac{dy}{dx}=\frac{1}{\frac{dx}{dy}}=\frac{1}{\sinh y}=\frac{1}{\sqrt{1-x^2}}
$$

### 反函数二阶导

$$
\begin{aligned}
\frac{d^2x}{dy^2}=\frac{d(\frac{dx}{dy})}{dy}&=\frac{d(\frac{dx}{dy})}{dx}\cdot\frac{dx}{dy}=\left(\frac{1}{f'(x)}\right)'\left(\frac{1}{f'(x)}\right)\\
&=-\frac{f''(x)}{[f'(x)]^3}=-\frac{\frac{d^2y}{dx^2}}{(\frac{dy}{dx})^3}
\end{aligned}
$$

### Fermat 费马定理

设 $f(x)$ 在 $x_0$ 处取得极值，且在此处可导，则 $f'(x_0)=0$，推论：取得最大最小值时也满足

### Rolle 罗尔定理

$f(x)\in C[a,b]\cap D(a,b),f(a)=f(b)$，则 $\exist\xi\in(a,b),f'(\xi)=0$

推论：若在 $(a,b)$ 内 $f'(x)\ne0$，则在闭区间 $[a,b]$ 上为单射函数，从而有反函数

广义罗尔定理1：若 $f(x)\in D(a,b),\lim_{x\to a^+}f(x)=\lim_{x\to b^-}f(x),\exist\xi\in(a,b),f'(\xi)=0$

证明：补充定义 $x=a$ 和 $x=b$，则 $f(x)\in C[a,b]\cap D(a,b)$，再用罗尔定理可证

广义罗尔定理2：若 $\lim_{x\to a^+}f(x)=\lim_{x\to b^-}f(x)=+\infty(-\infty)$

证明：先证 $+\infty$，取 $x_0\in(a,b),M>f(x_0)$，根据介值定理，$\exist\xi_1\in(a,x_0),f(\xi_1)=M,\exist\xi_2\in(x_0,b),f(\xi_2)=M$，再根据罗尔定理可证

广义罗尔定理3：若 $f(x)\in(a,+\infty),\lim_{x\to a^+}f(x)=\lim_{x\to+\infty}f(x)=A,\exist\xi\in(a,+\infty),f'(\xi)=0$

证明1（待完善）：存在 $x_0$，分别讨论 $f(x)=A,f(x_0)>A,f(x_0)<A$，考虑 $f(x_0)>A$ 根据极限保号性，有 $0<\delta<\frac{x_0-a}{2},M>x_0$（$a+\delta<x_0<M$，但是似乎 $\delta$ 取值范围可以是除以大于1的数）$f(x)<\frac{f(x_0)+A}{2}<f(x_0)$（局部保号，为了证明该式，取 $\epsilon=\frac{f(x_0)-A}{2}>0$，由 $|f(x)-A|<\epsilon$ 推得）$x\in(a,a+\delta]\cup[M,+\infty)$，则 $f(x_0)>f(a+\delta),f(x_0)>f(M)$，故最大值在 $(a+\delta,M)$ 取得，根据费马定理可取得

证明2：构造辅助函数，具体证明省略
$$
\left\{
\begin{array}{l}
g(x)=f(\tan x),&x\in(0,\frac{\pi}{2})\\
g(x)=A,&x=0,\frac{\pi}{2}
\end{array}
\right.
$$

### Lagrange 拉格朗日定理

$f(x)\in C[a,b]\cap D(a,b)$，则 $\exist\xi\in(a,b),f'(\xi)=\frac{f(b)-f(a)}{b-a}$

或表示为拉格朗日中值公式：$f(b)-f(a)=f'(\xi)(b-a)$

或有限增量公式：$f(x_0+\Delta x)-f(x_0)=f'(x_0+\theta\Delta x)\Delta x,\quad\theta\in(0,1)$

推论1：若 $f'(x)\equiv0$，则 $f(x)$ 在 $I$ 上等于一个常数

推论2：两个函数在区间上导数处处相等，则两个函数在区间相差一个常数

证明：构造函数 $F(x)=f(x)-\frac{f(b)-f(a)}{b-a}(x-a)$ 、从罗尔定理证明之

### Cauchy 柯西定理

$f(x)\in C[a,b]\cap D(a,b),\forall x\in(a,b),g'(x)\ne0,\exist\xi\in(a,b)$，使得
$$
\frac{f(b)-f(a)}{g(b)-g(a)}=\frac{f'(\xi)}{g'(\xi)}
$$
几何意义：把 $x$ 换成 $t$ 则可认为是函数曲线的参数方程。例如一个人走过的路程中必有某些点的切线与首末端点连线平行

证明：类似拉格朗日证明构造 $F(x)=f(x)-\frac{f(b)-f(a)}{g(b)-g(a)}[g(x)-g(a)]$，通过罗尔定理可证

### 达布定理

当函数 $f(x)$ 是某函数在闭区间 $[a,b]$ 上的导函数时，即使不连续也仍具有介值性

证明：先证零点存在，由于原函数可导故连续，可取得最小值 $m$，因 $f'(a)<0$，由保号性，$\exist\delta>0,x\in(a,a+\delta),\frac{f(x)-f(a)}{x-a}<0$，因此 $f(a)>m$，由费马定理推论得 $f'(\xi)=0$；然后构造函数证明之。

注意：因导函数的特殊性意味着不是任何一个函数都能是某个函数的导函数

### Stolz 定理（疑似不可用，但补充）

有数列 $\{a_n\},\{b_n\}$，其中 $\{b_n\}$ 严格单调发散（${b_n}$ 严格单调递减且趋于 $0$，$\lim_{n\to\infty}a_n=0$），$\lim_{n\to\infty}\frac{a_{n+1}-a_n}{b_{n+1}-b_n}=L$，则 $\lim_{n\to\infty}\frac{a_n}{b_n}=L\quad(+\infty/-\infty)$

证明：极限定义、迭代

### 洛必达

$\frac{0}{0}$ 型证明：运用柯西定理，任取 $x\in(x_0,x_0+\delta)$，故有 $\xi\in(x_0,x)$，可认为 $\xi$ 为关于 $x$ 的函数
$$
\frac{f(x)}{g(x)}=\frac{f(x)-f(x_0)}{g(x)-g(x_0)}=\frac{f'(\xi)}{g'(\xi)}\\
\lim_{x\to x_0^+}\frac{f(x)}{g(x)}=\lim_{x\to x_0^+}\frac{f'(\xi)}{g'(\xi)}=\lim_{\xi\to x_0^+}\frac{f'(\xi)}{g'(\xi)}=A
$$
类似可得 $x\to x_0^-$ 情况，因此得证

$\frac{\infty}{\infty}$ 型证明：根据柯西定理
$$
\forall\epsilon>0,\exist\delta>0,\forall x\in(a,a+\delta),L-\frac{\epsilon}{2}<\frac{f'(x)}{g'(x)}<L+\frac{\epsilon}{2}\\
\exist\xi\in(x,a+\delta),\frac{f'(\xi)}{g'(\xi)}=\frac{f(a+\delta)-f(x)}{g(a+\delta)-g(x)}=\frac{\frac{f(a+\delta)}{g(x)}-\frac{f(x)}{g(x)}}{\frac{g(a+\delta)}{g(x)}-1}\\
\frac{f(x)}{g(x)}=\frac{f'(\xi)}{g'(\xi)}\left(1-\frac{g(a+\delta)}{g(x)}\right)+\frac{f(a+\delta)}{g(x)}=\frac{f'(\xi)}{g'(\xi)}+r(x)\\
L-\epsilon<\frac{f(x)}{g(x)}<L+\epsilon
$$
两者证明最后记得用定义进行叙述

洛必达适用条件：必须在 $x_0$ 的邻域内连续可导

例题：quiz2，$f(x)$ 在 $x=1$ 处可导，且 $f'(1)=1$，求 $\lim_{x\to1}\frac{f(x)-f(1)}{x^{2023}-1}$（不可直接洛必达）

### 泰勒公式

设多项式 $P_n(x)=a_0+a_1(x-x_0)+\cdots+a_{n-1}(x-x_0)^{n-1}+a_n(x-x_0)^n$，有 $P_n^{(k)}(x_0)=k!a_k,a_k=\frac{f^{(k)}{x_0}}{k!}$，从而有 $P_n(x)=\sum^n_{k=0}\frac{f^{(k)}(x_0)}{k!}(x-x_0)^k$，称为在点 $x_0$ 处的泰勒多项式，其系数为泰勒系数

带Peano 佩亚诺余项的泰勒公式：
$$
f(x)=f(x_0)+\frac{f'(x_0)}{1!}(x-x_0)+\cdots+\frac{f^{(n)}(x_0)}{n!}(x-x_0)^n+o((x-x_0)^n)
$$
证明：取多项式前 $n$ 项，将函数与该多项式相减得 $R_n(x)$，则定理结论等价于 $\lim_{x\to x_0}\frac{R_n(x)}{(x-x_0)^n}=0$，应用 $n-1$ 次洛必达（因为 $R_n^{(n)}$ 不一定连续）可证

带拉格朗日余项的泰勒公式：

$f(x)$ 在包含点 $x_0$ 的开区间 $(a,b)$ 内有 $n+1$ 阶导数，$\forall x\in(a,b)$，有：
$$
f(x)=f(x_0)+\frac{f'(x_0)}{1!}(x-x_0)+\cdots+\frac{f^{(n)}(x_0)}{n!}(x-x_0)^n+\frac{f^{(n+1)}(\xi)}{(n+1)!}(x-x_0)^{n+1}
$$
其中 $\xi$ 介于 $x_0$ 和 $x$ 之间

证明：对 $\frac{R_n(x)}{(x-x_0)^n}$ 持续应用柯西定理可得

### 简单函数的麦克劳林公式

1. $f(x)=e^x$
   $$
   e^x=1+\frac{x}{1!}+\frac{x^2}{2!}+\cdots+\frac{x^n}{n!}+\frac{e^{\theta x}}{(n+1)!}x^{n+1},\theta\in(0,1)
   $$

2. $f(x)=\sin x$
   $$
   \sin x=x-\frac{x^3}{3!}+\frac{x^5}{5!}-\cdots+(-1)^{n-1}\frac{x^{2n-1}}{(2n-1)!}+(-1)^n\frac{\cos\theta x}{(2n+1)!}x^{2n+1},\theta\in(0,1)
   $$

3. $f(x)=\cos x$
   $$
   \cos x=1-\frac{x^2}{2!}+\frac{x^4}{4!}-\cdots+(-1)^n\frac{x^{2n}}{(2n)!}+(-1)^{n+1}\frac{\cos\theta x}{(2n+2)!}x^{2n+2},\theta\in(0,1)
   $$

4. $f(x)=\ln(1+x)$
   $$
   \ln(1+x)=x-\frac{1}{2}x^2+\frac{1}{3}x^3-\cdots+(-1)^{n-1}\frac{1}{n}x^n+(-1)^n\frac{1}{(n+1)(1+\theta x)^{n+1}}x^{n+1}
   $$

5. $f(x)=(1+x)^\alpha$
   $$
   (1+x)^\alpha=1+\alpha x+\frac{\alpha(\alpha-1)}{2!}x^2+\cdots+\frac{\alpha(\alpha-1)\cdots(\alpha-n+1)}{n!}x^n+\frac{\alpha(\alpha-1)\cdots(\alpha-n)}{(n+1)!}(1+\theta x)^{\alpha-n-1}x^{n+1},\theta\in(0,1)
   $$

6. $f(x)=\frac{1}{1+x}$
   $$
   \frac{1}{1+x}=1-x+x^2+\cdots+(-1)^nx^n+\frac{(-1)^{n+1}}{(1+\theta x)^{n+2}}x^{n+1},\theta\in(0,1)
   $$

### 函数凸性

$f(x)$ 在区间 $I$ 连续，若 $\forall x1,x2\in I,\forall\alpha\in(0,1)$，都有 $f[\alpha x_1+(1-\alpha)x_2]\le \alpha f(x_1)+(1-\alpha)f(x_2)$ 则为下凸（$<$ 为严格下凸）

第一判别法：$f(x)\in D(a,b)$，且 $f'(x)$ 在 $(a,b)$ 内严格单调增加（减少），则函数 $f(x)$ 严格下凸（上凸）

第二判别法：即通过二阶导判断 $f'(x)$ 单调性

### 函数拐点

上凸下凸的分界点，$x_0$ 称为函数 $f(x)$ 拐点，$(x_0,f(x_0))$ 称为曲线 $y=f(x)$ 拐点；函数的拐点在二阶导数为 $0$ 或不存在的点之中

### 渐近线

1. 铅直渐近线：$\lim_{x\to x_0}f(x)=\infty$，则渐近线为 $x=x_0$

2. 水平渐近线：$\lim_{x\to x_0}f(x)=b$，则渐近线为 $y=b$

3. 斜渐近线：$\lim_{x\to\infty}(f(x)-ax-b)=0$，则渐近线为 $y=ax+b$

   曲线 $y=f(x)$ 有渐近线 $y=ax+b\quad\Leftrightarrow\quad a=\lim_{x\to\infty}\frac{f(x)}{x},b=\lim_{x\to\infty}[f(x)-ax]$

### 不定积分

1. 若函数 $f(x)$ 在区间 $I$ 上存在原函数，则 $(\int f(x)dx)'=f(x)\quad\Leftrightarrow\quad d(\int f(x)dx)=f(x)dx$

2. 若函数 $f(x)$ 在区间 $I$ 上可导，则 $\int f'(x)dx=f(x)+C\quad\Leftrightarrow\quad\int df(x)=f(x)+C$

3. 函数的导函数不一定可积；导函数的原函数无第一类间断点（跳跃/可去）

4. 有理函数 $R(x)=\frac{P_n(x)}{Q_m(x)}$ 不定积分（$n\ge m$ 时为假分式，可化为一个多项式和一个真分式之和）

   先把分母因式分解，用待定系数法求解每一个基本项

   例书本 5.43：$\int\frac{x^5-x^3-2x^2+27x}{x^4-x^2-2x+2}dx$ 
   $$
   \frac{x^5-x^3-2x^2+27x}{x^4-x^2-2x+2}=x+\frac{25x}{(x-1)^2(x^2+2x+2)}=\frac{A_1}{x-1}+\frac{A_2}{(x-1)^2}+\frac{Bx+D}{x^2+2x+2}
   $$
   再解线性方程组求得系数，最后积分即可

### 基本积分表

$$
\begin{aligned}
    &\int\frac{dx}{x}=\ln|x|+C\\
    &\int\sec^2xdx=\tan x+C\\
    &\int\csc^2xdx=-\cot x+C\\
    &\int\sec xdx=\ln|\sec x+\tan x|+C\\
    &\int\csc xdx=\ln|\sec x-\cot x|+C\\
\end{aligned}
\quad\quad
\begin{aligned}
    &\int\frac{dx}{x^2+a^2}=\frac{1}{a}\arctan\frac{x}{a}+C\quad(a\ne0)\\
    &\int\frac{dx}{x^2-a^2}=\frac{1}{2a}\ln\left|\frac{x-a}{x+a}\right|+C\quad(a\ne0)\\
    &\int\frac{dx}{\sqrt{a^2-x^2}}=\arcsin\frac{x}{a}+C\quad(a>0)\\
    &\int\frac{dx}{\sqrt{x^2+a^2}}=\ln(x+\sqrt{x^2+a^2})+C\quad(a>0)\\
    &\int\frac{dx}{\sqrt{x^2-a^2}}=\ln|x+\sqrt{x^2-a^2}|+C\quad(a>0)\\
\end{aligned}
$$

### 不定积分技巧

1. 遇到根号时考虑三角换元，或用 $t$ 换掉根式
2. 建立递推公式通常用分部积分
3. 凑出分子是分母导数的项
4. $\sin mx\cos nx$ 诸如此类考虑积化和差，含三角函数平方的考虑 $\tan x$，$\tan^2 x+1=\frac{1}{\cos^2 x}$，$\frac{1}{\tan^2 x}+1=\frac{1}{\sin^2 x}$
5. 三角函数万能代换：$t=\tan\frac{x}{2}$

### 定积分

保号性、保序性、乘积函数可积

**注意判断积分区间内是否含有奇点（无界）**

绝对值不等式：
$$
\left|\int^b_af(x)dx\right|\le\int^b_a|f(x)|dx
$$
估值不等式：$f(x)$ 可积，且 $m\le f(x)\le M$
$$
m(b-a)\le\int^b_af(x)dx\le M(b-a)
$$
Schwarz 施瓦茨不等式：
$$
\left(\int^b_af(x)g(x)dx\right)^2\le\int^b_af^2(x)dx\cdot\int^b_ag^2(x)dx
$$
积分中值定理：函数 $f$ 连续，$g$ 黎曼可积，$g(x)$ 在 $[a,b]$ 不变号，则 $\exist\xi\in[a,b]$，使得
$$
\int^b_af(x)g(x)dx=f(\xi)\int^b_ag(x)dx
$$

沃利斯公式：
$$
\int^{\frac{\pi}{2}}_0\sin^n xdx=\int^{\frac{\pi}{2}}_0\cos^n xdx=\left\{
\begin{array}{l}
\frac{(n-1)!!}{n!!}\cdot\frac{\pi}{2},&n为偶数\\
\frac{(n-1)!!}{n!!},&n为奇数
\end{array}
\right.
$$
三角函数规则：$0$ 到 $\frac{\pi}{2}$ 积分时 $\sin x$ 可与 $\cos x$ 互换；多考虑**周期性**，如换元 $x=\pi-t$ 等

### 变上限积分函数

$\Phi(x)=\int^x_af(t)dt$，$\Phi$ 连续且可导，且 $\Phi'(x)=f(x)$

求变限积分导数时，积分内部 $x$ 看作常数

### 定积分应用

极坐标下求面积：$S=\frac{1}{2}\int^\beta_\alpha r^2(\theta)d\theta$

求体积：薄片法，薄壳法（$\Delta V\approx[\pi(x+dx)^2-\pi x^2]f(x)=\pi f(x)[2xdx+(dx)^2]$，故微元 $dV=2\pi xf(x)dx$

求弧长：$ds=\sqrt{(dx)^2+(dy)^2}$, $s=\int^b_a\sqrt{1+y'^2(x)}dx=\int^b_a\sqrt{x'^2(t)+y'^2(t)}dt=\int^b_a\sqrt{r^2(\theta)+r'^2(\theta)}d\theta$

### 数项级数

若级数收敛到 $S$，则其相邻若干项加括号所得新级数仍收敛到 $S$（逆命题不成立，但可用逆否命题，若加括号后发散则原级数发散）

级数收敛必要条件：$\lim_{n\to\infty}a_n=0$，常用若某级数一般项不趋于 $0$，则必发散

课本例11.3. **调和级数** $\sum_{n=1}^\infty\frac{1}{n}$ 的敛散性（发散）

若该级数收敛，则其部分和数列收敛，其子列 ${S_{2^n}}$ 也收敛，而 $S_{2^n}>1+\frac{1}{2}+{\frac{1}{4}+\frac{1}{4}}+\cdots=1+\frac{n}{2}\rightarrow+\infty$，故发散

重要公式：$\sum^n_{i=1}i^2=\frac{n(n+1)(2n+1)}{6}$，$\frac{1}{1-x}=\sum^\infty_{i=0}x^i$

### 正项级数

1. 正项级数收敛充要条件是其部分和数列有上界。例：讨论 $p$ 级数的敛散性（$p>1$ 收敛，$p\le1$ 发散，用积分）
2. 比较判别法：若 $\exist N\in \mathbf{Z}^+,\forall n>N,a_n\le b_n$，则当 $b_n$ 级数收敛时 $a_n$ 级数也收敛，当 $a_n$ 级数发散时 $b_n$ 级数发散
3. 比较判别法极限形式：$\lim_{n\to\infty}\frac{a_n}{b_n}=l$，当 $0<l<+\infty$ 时敛散性相同
4. $p$-判别法：即比较某正项级数与 $p$ 级数
5. 比值判别法：$\lim_{n\to\infty}\frac{a_{n+1}}{a_n}=l$，当 $0\le l<1$ 时级数收敛，当 $1<l\le+\infty$ 时级数发散，$l=1$ 需要另外判断
6. 根值判别法：$\lim_{n\to\infty}\sqrt[n]{a_n}=l$，当 $0\le l<1$ 时级数收敛，当 $1<l\le+\infty$ 时级数发散，$l=1$ 需要另外判断
7. 积分判别法：若非负函数 $f(x)$ 在 $[1,+\infty]$ 单调减少且有 $a_n=f(n)$，则级数与反常积分 $\int^{+\infty}_1f(x)dx$ 同敛散

### 任意项级数

交错级数 Leibniz 判别法：若交错级数 $\sum^\infty_{n=1}(-1)^{n-1}a_n$ 满足 $0<a_{n+1}\le a_n$ 且 $\lim_{n\to\infty}a_n=0$，则收敛

任意项级数 $\sum^\infty_{n=1}a_n$，若 $\sum^\infty_{n=1}|a_n|$ 收敛则称为绝对收敛，则 $\sum^\infty_{n=1}a_n$ 必收敛

任意项级数 $\sum^\infty_{n=1}a_n$，若 $\sum^\infty_{n=1}|a_n|$ 发散而 $\sum^\infty_{n=1}a_n$ 收敛，则成为条件收敛

若任意项级数绝对收敛，则交换其各项的次序所得的新级数仍绝对收敛，且其和不变

### 幂级数

Abel 定理：对于幂级数 $\sum^\infty_{n=0}a_nx^n$，有以下结论：

1. 若 $x=x_0\ne0$ 为收敛点，则 $|x|<|x_0|$ 时绝对收敛
2. 若 $x=x_1$ 为发散点，则 $|x|>|x_1|$ 时发散

推论：幂级数收敛域仅有三种可能情形（仅在 $x=0$ 收敛；在 $(-R,R)$ 收敛， $|x|>R$ 时发散；在 $(-\infty,+\infty)$ 收敛

系数模比值法：对于幂级数若 $\lim_{n\to\infty}\frac{|a_{n+1}|}{|a_n|}=\rho$（或 $+\infty$），则收敛半径
$$
R=\left\{
\begin{array}{l}
0,&\rho=+\infty\\
\frac{1}{\rho},&0<\rho<+\infty\\
+\infty,&\rho=0
\end{array}
\right.
$$
系数模根值法：对于幂级数若 $\lim_{n\to\infty}\sqrt[n]{|a_n|}=\rho$（或 $+\infty$），则收敛半径同上

幂级数逐项可导、逐项可积：积分是从 $0$ 积到 $x$

重要等式：$(2n)!!=2^nn!，\frac{1}{(n+1)^2}=(-\frac{1}{n+1})'$

### 泰勒（Taylor）级数

$$
\begin{array}{ll}
e^x=\sum^\infty_{n=0}\frac{x^n}{n!},&x\in(-\infty,+\infty)\\
\ln(1+x)=\sum^\infty_{n=1}\frac{(-1)^{n-1}x^n}{n},&x\in(-1,1]\\
\sin x=\sum^\infty_{n=0}(-1)^{n}\frac{x^{2n+1}}{(2n+1)!},&x\in(-\infty,+\infty)\\
\cos x=\sum^\infty_{n=0}(-1)^{n}\frac{x^{2n}}{(2n)!},&x\in(-\infty,+\infty)\\
(1+x)^\alpha=\sum^\infty_{n=0}\frac{\alpha(\alpha-1)\cdots(a-n+1)}{n!}x^n,&x\in(-1,1)
\end{array}
$$

### 傅里叶（Fourier）级数

三角级数：$\frac{a_0}{2}+\sum^\infty_{n=1}(a_n\cos nx+b_n\sin nx)$，三角函数系中任意两个不同函数乘积在 $[-\pi,\pi]$ 积分为 $0$（正交）

Fourier 系数公式：$a_n=\frac{1}{\pi}\int^\pi_{-\pi}f(x)\cos nxdx,n=0,1,2,\cdots$；$b_n=\frac{1}{\pi}\int^\pi_{-\pi}f(x)\sin nxdx,n=1,2,\cdots$

（将三角级数左右两端分别乘以 $\cos mx$ 或 $\sin mx$，利用正交性可得）

Dirichlet 收敛定理：设周期为 $2\pi$ 的函数 $f(x)$ 在 $[-\pi,\pi]$ 上分段单调且至多有有限个第一类间断点，则 $f(x)$ 的傅里叶级数收敛，并且在 $[-\pi,\pi]$ 上，其和函数满足：
$$
S(x)=\left\{
\begin{array}{l}
f(x),&当x是f(x)连续点\\
\frac{f(x-0)+f(x+0)}{2},&当x是f(x)间断点\\
\frac{f(\pi-0)+f(-\pi+0)}{2},&当x=\pm\pi
\end{array}
\right.
$$
正弦级数、余弦级数：当 $f(x)$ 在 $[-\pi,\pi]$ 为奇函数/偶函数时，$a_n$ 或 $b_n$ 等于 $0$，即仅含正弦/余弦项

周期为 $2l$ 的 Fourier 级数：$x=\frac{l}{\pi}t, F(t)=f(\frac{l}{\pi}t)$

1. $a_n=\frac{1}{l}\int^l_{-l}f(x)\cos\frac{n\pi}{l}xdx,n=0,1,2,\cdots$；$b_n=\frac{1}{l}\int^l_{-l}f(x)\sin \frac{n\pi}{l}xdx,n=1,2,\cdots$
2. $f(x)\sim\frac{a_0}{2}+\sum^\infty_{n=1}(a_n\cos\frac{n\pi}{l}x+b_n\sin\frac{n\pi}{l}x)$

---
title: 高等数学II 笔记
date: 2025-3-6 16:13:00
tags:
---

### 一阶微分方程

1. 可分离变量：$x,dx$ 移到一边，$y,dy$ 移到另一边，两边同时积分

2. 齐次微分方程：微分方程 $y'=f(x,y)$ 可表示为 $y'=g(\frac{y}{x})$，令 $u=\frac{y}{x}$，先求出关于 $u$ 的解再代入

3. $y'=f(ax+by+c)$ （其中 $b\ne0$）：令 $u=ax+by+c$，则 $y'=\frac{1}{b}(\frac{du}{dx}-a)$，代入原方程

4. $y'=f(\frac{a_1x+b_1y+c_1}{a_2x+b_2y+c_2})$：可先尝试化简，否则采取如下变量代换，先解出 $x_0,y_0$，再带入右侧
   $$
   \left\{
   \begin{array}{ll}
   a_1x+b_1y+c_1=0,\\
   a_2x+b_2y+c_2=0
   \end{array}
   \right.\quad\quad\quad
   \left\{
   \begin{array}{ll}
   X=x-x_0\\
   Y=y-y_0
   \end{array}
   \right.
   $$

### 一阶线性微分方程

即 $y'+P(x)y=Q(x)$，先求得齐次解 $y=Ce^{-\int P(x)dx}$，将 $C$ 看作 $C(x)$，代入原方程求解得通解：
$$
y=e^{-\int P(x)dx}(\int Q(x)e^{\int P(x)dx}dx+C)
$$
上述方法为**常数变易法**

### 伯努利方程

即 $y'+P(x)y=Q(x)y^\alpha,\alpha\ne0,1$，令 $z=y^{1-\alpha}$，再将 $y'=\frac{1}{1-\alpha}y^\alpha z'$ 代入方程得：
$$
z'+(1-\alpha)P(x)z=(1-\alpha)Q(x)
$$
此为一阶线性方程，先求出 $z$ 再转换到 $y$ 即可

### 可降阶高阶微分方程

1. $y^{(n)}=f(x)$：逐次积分
2. $y''=f(x,y')$：令 $p(x)=y'$，先求 $p$，再求 $y$
3. $y''=f(y,y')$：令 $p(y)=y'$，则 $y''=\frac{dp}{dy}\cdot\frac{dy}{dx}=p\cdot\frac{dp}{dy}$，代入原方程解出 $p=p(y)$，再求 $y$

### 叠加原理

若 $y_1(x),y_2(x)$ 分别为
$$
y^{(n)}(x) + p_1(x)y^{(n-1)}(x) + \cdots + p_{n-1}(x)y' + p_n(x)y(x) = f_1(x)\\
y^{(n)}(x) + p_1(x)y^{(n-1)}(x) + \cdots + p_{n-1}(x)y' + p_n(x)y(x) = f_2(x)
$$
的解，则 $C_1y_1(x)+C_2y_2(x)$ 是下面方程的解
$$
y^{(n)}(x) + p_1(x)y^{(n-1)}(x) + \cdots + p_{n-1}(x)y' + p_n(x)y(x) = C_1f_1(x) + C_2f_2(x)
$$
**推论**：若 $y_1(x),y_2(x)$ 是线性齐次微分方程
$$
y^{(n)}(x) + p_1(x)y^{(n-1)}(x) + \cdots + p_{n-1}(x)y' + p_n(x)y(x) = 0
$$
的解，则 $C_1y_1(x)+C_2y_2(x)$ 也是该方程的解

### Liouville 刘维尔公式（HL）

若 $y_1(x)$ 是方程 $y''+p(x)y'+q(x)y=0$ （HL）的非零解，则另一个线性无关解为：
$$
y_2(x)=y_1\int\frac{1}{y_1^2}e^{-\int p(x)dx}dx
$$

### 二阶线性非齐次方程（NHL）

即 $y''+p(x)y'+q(x)y=f(x)$，记为 NHL；若 $y*$ 为此方程的解，$y_1(x),y_2(x)$ 是齐次方程的基本解组，则通解为
$$
y=y*+C_1y_1(x)+C_2y_2(x)
$$
课本例 6.19：$y''+y=\tan x$，有齐次基本解组 $\cos x,\sin x$

设特解为 $\hat{y}=c_1(x)\cos x+c_2(x)\sin x$，求导 $\hat{y}'=c_1'(x)\cos x+c_2'(x)\sin x-c_1(x)\sin x+c_2(x)\cos x$

令 $c_1'(x)\cos x+c_2'(x)\sin x=0$，继续求 $y''$，代入原方程求解

**可推广到 $n$ 阶线性（齐次）微分方程**

### 常系数线性齐次微分方程






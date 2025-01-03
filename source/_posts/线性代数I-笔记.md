---
title: 线性代数I 笔记
date: 2024-11-08 16:49:37
tags:
---

### 矩阵

$(AB)^{-1}=B^{-1}A^{-1}$

$(AB)^\top=B^\top A^\top$

### 矩阵可逆的等价说法

1. $A$ 可逆
2. $A\vec{x}=0$ 只有平凡解
3. $A$ 的简化阶梯型为单位矩阵
4. $A$ 是一组初等矩阵的乘积
5. $A\vec{x}=\vec{b}$ 对任何 $n\times1$ 的列向量 $\vec{b}$ 都有解（且仅有一个解）
6. $\det(A)\neq0$
7. $A$ 的所有 $n$ 个**行**向量线性无关
8. $A$ 的所有 $n$ 个**列**向量线性无关
9. $span(Row(A))=\mathbb{R}^n$
10. $span(Col(A))=\mathbb{R}^n$
11. $A$ 的所有 $n$ 个**行**向量构成 $\mathbb{R}^n$ 的一组基底
12. $A$ 的所有 $n$ 个**列**向量构成 $\mathbb{R}^n$ 的一组基底
13. $rank(A)=n$
14. $nullity(A)=0$

### 行列式

$$
a_{i1}C_{k1}+\cdots+a_{in}C_{kn}=
\left\{
\begin{aligned}
det(A),i=k\\
0,i\ne k
\end{aligned}
\right.
$$

### 伴随矩阵

任意 $n$ 阶方阵 $A$，有 $Aadj(A)=\det(A)I_n$

推论：$\det(adj(A))=\det(A)^{n-1}$，$A=\det(adj(A))^{\frac{1}{n-1}}adj(A)^{-1}$

### 向量例题 

例题 期中模拟第二题判断：如果 $A\vec{x}=B\vec{x}$ 对任意 $\vec{x}\in\mathbf{R}^n$ 都成立，则 $A=B$ （正确）

因为对任意 $\vec{x}$ 都成立，则考虑任意 $\vec{e_i},i=1,\dots,n$，即 $\mathbf{R}^n$ 标准单位向量（列向量形式），由于 $A\vec{e_i}$ 为 $A$ 的第 $i$ 列向量，因此如果题中条件成立，则对任意 $i$ 都有 $A$ 的第 $i$ 列与 $B$ 的第 $i$ 列相等，故 $A=B$

### 正交投影

$\vec{u}$ 在 $\vec{v}$ 上正交投影：
$$
proj_{\vec{v}}(\vec{u})=\frac{\vec{u}\cdot\vec{v}}{||\vec{v}||^2}\vec{v}
$$

### 叉乘

**仅对三维空间里的向量定义**

$\vec{u}\times\vec{v}$ 与 $\vec{u}$ 和 $\vec{v}$ 正交

Lagrange's identity: $||\vec{u}\times\vec{v}||^2=||\vec{u}||^2||\vec{v}||^2-(\vec{u}\cdot\vec{v})^2$

Cauchy-Schwarz inequality: $|\vec{u}\cdot\vec{v}|\leq||\vec{u}||\ ||\vec{v}||$

Triangle inequality: $||\vec{u}+\vec{v}||\leq||\vec{u}||+||\vec{v}||,d(\vec{u},\vec{v})\leq d(\vec{u},\vec{w})+d(\vec{w},\vec{v})$

$\vec{u}\times\vec{v}=-\vec{v}\times\vec{u},\vec{u}\times\vec{u}=0$

### 向量空间

注意：要满足有零向量、满足加法交换律结合律、有加法相反数

### 秩

$rank(A^\top A)=rank(A)$






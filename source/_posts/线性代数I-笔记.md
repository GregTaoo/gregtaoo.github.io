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

1. 秩-零化度定理：$rank(A)+nullity(A)=n$ ($A$ 列数，即 $A\vec{x}$ 中 $\vec{x}$ 维数)
2. $W\subset\mathbb{R}^n$ 为一个子空间，则 $\dim(W)+\dim(W^\perp)=n$
3. $A\in M_{m\times n},B\in M_{n\times k}$，且 $AB=0_{m\times k}$，则 $Col(B)\subset Null(A), rank(B)\le nullity(A)$
4. $A\in M_{m\times n},B\in M_{n\times k}$，必然有 $rank(AB)\le rank(A)$
5. $A\in M_{m\times n}$，都有 $rank(A^\top A)=rank(A)$

### 矩阵变换

1. 单射 (one-to-one/injective)，满射 (surjective/be onto)，双射 (bijection)
2. $T:\mathbb{R}^n\rightarrow\mathbb{R}^m,[T]\in M_{m\times n}$，则 $Ker(T)=Null([T])$，$RAN(T)=Col([T])$
3. $T$ 单射，当且仅当 $Ker(T)=Null([T])=\{0\}$，即 $nullity([T])=0$ (若 $n>m$ 则不可能单射)
4. $T$ 满射，当且仅当 $RAN(T)=Col([T])=\mathbb{R}^m$，即 $rank([T])=m$ (若 $n<m$ 则不可能满射)
5. $m=n$ 时，$T$ 双射当且仅当 $[T]$ 可逆；若 $T$ 单射或满射，则必双射

### 线性变换

1. $T:V\rightarrow W$ 为线性变换，则 $\dim(Ker(T))=nullity(T),\dim(RAN(T))=rank(T)$
2. $rank(T)+nullity(T)=\dim(V)$
3. 一个双射的线性变换 $T:V\rightarrow W$ 是一个同构 (Isomorphism)，$V$ 与 $W$ 是同构的 (V is isomorphic to W)
4. 任何 $n$ 维的向量空间 $V$ 都与欧氏空间 $\mathbb{R}^n$ 同构

### 相似矩阵

1. 两个方阵相似，即 $B=P^{-1}AP$
2. $[T]_{B',B'}=(P_{B\leftarrow B'})^{-1}[T]_{B,B}P_{B\leftarrow B'}$ (补充：$P_{B'\leftarrow B}=(B')^{-1}B$)
3. 相似矩阵行列式、秩、零化度、迹 (trace) 、特征值、特征多项式、特征空间维数相等，为相似不变量

### 特征值与特征向量

1. $A$ 为 $n$ 阶方阵，存在非零向量 $\vec{x}\in\mathbb{R}^n$，且 $A\vec{x}=\lambda\vec{x}$，则 $\lambda$ 为特征值，$\vec{x}$ 为对应的特征向量

2. $\lambda$ 为 $A$ 特征值时，$\lambda I_n-A$ 不可逆，且：
   $$
   \begin{aligned}
   \exist\vec{x}\in\mathbb{R}^n,\vec{x}\ne0,A\vec{x}=\lambda\vec{x}
   &\Leftrightarrow\exist\vec{x}\in\mathbb{R}^n,\vec{x}\ne0,(\lambda I_n-A)\vec{x}=0\\
   &\Leftrightarrow Ker(\lambda I_n-A)\ne\{0\}\\
   &\Leftrightarrow\det(\lambda I_n-A)=0
   \end{aligned}
   $$

3. $p(\lambda)=\det(\lambda I_n-A)=\lambda^n-tr(A)\lambda^{n-1}+c_2\lambda^{n-2}+\cdots+c_{n-1}\lambda+(-1)^n\det(A)$
4. 上/下三角矩阵的特征值为对角线上元素
5. $A$ 可逆当且仅当 $\lambda=0$ 不是 $A$ 的特征值
6. $f(x)=a_0+a_1x+\cdots+a_mx^m$，则 $\vec{x}$ 为 $f(A)$ 关于 $f(\lambda)$ 的特征向量
7. $V_{\lambda}=Null(\lambda I_n-A)$ 为特征空间，有 $V_{\lambda_1}\cap V_{\lambda_2}=\{0\}$，则 $\dim(V_{\lambda_1}+V_{\lambda_2})=\dim(V_{\lambda_1})+\dim(V_{\lambda_2})$
8. 若 $z\in\mathbb{C}$ 是 $A$ 的特征值，则其共轭也是 $A$ 的特征值
9. 若 $n$ 为奇数，则对于任何实数矩阵，必然都有至少一个实数特征值

### 对角化

1. 若 $A\in M_{n\times n}$ 有 $n$ 个不同的特征值，则可对角化；若所有特征值的几何重数都等于代数重数，则可对角化
2. 对于 $A$ 任意特征值，它的几何重数（特征空间维数）都小于等于它的代数重数

### 正交对角化

1. 正交矩阵：$A^TA=AA^T=I_n$，即 $A^{-1}=A^T$
2. 正交规范/标准集合：集合内向量两两正交，且 $||\vec{v_i}||=1$
3. $A$ 为正交矩阵，其 $n$ 个行/列向量构成 $\mathbb{R}^n$ 的标准正交基底
4. $A$ 为正交矩阵，当且仅当 $||A\vec{x}||=||\vec{x}||$，当且仅当 $A\vec{x}\cdot A\vec{y}=\vec{x}\cdot\vec{y}$
5. $A$ 为正交矩阵，则 $A$ 可逆且 $A^{-1}$ 也为正交矩阵；若 $B$ 也为正交矩阵，则 $AB$ 为正交矩阵
6. $A$ 为正交矩阵，则 $\det(A)=1$ 或 $\det(A)=-1$，且 $\lambda=1$ 或 $\lambda=-1$
7. 若 $S$ 和 $S'$ 均为标准正交基底，则 $P_{S'\leftarrow S}$ 和 $P_{S\leftarrow S'}$ 均为正交矩阵
8. $A$ 可正交对角化当且仅当 $A$ 为对称矩阵（$A$ 的所有特征值均为实数）

### 最小二乘法

若求解形如 $A\vec{x}=\vec{b}$ 最小值问题，则求解 $(A^TA)\vec{x}=A^T\vec{b}$


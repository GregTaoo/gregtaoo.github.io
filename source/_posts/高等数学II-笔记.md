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

即 $y'+P(x)y=Q(x)$，先求得齐次解 $y=Ce^{-\int P(x)dx}$，将 $C$ 看作 $C(x)$，代入原方程求解得 $C(x)$，然后得通解：
$$
y=e^{-\int P(x)dx}\left(\int Q(x)e^{\int P(x)dx}dx+C\right)
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

### 二阶线性齐次方程/刘维尔公式（HL）

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

### 常系数线性齐次方程

如 $y''+py'+qy=0$，猜测其可化为 $(r^2+pr+q)e^{rx}=0$，得特征方程 $r^2+pr+q=0$ 再解得特征根，即可求得：
1. $r_1\ne r_2,r_{1},r_{2}\in\mathbb{R}$：通解为 $y=C_1e^{r_1x}+C_2e^{r_2x}$ 
2. $r_1=r_2,r_{1},r_{2}\in\mathbb{R}$：用刘维尔公式求得 $y=C_1e^{rx}+C_2xe^{rx}$
3. $r_1=\alpha+i\beta,r_{2}=\alpha-i\beta$：用欧拉公式得 $y=C_1e^{\alpha x}\cos\beta x+C_{2}e^{\alpha x}\sin\beta x$

推广到 $y^{(n)}+p_{1}y^{(n-1)}+\cdots+p_{n-1}y'+p_{n}=0$：
1. 单实根：$e^{rx}$
2. $k$ 重实根：$e^{rx},xe^{rx},\cdots,x^{k-1}e^{rx}$
3. 单重共轭复根：$e^{\alpha x}\cos\beta x,e^{\alpha x}\sin\beta x$
4. $k$ 重共轭复根：$e^{\alpha x}\cos\beta x,e^{\alpha x}\sin\beta x,\cdots,x^{k-1}e^{\alpha x}\cos\beta x,x^{k-1}e^{\alpha x}\sin\beta x$

### 常系数线性非齐次方程

二阶基本形式：$y''+py'+qy=f(x)$，$f(x)$ 为连续函数，考虑其不同形式：
- $f(x)=(b_0x^m+b_1x^{m-1}+\cdots+b_{m-1}x+b_m)e^{\lambda x}$：特解为 $y^*=x^k(B_{0}x^m+B_{1}x^{m-1}+\cdots+B_{m-1}x+B_{m})e^{\lambda x}$，其中 $k$ 为 $\lambda$ 作为特征方程的根的重数
- $f(x)=[P(x)\cos\beta x+Q(x)\sin\beta x]e^{\alpha x}=\frac{1}{2}e^{\alpha x-i\beta x}[P(x)+iQ(x)]$：特解为 $y^*=x^k[A(x)\cos\beta x+B(x)\sin\beta x]e^{\alpha x}$，其中 $k$ 是 $\alpha+i\beta$ 作为特征方程的根的重数，$P(x),Q(x)$ 最高次数为 $m$，$A(x),B(x)$ 均为 $m$ 次待定多项式

### 欧拉方程

二阶欧拉方程：$x^2y''+pxy'+qy=0$，设 $x=e^t,y=y(t)$，带入求得 $y$ 与 $t$ 的二阶常系数线性方程：$\frac{d^2y}{dt^2}+(p-1) \frac{dy}{dt}+qy=0$，引入记号 $D=\frac{d}{dt}$，则化为：
$$
[D(D-1)+pD+q]y=0
$$
其特征方程为 $r(r-1)+pr+q=0$，易解出原方程通解

### 微分方程数值解

略

### 向量

- $|\vec{a}\times \vec{b}|=|\vec{a}|\cdot|\vec{b}|\cdot \sin(\widehat{\vec{a},\vec{b}})$
- 混合积（围成体积）
$$
[\vec{a},\vec{b},\vec{c}]=\begin{vmatrix}
a_{1} & a_{2} & a_{3} \\
b_{1} & b_{2} & b_{3} \\
c_{1} & c_{2} & c_{3}
\end{vmatrix}
$$
- 空间四点共面充要条件即体积为 $0$

### 空间平面

- 点法式：$A(x-x_0)+B(y-y_0)+C(z-z_0)=0$，法向量 $\vec{n}=(A,B,C)$
- 一般式：$Ax+By+Cz+D=0$
- 截距式：$\frac{x}{a}+\frac{y}{b}+\frac{z}{c}=1$，$a,b,c$ 分别在 $x,y,z$ 轴截距
- 标准式：$\vec{u},\vec{v}$ 在平面上不共线
$$
\begin{vmatrix}
x-x_{0} & y-y_{0} & z-z_{0} \\
u_{1} & u_{2} & u_{3} \\
v_{1} & v_{2} & v_{3}
\end{vmatrix}
=0
$$
- 三点式：平面上三个不共线的点
$$
\begin{vmatrix}
x-x_{1} & y-y_{1} & z-z_{1} \\
x_{2}-x_{1} & y_{2}-y_{1} & z_{2}-z_{1} \\
x_{3}-x_{1} & y_{3}-y_{1} & z_{3}-z_{1}
\end{vmatrix}
=0
$$

### 空间直线

- 参数式：$\vec{s}=(m,n,p)$ 为方向向量
$$
\begin{cases}
x=x_{0}+tm \\
y=y_{0}+tn \\
z=z_{0}+tp
\end{cases}
\quad t\in\mathbb{R}
$$
- 标准式/点向式：$\frac{x-x_{0}}{m}=\frac{y-y_{0}}{n}=\frac{z-z_{0}}{p}$
- 两点式：$\frac{x-x_{1}}{x_{2}-x_{1}}=\frac{y-y_{1}}{y_{2}-y_{1}}=\frac{z-z_{1}}{z_{2}-z_{1}}$
- 一般式：
$$
\begin{cases}
A_{1}x+B_{1}y+C_{1}z+D_{1}=0 \\
A_{2}x+B_{2}y+C_{2}z+D_{2}=0
\end{cases}
\quad
(A_{1}:B_{1}:C_{1}\ne A_{2}:B_{2}:C_{2})
$$
- 点 $P$ 到直线距离公式：直线方向向量 $\vec{s}$，取直线上一点 $M$，则距离
$$
d=\frac{|\overrightarrow{MP}\times \vec{s}|}{|\vec{s}|}
$$
- 验证两条直线异面：分别取两点，然后 $[\overrightarrow{M_1M_2},\vec{s_{1}},\vec{s_{2}}]=0$
- 求两条直线 $l_{1},l_{2}$ 公垂线 $l$：设 $l_{1},l$ 平面为 $\pi_{1}$，$l_{2},l$ 平面为 $\pi_{2}$，则公垂线为：
$$
\begin{cases}
[\overrightarrow{M_{1}M},\vec{s_{1}},\vec{s_{1}}\times\vec{s_{2}}]=0 \\
[\overrightarrow{M_{2}M},\vec{s_{2}},\vec{s_{1}}\times\vec{s_{2}}]=0 
\end{cases}
$$
### 曲面/曲线

- 椭球面：$\frac{x^2}{a^2}+\frac{y^2}{b^2}+\frac{z^2}{c^2}=1$ $(a>0,b>0,c>0)$，其中 $a,b,c$ 称为半轴
- 单叶双曲面：$\frac{x^2}{a^2}+\frac{y^2}{b^2}-\frac{z^2}{c^2}=1$ $(a>0,b>0,c>0)$
- 双叶双曲面：$-\frac{x^2}{a^2}-\frac{y^2}{b^2}+\frac{z^2}{c^2}=1$ $(a>0,b>0,c>0)$
- 椭圆抛物面：$\frac{x^2}{a^2}+\frac{y^2}{b^2}=z$ $(a>0,b>0)$，与对称轴交点称为顶点
- 双曲抛物面：$\frac{x^2}{a^2}-\frac{y^2}{b^2}=z$ $(a>0,b>0)$
- 柱面：母线沿准线移动形成的面
- 旋转面：曲线 $C$ （子午线）绕定直线（对称轴）旋转一周的曲面
- 锥面：准线中间固定在顶点，另一段沿母线移动形成锥面
- 曲面可表示为双参数方程

- 曲线一般式方程，参数方程：即两个相交曲面方程联立
- 曲线在坐标平面的投影：分别变换消去 $x,y,z$ 即可

### 偏导数/全微分

- $f_{xy}=\frac{\partial^2f}{\partial x\partial y}=\frac{\partial}{\partial y}\left( \frac{\partial f}{\partial x} \right)$
- 全微分：$\mathrm{d}f = f_x\, \mathrm{d}x + f_y\, \mathrm{d}y$
- 偏导数连续 $\Rightarrow$ 可微 $\Rightarrow$ 连续 & 可偏导
- 全微分近似计算：$f(x,y)\approx f(x_{0},y_{0})+f_{x}(x_{0},y_{0})(x-x_{0})+f_{y}(x_{0},y_{0})(y-y_{0})$

### 隐函数的偏导数

- 隐函数存在定理：$F(x,y)$ 在 $(x_0,y_0)$ 邻域内具有连续偏导数，且 $F(x_0,y_0)=0,F_y(x_0,y_0)\ne0$，则可确定唯一的 $y=y(x)$，且 $\frac{dy}{dx}=\frac{\partial y}{\partial x}=-\frac{F_{x}}{F_{y}}$
- 若隐函数以方程组 $F(x_0,y_0,u_0,v_0)=0,G(x_0,y_0,u_0,v_0)=0$ 确定，则有行列式
$$
J=\frac{\partial(F,G)}{\partial(u,v)}=
\begin{vmatrix}
\frac{ \partial F }{ \partial u } & \frac{ \partial F }{ \partial v }  \\
\frac{ \partial G }{ \partial u }  & \frac{ \partial G }{ \partial v } 
\end{vmatrix}
$$
- 若该 Jacobi 行列式在 $(x_0,y_0,u_0,v_0)$ 处不等于 $0$，则可确定唯一一组 $u=u(x,y),v=v(x,y)$，且有连续偏导数：
$$
\begin{aligned}
u_x &= -\frac{1}{J} \cdot \frac{\partial(F, G)}{\partial(x, v)} \quad
v_x = -\frac{1}{J} \cdot \frac{\partial(F, G)}{\partial(u, x)} \\
u_y &= -\frac{1}{J} \cdot \frac{\partial(F, G)}{\partial(y, v)} \quad
v_y = -\frac{1}{J} \cdot \frac{\partial(F, G)}{\partial(u, y)}
\end{aligned}
$$

### 方向导数/梯度

- 方向导数：将方向向量单位化 $\vec{l^0}$，则 $\frac{ \partial u }{ \partial l }|_{M_{0}}=(u_{x},u_{y})\cdot\vec{l^0}$
- 梯度：$\text{grad }f=\nabla f=(f_{x},f_{y})$，$\nabla$ 为哈密顿算子

### 切线/切平面/法线/法平面

- 参数方程求切向量：$\vec{\tau}=(x'(t_{0}),y'(t_{0}),z'(t_{0}))$
- 两个隐函数：左右同时微分，代入点 $M_0$，得 $k(dx,dy,dz)$ 即切向量
- 光滑曲线：在每一个点有切线且切向量 $(x'(t),y'(t),z'(t))$ 连续变化
- 切平面：取法向量 $\vec{n}=\nabla F(M_{0})=(F_{x},F_{y},F_{z})$
- 光滑曲面：对曲面 $F(x,y,z)=0$，$F$ 有连续偏导数且 $F_x^2+F_y^2+F_z^2\ne0$，那么每点都有切平面，且法向量连续变化
- 两个曲面交线切向量：求两个曲面的法向量，再叉乘

### 二元泰勒公式

- 二元泰勒公式
$$
f(x_0+\Delta x,y_0+\Delta y)=\sum_{k=0}^n \frac{1}{k!}\left( \Delta x \frac{\partial}{\partial x} + \Delta y \frac{\partial}{\partial y} \right)^k f(x_{0},y_{0})+R_{n}
$$
- 拉格朗日型余项：
$$
R_{n}=\frac{1}{(n+1)!}\left( \Delta x \frac{\partial}{\partial x} + \Delta y \frac{\partial}{\partial y} \right)^{n+1} f(x_{0}+\theta\Delta x,y_{0}+\theta\Delta y),0<\theta<1
$$
- 拉格朗日中值定理（取 $n=0$）：
$$
f(x_{0}+\Delta x,y_{0}+\Delta y)-f(x_{0},y_{0})=f_{x}(x_{0}+\theta\Delta x,y_{0}+\theta\Delta y)\Delta x+f_{y}\Delta y,0<\theta<1
$$
- Peano 型余项
$$
R_{n}=o(\phi^n),\phi=\sqrt{ (\Delta x)^2+(\Delta y)^2 }
$$
- Maclaurin 公式（取 $x_0=0,y_0=0$）
$$
f(x,y)=\sum_{k=0}^n \frac{1}{k!}\left( \Delta x \frac{\partial}{\partial x} + \Delta y \frac{\partial}{\partial y} \right)^k f(0,0)+\frac{1}{(n+1)!}\left( \Delta x \frac{\partial}{\partial x} + \Delta y \frac{\partial}{\partial y} \right)^{n+1} f(\theta x,\theta y),0<\theta<1
$$
- 二阶泰勒公式
$$
\begin{aligned}
f(x, y) \approx\ & f(a, b) 
+ f_x(a, b)(x - a) + f_y(a, b)(y - b) \\
& + \frac{1}{2}f_{xx}(a, b)(x - a)^2 
+ f_{xy}(a, b)(x - a)(y - b) 
+ \frac{1}{2}f_{yy}(a, b)(y - b)^2
\end{aligned}
$$

### 二元函数极值

- 二元函数极值必要条件：$f_x(x_0,y_0)=f_y(x_0,y_0)=0$（驻点），极值点存在于驻点或至少有一个偏导数不存在的点中
- 二元函数极值充分条件：若二元函数在某领域有二阶连续偏导数，且 $P_0(x_0,y_0)$ 为驻点，记 $A=f_{xx}(x_0,y_0),B=f_{xy},C=f_{yx},D=f_{yy}$，且 $H=AC-B^2$，则： 当 $H>0$ 时 $f(x_0,y_0)$ 为极值，若 $A>0$ 为极小值，若 $A<0$ 为极大值；当 $H<0$ 时不是极值
- 条件极值/拉格朗日乘数法：在 $\phi=0$ 的约束下求 $f$ 极值，引进函数 $F(x,y,z,\lambda)=f+\lambda g$，求解方程组 $F_x=F_y=F_z=F_\lambda=\phi=0$

### 重积分

- Jacobi 行列式：换元的目标对象放在下面。如 $x,y$ 换 $u, v$，则求 $\frac{\partial(x,y)}{\partial(u,v)}$
- 球坐标：$x=r\sin \phi \cos \theta,y=r\sin \phi \sin \theta,z=r\cos \phi,|J|=r^2\sin \phi$
- 平面薄片的静力矩：$x$ 轴为 $M_x = \iint_{D} y \mu(x,y)d\sigma$，$y$ 轴为 $M_y = \iint_{D} x \mu(x,y)d\sigma$
- 质心位置：$x=\frac{M_{y}}{m}=\frac{\iint_{D} x \mu(x,y)d\sigma}{\iint_{D} \mu(x,y)d\sigma},y=\frac{M_{x}}{m}=\frac{\iint_{D} y \mu(x,y)d\sigma}{\iint_{D} \mu(x,y)d\sigma}$
- 面密度 $\mu$ 为常数时，薄片质心即形心，形心位置：$x=\frac{1}{A_{D}}\iint xd\sigma,y=\frac{1}{A_{D}}\iint yd\sigma$
- 转动惯量：$I_{x}=\iiint_{\Omega}(y^2+z^2)\mu dV,I_{O}=\iiint_{\Omega}(x^2+y^2+z^2)\mu dV$
- 引力：$F_x=\iiint_{\Omega}\frac{km_{0}\mu(x-x_{0})}{r^3}dV$

### 第一类曲线/曲面积分

- 曲线 $\int_{C}f(x,y)ds$：$ds=\sqrt{ x'^2(t)+y'^2(t) }dt=\sqrt{ 1+y'^2(t) }dx$
- 曲面 $\iint_{\Sigma}f(x,y,z)dS$：若从 $x,y,z$ 换到 $u,v$，则令 $\vec{r}(u,v)=(x(u,v),y(u,v),z(u,v))$，$dS=|\vec{r_{x}}\times\vec{r_{y}}|dxdy=|(\frac{\partial(y,z)}{\partial(u,v)},\frac{\partial(z,x)}{\partial(u,v)},\frac{\partial(x,y)}{\partial(u,v)})|dxdy=\sqrt{ A^2+B^2+C^2 }dxdy=\sqrt{ 1+z_{x}^2+z_{y}^2 }dxdy$

### 第二类曲线/曲面积分

- 曲线 $\int_{C}\vec{F}(x,y)\cdot d \vec{r}=\int_{C}[\vec{F}(x,y)\cdot \vec{e_{r}}(x,y)]ds=\int_{C}Pdx+Qdy=\int_{\alpha}^\beta[Px'(t)+Qy'(t)]dt=\int_{a}^b[P+Qy'(x)]dx$
- 曲面 $\iint_{\Sigma}\vec{F}(x,y,z)\cdot d \vec{S}=\iint_{\Sigma}\vec{F}\cdot\vec{n^0}dS=\pm \iint_{D}(PA+QB+RC)dudv=\pm \iint_{D_{xy}}(-Pz_{x}-Qz_{y}+R)dxdy$
- 曲面合一投影法：$x,y,z$ 分开求；即 $P=Q=0$时，$\iint_{\Sigma}Rdxdy=\pm \iint_{D_{xy}}R(x,y,z(x,y))dxdy$

### Green 公式

- 正方向：逆时针；反方向：顺时针
- 若 $D$ 内的任意一条封闭曲线所围成的区域都在 $D$ 内则称区域 $D$ 为单连通的，否则为复连通的
- $\oint_{C^+}Pdx+Qdy=\iint_{D}\left( \frac{\partial Q}{\partial x}-\frac{\partial P}{\partial y} \right)dxdy$ （沿曲线切向量方向）
- 向量形式：$\vec{F}(x,y)=(f,g), \oint_{C^+}\vec{F}\cdot \vec{n^0}ds=\oint_{C}(-gdx+fdy)= \iint_{D} \nabla \cdot \vec{F}d\sigma=\iint_{D} \left( \frac{\partial f}{{\partial x}}+\frac{\partial g}{{\partial y}} \right) d\sigma$  ($\vec{n}_{0}$ 为法向量，垂直于切向量 $\vec{e_{r}}$，沿垂直方向，用于计算流量) 
- 如果曲线不封闭，则先封闭，再扣除新增曲线。如果过原点，则画半径为 $\epsilon$ 的圆/椭圆。
- 平面区域 $D$ 的面积：$A_D=\iint_{D} dxdy=\oint_{C^+}xdy=-\oint_{C^+}ydx=\frac{1}{2}\oint_{C^+}xdy-ydx$
- 若函数 $P,Q$ 在单连通区域 $D$ 上有连续的偏导数，则以下几个条件相互等价：
- 1. 对 $D$ 内任一条分段光滑闭曲线 $C$，有 $\oint_{C}Pdx+Qdy=0$
- 2. 曲线积分 $\int_{C}Pdx+Qdy$ 在 $D$ 内与路径无关
- 3. 存在 $D$ 上的可微函数 $u(x,y)$，使得 $du=Pdx+Qdy$
- 4. 等式 $\frac{{\partial Q}}{dx}=\frac{{\partial P}}{{\partial y}}$ 在 $D$ 内处处成立

### 全微分方程

- 前提条件：函数 $P,Q$ 在单连通区域 $D$ 上有连续的偏导数，且等式 $\frac{\partial Q}{dx}=\frac{\partial P}{{\partial y}}$ 在 $D$ 内处处成立
- 方法1：选择一个点 $(x_0,y_0)$，然后先沿着 $x$ 或 $y$ 轴平行的直线积分，再积到 $(x,y)$
- 方法2：先取 $u=\int \frac{\partial u}{\partial x}dx=\int Pdx=f(x,y)+C(y)$，则 $\frac{\partial u}{\partial y}=f'(x,y)+C'(y)=Q$，即可解出
- 若 $\frac{{\partial Q}}{dx}\ne\frac{{\partial P}}{{\partial y}}$，则需要凑微分凑出正确形式，一般需要乘以积分因子：$\frac{1}{x^2}, \frac{1}{y^2}, \frac{1}{xy}, \frac{1}{x^2+y^2}, \frac{1}{x^2y^2}, \frac{1}{\sqrt{ x^2+y^2 }}$

### Gauss 公式

- $S^+$ 为曲面外侧

$$
\iint_{S^+} Pdydz+Qdzdx+Rdxdy=\iiint_{\Omega}\left(\frac{\partial P}{{\partial x}}+\frac{\partial Q}{{\partial y}}+\frac{\partial R}{{\partial z}}\right)dV
$$
- 空间区域 $\Omega$ 体积计算公式：
$$
V_{\Omega}=\frac{1}{3}\iint_{S^+}xdydz+ydzdx+zdxdy
$$
- 通量：$\Phi=\iint_{\Sigma}\vec{F}\cdot d\vec{S}$
- 散度：$\nabla \cdot \vec{F}=div \vec{F}=\frac{\partial P}{{\partial x}}+\frac{\partial Q}{{\partial y}}+\frac{\partial R}{{\partial z}}$
- Gauss 公式的向量形式：$\iint_{S^+}\vec{F}\cdot d\vec{S}=\iiint_{\Omega}div \vec{F}dV$（向量场 $F$ 的散度场为数量场）

### Stokes 公式*

- Green 公式的三维下的推广
- 曲线 $C$ 方向与曲面 $\Sigma$ 法向量方向（拇指）符合右手法则
$$
\oint_{C}Pdx+Qdy+Rdz=\iint_{\Sigma}\left( \frac{\partial R}{{\partial y}}-\frac{\partial Q}{{\partial z}} \right)dydz+\left( \frac{\partial P}{{\partial z}}-\frac{\partial R}{{\partial x}} \right)dzdx+\left( \frac{\partial Q}{{\partial x}}-\frac{\partial P}{{\partial y}} \right)dxdy
$$
- 环量：$\int_{L}\vec{F}\cdot d\vec{r}=\int_{L}Pdx+Qdy+Rdz$（即第二类曲线积分）
- 旋度：即 Green 公式或 Stokes 公式算出来的值，在 $M$ 点旋度记为 $rot \vec{F}(M), curl\vec{F}(M)=\nabla \times \vec{F}$

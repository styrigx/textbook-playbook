# 全书公式速查

导读：按主题汇总的公式表，只收"做题时要查"的东西。证明思路和解题套路见各章文件。

## 极限

- $\displaystyle\lim_{x\to 0}\frac{\sin x}{x}=1$，$\displaystyle\lim_{x\to 0}\frac{1-\cos x}{x}=0$
- $\displaystyle\lim_{n\to\infty}\left(1+\frac1n\right)^n=e$，$\displaystyle\lim_{x\to 0}(1+x)^{1/x}=e$
- $\displaystyle\lim_{x\to 0}\frac{\ln(1+x)}{x}=1$，$\displaystyle\lim_{x\to 0}\frac{e^x-1}{x}=1$
- $\displaystyle\lim_{n\to\infty}\frac{x^n}{n!}=0$（任意固定的 $x$）
- 洛必达法则（$0/0$ 或 $\infty/\infty$ 型，$g'\ne 0$）：$\displaystyle\lim_{x\to a}\frac{f(x)}{g(x)}=\lim_{x\to a}\frac{f'(x)}{g'(x)}$
- 指数型化归：$1^{\pm\infty},0^0,\infty^0$ 一律取对数化为 $0\times\infty$ 再做

## 求导法则

- 定义：$\displaystyle f'(x)=\lim_{h\to 0}\frac{f(x+h)-f(x)}{h}$
- $(x^n)'=nx^{n-1}$；$(fg)'=f'g+fg'$；$\displaystyle\left(\frac{f}{g}\right)'=\frac{f'g-fg'}{g^2}$
- 链式法则：$\displaystyle\frac{dy}{dx}=\frac{dy}{du}\cdot\frac{du}{dx}$
- 反函数：$(f^{-1})'(y)=\dfrac{1}{f'(x)}$，其中 $y=f(x)$ 且 $f'(x)\ne 0$
- 取对数求导：$y=x^x$ 型先 $\ln y=x\ln x$ 再求导

## 三角函数求导与恒等式

- $(\sin x)'=\cos x$，$(\cos x)'=-\sin x$，$(\tan x)'=\sec^2 x$
- $(\cot x)'=-\csc^2 x$，$(\sec x)'=\sec x\tan x$，$(\csc x)'=-\csc x\cot x$
- $\sin^2x+\cos^2x=1$；$1+\tan^2x=\sec^2x$；$1+\cot^2x=\csc^2x$
- $\sin 2x=2\sin x\cos x$；$\cos 2x=\cos^2x-\sin^2x=2\cos^2x-1=1-2\sin^2x$
- 降幂：$\sin^2x=\dfrac{1-\cos 2x}{2}$，$\cos^2x=\dfrac{1+\cos 2x}{2}$

## 指数、对数、双曲函数

- $e=\lim_{n\to\infty}(1+1/n)^n$；对数法则要求底数和真数 $>0$
- $(e^x)'=e^x$；$(a^x)'=a^x\ln a$；$(\ln x)'=\dfrac1x$；$(\log_a x)'=\dfrac{1}{x\ln a}$
- $\sinh x=\dfrac{e^x-e^{-x}}{2}$，$\cosh x=\dfrac{e^x+e^{-x}}{2}$；$(\sinh x)'=\cosh x$，$(\cosh x)'=\sinh x$

## 反三角函数

- $(\arcsin x)'=\dfrac{1}{\sqrt{1-x^2}}$，$(\arccos x)'=-\dfrac{1}{\sqrt{1-x^2}}$，$(\arctan x)'=\dfrac{1}{1+x^2}$

## 微积分基本定理

- FTC1：$f$ 在 $[a,b]$ 连续 $\Rightarrow$ $\displaystyle\frac{d}{dx}\int_a^x f(t)\,dt=f(x)$
- 变形：下限为变量添负号；上限为函数用链式法则；上下限都为函数拆成两项
- FTC2（牛顿–莱布尼茨）：$\displaystyle\int_a^b f(x)\,dx=F(b)-F(a)$，其中 $F'=f$
- 积分平均值：$\displaystyle\bar f=\frac{1}{b-a}\int_a^b f(x)\,dx$

## 常用不定积分

- $\int x^n\,dx=\dfrac{x^{n+1}}{n+1}+C\ (n\ne-1)$；$\int\frac{dx}{x}=\ln|x|+C$
- $\int e^x\,dx=e^x+C$；$\int a^x\,dx=\dfrac{a^x}{\ln a}+C$
- $\int\sin x\,dx=-\cos x+C$；$\int\cos x\,dx=\sin x+C$
- $\int\sec^2x\,dx=\tan x+C$；$\int\csc^2x\,dx=-\cot x+C$
- $\int\sec x\tan x\,dx=\sec x+C$；$\int\csc x\cot x\,dx=-\csc x+C$
- $\int\frac{dx}{1+x^2}=\arctan x+C$；$\int\frac{dx}{\sqrt{1-x^2}}=\arcsin x+C$

## 积分方法

- 换元法：看到复合结构设 $u$；定积分换元必须换限
- 分部积分：$\int u\,dv=uv-\int v\,du$（选 $u$ 顺序：反对幂指三）
- 部分分式：先长除法化为真分式再拆；基本型 $\int\frac{dx}{x-a}$、$\int\frac{dx}{x^2+a^2}$
- 三角换元：$\sqrt{a^2-x^2}\to x=a\sin\theta$；$\sqrt{x^2+a^2}\to x=a\tan\theta$；$\sqrt{x^2-a^2}\to x=a\sec\theta$

## 反常积分判别

- $\int_1^\infty\frac{dx}{x^p}$：$p>1$ 收敛，$p\le 1$ 发散
- $\int_0^1\frac{dx}{x^p}$：$p<1$ 收敛，$p\ge 1$ 发散
- 先找破裂点拆积分；含负项先取绝对值看绝对收敛

## 级数判别

- 几何级数：$\sum_{n=0}^\infty ar^n=\dfrac{a}{1-r}$（$|r|<1$）
- $p$-级数 $\sum\frac1{n^p}$：$p>1$ 收敛；调和级数 $\sum\frac1n$ 发散
- 第 $n$ 项判别法：通项不趋于 $0$ 则发散
- 比式/根式判别法：极限 $<1$ 绝对收敛，$>1$ 发散，$=1$ 无效
- 交错级数：项递减趋于 $0$ 则收敛；绝对收敛 $\Rightarrow$ 收敛

## 泰勒级数

- $T_n(x)=\sum_{k=0}^n\dfrac{f^{(k)}(a)}{k!}(x-a)^k$；拉格朗日余项 $R_n(x)=\dfrac{f^{(n+1)}(c)}{(n+1)!}(x-a)^{n+1}$
- $e^x=\sum_{n=0}^\infty\dfrac{x^n}{n!}$（全体实数）
- $\sin x=\sum_{n=0}^\infty(-1)^n\dfrac{x^{2n+1}}{(2n+1)!}$；$\cos x=\sum_{n=0}^\infty(-1)^n\dfrac{x^{2n}}{(2n)!}$
- $\dfrac{1}{1-x}=\sum_{n=0}^\infty x^n$（$|x|<1$）
- 新级数合成：代换、逐项求导、逐项积分、加减乘除（除法用长除法思想）

## 参数方程与极坐标

- 切线斜率：$\dfrac{dy}{dx}=\dfrac{dy/dt}{dx/dt}$
- 参数弧长：$\int\sqrt{\left(\frac{dx}{dt}\right)^2+\left(\frac{dy}{dt}\right)^2}\,dt$
- 极坐标面积：$A=\dfrac12\int r^2\,d\theta$；极坐标弧长：$\int\sqrt{r^2+\left(\frac{dr}{d\theta}\right)^2}\,d\theta$

## 复数

- 欧拉公式：$e^{i\theta}=\cos\theta+i\sin\theta$；棣莫弗定理：$(\cos\theta+i\sin\theta)^n=\cos n\theta+i\sin n\theta$
- $z^n=w$ 有 $n$ 个根：$r^{1/n}e^{i(\theta+2k\pi)/n}$，$k=0,\dots,n-1$，均匀分布在圆上

## 体积、弧长、表面积

- 圆盘法：$V=\pi\int R^2\,dx$；垫圈法：$V=\pi\int(R^2-r^2)\,dx$
- 壳法：$V=2\pi\int(\text{半径})(\text{高度})\,dx$（平行于轴切片用壳，垂直于轴切片用圆盘）
- 弧长：$L=\int\sqrt{1+(y')^2}\,dx$；旋转表面积：$S=2\pi\int(\text{半径})\sqrt{1+(y')^2}\,dx$

## 微分方程

- 可分离变量：$\frac{dy}{dx}=g(x)h(y)\Rightarrow\int\frac{dy}{h(y)}=\int g(x)\,dx$
- 一阶线性 $y'+P(x)y=Q(x)$：积分因子 $\mu=e^{\int P(x)\,dx}$，$\frac{d}{dx}(\mu y)=\mu Q$
- 二阶常系数齐次 $ay''+by'+cy=0$：特征方程 $ar^2+br+c=0$
  - 两相异实根 $r_1,r_2$：$y=C_1e^{r_1x}+C_2e^{r_2x}$
  - 重根 $r$：$y=(C_1+C_2x)e^{rx}$
  - 共轭复根 $\alpha\pm\beta i$：$y=e^{\alpha x}(C_1\cos\beta x+C_2\sin\beta x)$
- 非齐次：$y=y_H+y_P$，待定系数法设 $y_P$；与 $y_H$ 冲突时乘 $x$

## 数值积分

- 梯形法则：$T_n=\dfrac{\Delta x}{2}(f_0+2f_1+\cdots+2f_{n-1}+f_n)$
- 辛普森法则（$n$ 为偶数）：$S_n=\dfrac{\Delta x}{3}(f_0+4f_1+2f_2+\cdots+4f_{n-1}+f_n)$
- 误差界：$|E_T|\le\dfrac{K(b-a)^3}{12n^2}$，$|E_S|\le\dfrac{K(b-a)^5}{180n^4}$

## 线性化与牛顿法

- 线性化：$L(x)=f(a)+f'(a)(x-a)$；微分：$dy=f'(x)\,dx$
- 牛顿法：$x_{n+1}=x_n-\dfrac{f(x_n)}{f'(x_n)}$

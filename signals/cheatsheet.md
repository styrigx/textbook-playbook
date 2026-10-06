# 全书公式速查

《信号与系统》（Oppenheim）核心公式一览：四种傅里叶分析的性质对照、基本变换对、拉普拉斯/z 变换表、LTI 系统判定条件。查阅用，不求推导。

## 一、四种傅里叶分析对照

| | 连续时间周期 (CTFS) | 连续时间非周期 (CTFT) | 离散时间周期 (DTFS) | 离散时间非周期 (DTFT) |
|---|---|---|---|---|
| 时域 | $x(t)=\sum_{k=-\infty}^{\infty}a_k e^{jk\omega_0 t}$ | $x(t)=\frac{1}{2\pi}\int_{-\infty}^{\infty}X(j\omega)e^{j\omega t}d\omega$ | $x[n]=\sum_{k=\langle N\rangle}a_k e^{jk\omega_0 n}$ | $x[n]=\frac{1}{2\pi}\int_{2\pi}X(e^{j\omega})e^{j\omega n}d\omega$ |
| 频域 | $a_k=\frac{1}{T}\int_T x(t)e^{-jk\omega_0 t}dt$ | $X(j\omega)=\int_{-\infty}^{\infty}x(t)e^{-j\omega t}dt$ | $a_k=\frac{1}{N}\sum_{n=\langle N\rangle}x[n]e^{-jk\omega_0 n}$ | $X(e^{j\omega})=\sum_{n=-\infty}^{\infty}x[n]e^{-j\omega n}$ |
| 频率变量 | 离散 $k\omega_0$，$\omega_0=2\pi/T$ | 连续 $\omega$ | 离散 $k\omega_0$，$\omega_0=2\pi/N$，$a_{k+N}=a_k$ | 连续 $\omega$，$X(e^{j\omega})$ 以 $2\pi$ 为周期 |
| 谐波个数 | 无穷多 | — | 只有 $N$ 个独立谐波 | — |

## 二、傅里叶级数性质表

连续时间（周期 $T$，$\omega_0=2\pi/T$）：

| 时域 $x(t)$ | 频域 $a_k$ |
|---|---|
| $Ax(t)+By(t)$ | $Aa_k+Bb_k$ |
| $x(t-t_0)$ | $a_k e^{-jk\omega_0 t_0}$ |
| $x(-t)$ | $a_{-k}$ |
| $x(\alpha t)$（周期 $T/\|\alpha\|$） | $a_k$（系数不变） |
| $x(t)y(t)$ | $T\sum_{l=-\infty}^{\infty}a_l b_{k-l}$ |
| $x^*(t)$ | $a_{-k}^*$ |
| $\frac{dx}{dt}$ | $jk\omega_0 a_k$ |
| $\int_{-\infty}^{t}x(\tau)d\tau$（要求 $a_0=0$） | $\frac{1}{jk\omega_0}a_k$ |
| 帕斯瓦尔 | $\frac{1}{T}\int_T\|x(t)\|^2dt=\sum_{k=-\infty}^{\infty}\|a_k\|^2$ |

离散时间（周期 $N$，$\omega_0=2\pi/N$）：

| 时域 $x[n]$ | 频域 $a_k$ |
|---|---|
| $Ax[n]+By[n]$ | $Aa_k+Bb_k$ |
| $x[n-n_0]$ | $a_k e^{-jk\omega_0 n_0}$ |
| $x[-n]$ | $a_{-k}$ |
| $x[n]y[n]$ | $N\sum_{l=\langle N\rangle}a_l b_{k-l}$ |
| $x^*[n]$ | $a_{-k}^*$ |
| $x[n]-x[n-1]$（一次差分） | $(1-e^{-jk\omega_0})a_k$ |
| 帕斯瓦尔 | $\frac{1}{N}\sum_{n=\langle N\rangle}\|x[n]\|^2=\sum_{k=\langle N\rangle}\|a_k\|^2$ |

## 三、傅里叶变换性质表

连续时间傅里叶变换：

| 时域 $x(t)$ | 频域 $X(j\omega)$ |
|---|---|
| $Ax(t)+By(t)$ | $AX(j\omega)+BY(j\omega)$ |
| $x(t-t_0)$ | $e^{-j\omega t_0}X(j\omega)$ |
| $e^{j\omega_0 t}x(t)$（频移） | $X(j(\omega-\omega_0))$ |
| $x^*(t)$ | $X^*(-j\omega)$ |
| $x(-t)$ | $X(-j\omega)$ |
| $x(at)$ | $\frac{1}{\|a\|}X(j\omega/a)$ |
| $\frac{d^n x}{dt^n}$ | $(j\omega)^n X(j\omega)$ |
| $\int_{-\infty}^{t}x(\tau)d\tau$ | $\frac{1}{j\omega}X(j\omega)+\pi X(0)\delta(\omega)$ |
| $-tx(t)$（对偶的频域微分） | $\frac{dX(j\omega)}{d\omega}$ |
| $X(jt)$（对偶性） | $2\pi x(-j\omega)$ |
| $x(t)*h(t)$（卷积） | $X(j\omega)H(j\omega)$ |
| $x(t)w(t)$（相乘） | $\frac{1}{2\pi}\int_{-\infty}^{\infty}X(j\theta)W(j(\omega-\theta))d\theta$ |
| 帕斯瓦尔 | $\int_{-\infty}^{\infty}\|x(t)\|^2dt=\frac{1}{2\pi}\int_{-\infty}^{\infty}\|X(j\omega)\|^2d\omega$ |

离散时间傅里叶变换：

| 时域 $x[n]$ | 频域 $X(e^{j\omega})$ |
|---|---|
| $Ax[n]+By[n]$ | $AX(e^{j\omega})+BY(e^{j\omega})$ |
| $x[n-n_0]$ | $e^{-j\omega n_0}X(e^{j\omega})$ |
| $e^{j\omega_0 n}x[n]$（频移） | $X(e^{j(\omega-\omega_0)})$ |
| $x^*[n]$ | $X^*(e^{-j\omega})$ |
| $x[-n]$ | $X(e^{-j\omega})$ |
| $x[n]-x[n-1]$（差分） | $(1-e^{-j\omega})X(e^{j\omega})$ |
| $\sum_{k=-\infty}^{n}x[k]$（累加） | $\frac{1}{1-e^{-j\omega}}X(e^{j\omega})+\pi X(e^{j0})\sum_{k}\delta(\omega-2\pi k)$ |
| $nx[n]$（频域微分） | $j\frac{dX(e^{j\omega})}{d\omega}$ |
| $x_{(k)}[n]$（$k$ 倍时域扩展/内插零） | $X(e^{jk\omega})$ |
| $x[n]*h[n]$（卷积和） | $X(e^{j\omega})H(e^{j\omega})$ |
| $x[n]w[n]$（相乘） | $\frac{1}{2\pi}\int_{2\pi}X(e^{j\theta})W(e^{j(\omega-\theta)})d\theta$ |
| 帕斯瓦尔 | $\sum_{n=-\infty}^{\infty}\|x[n]\|^2=\frac{1}{2\pi}\int_{2\pi}\|X(e^{j\omega})\|^2d\omega$ |

## 四、基本傅里叶变换对

连续时间：

| $x(t)$ | $X(j\omega)$ |
|---|---|
| $\delta(t)$ | $1$ |
| $1$ | $2\pi\delta(\omega)$ |
| $u(t)$ | $\frac{1}{j\omega}+\pi\delta(\omega)$ |
| $e^{-at}u(t)$，$a>0$ | $\frac{1}{a+j\omega}$ |
| $te^{-at}u(t)$，$a>0$ | $\frac{1}{(a+j\omega)^2}$ |
| $e^{j\omega_0 t}$ | $2\pi\delta(\omega-\omega_0)$ |
| $\cos\omega_0 t$ | $\pi[\delta(\omega-\omega_0)+\delta(\omega+\omega_0)]$ |
| $\sin\omega_0 t$ | $\frac{\pi}{j}[\delta(\omega-\omega_0)-\delta(\omega+\omega_0)]$ |
| 矩形脉冲（$\|t\|<T_1$ 为 1） | $\frac{2\sin\omega T_1}{\omega}$ |
| $\frac{\sin Wt}{\pi t}$ | 矩形（$\|\omega\|<W$ 为 1） |

离散时间：

| $x[n]$ | $X(e^{j\omega})$ |
|---|---|
| $\delta[n]$ | $1$ |
| $1$ | $2\pi\sum_{k=-\infty}^{\infty}\delta(\omega-2\pi k)$ |
| $u[n]$ | $\frac{1}{1-e^{-j\omega}}+\pi\sum_{k}\delta(\omega-2\pi k)$ |
| $a^n u[n]$，$\|a\|<1$ | $\frac{1}{1-ae^{-j\omega}}$ |
| $na^n u[n]$，$\|a\|<1$ | $\frac{ae^{-j\omega}}{(1-ae^{-j\omega})^2}$ |

## 五、拉普拉斯变换

定义：$X(s)=\int_{-\infty}^{\infty}x(t)e^{-st}dt$，$s=\sigma+j\omega$

常用变换对（含 ROC）：

| $x(t)$ | $X(s)$ | ROC |
|---|---|---|
| $\delta(t)$ | $1$ | 全 $s$ 平面 |
| $u(t)$ | $\frac{1}{s}$ | $\mathrm{Re}\{s\}>0$ |
| $-u(-t)$ | $\frac{1}{s}$ | $\mathrm{Re}\{s\}<0$ |
| $e^{-at}u(t)$ | $\frac{1}{s+a}$ | $\mathrm{Re}\{s\}>-a$ |
| $-e^{-at}u(-t)$ | $\frac{1}{s+a}$ | $\mathrm{Re}\{s\}<-a$ |
| $tu(t)$ | $\frac{1}{s^2}$ | $\mathrm{Re}\{s\}>0$ |
| $\frac{t^{n-1}}{(n-1)!}e^{-at}u(t)$ | $\frac{1}{(s+a)^n}$ | $\mathrm{Re}\{s\}>-a$ |
| $e^{-at}\cos(\omega_0 t)u(t)$ | $\frac{s+a}{(s+a)^2+\omega_0^2}$ | $\mathrm{Re}\{s\}>-a$ |
| $e^{-at}\sin(\omega_0 t)u(t)$ | $\frac{\omega_0}{(s+a)^2+\omega_0^2}$ | $\mathrm{Re}\{s\}>-a$ |

主要性质：

| 时域 | $s$ 域 | ROC |
|---|---|---|
| $Ax_1+Bx_2$ | $AX_1+BX_2$ | 至少 $R_1\cap R_2$ |
| $x(t-t_0)$ | $e^{-st_0}X(s)$ | $R$ |
| $e^{s_0 t}x(t)$ | $X(s-s_0)$ | $R+\mathrm{Re}\{s_0\}$ |
| $x(at)$ | $\frac{1}{\|a\|}X(s/a)$ | $aR$ |
| $x^*(t)$ | $X^*(s^*)$ | $R$ |
| $x_1*x_2$ | $X_1X_2$ | 至少 $R_1\cap R_2$ |
| $\frac{dx}{dt}$ | $sX(s)$ | 至少 $R$ |
| $-tx(t)$ | $\frac{dX(s)}{ds}$ | $R$ |
| $\int_{-\infty}^{t}x(\tau)d\tau$ | $\frac{1}{s}X(s)$ | 至少 $R\cap\{\mathrm{Re}\{s\}>0\}$ |

- 初值定理：$\lim_{t\to0^+}x(t)=\lim_{s\to\infty}sX(s)$（要求 $x(t)$ 在 $t=0$ 处无冲激）
- 终值定理：$\lim_{t\to\infty}x(t)=\lim_{s\to0}sX(s)$（要求 $sX(s)$ 除原点外极点全在左半平面，否则不适用）
- 单边拉普拉斯 $\mathcal{L}_u\{x(t)\}=\int_{0^-}^{\infty}x(t)e^{-st}dt$；$\frac{dx}{dt}\leftrightarrow sX_u(s)-x(0^-)$（处理非零初始条件）

ROC 判定口诀：右边信号→最右极点之右；左边信号→最左极点之左；双边→条带；有限长→全平面；有理 ROC 不含极点；含 $j\omega$ 轴 ⟺ 傅里叶变换存在。

## 六、z 变换

定义：$X(z)=\sum_{n=-\infty}^{\infty}x[n]z^{-n}$

常用变换对（含 ROC）：

| $x[n]$ | $X(z)$ | ROC |
|---|---|---|
| $\delta[n]$ | $1$ | 全 $z$ 平面 |
| $u[n]$ | $\frac{1}{1-z^{-1}}=\frac{z}{z-1}$ | $\|z\|>1$ |
| $-u[-n-1]$ | $\frac{1}{1-z^{-1}}$ | $\|z\|<1$ |
| $a^n u[n]$ | $\frac{1}{1-az^{-1}}=\frac{z}{z-a}$ | $\|z\|>\|a\|$ |
| $-a^n u[-n-1]$ | $\frac{1}{1-az^{-1}}$ | $\|z\|<\|a\|$ |
| $na^n u[n]$ | $\frac{az^{-1}}{(1-az^{-1})^2}$ | $\|z\|>\|a\|$ |

主要性质：

| 时域 | $z$ 域 | ROC |
|---|---|---|
| $Ax_1+Bx_2$ | $AX_1+BX_2$ | 至少 $R_1\cap R_2$ |
| $x[n-n_0]$ | $z^{-n_0}X(z)$ | $R$（可能增删 $0$ 或 $\infty$） |
| $a^n x[n]$ | $X(a^{-1}z)$ | $\|a\|R$ |
| $x[-n]$ | $X(z^{-1})$ | $1/R$ |
| $x_{(k)}[n]$（$k$ 倍扩展） | $X(z^k)$ | $R^{1/k}$ |
| $x^*[n]$ | $X^*(z^*)$ | $R$ |
| $x_1*x_2$ | $X_1X_2$ | 至少 $R_1\cap R_2$ |
| $nx[n]$ | $-z\frac{dX(z)}{dz}$ | $R$ |

- 初值定理：$x[0]=\lim_{z\to\infty}X(z)$（要求 $x[n]$ 右边序列）
- 单边 z 变换 $\mathcal{Z}_u\{x[n]\}=\sum_{n=0}^{\infty}x[n]z^{-n}$；右移 $x[n-n_0]\leftrightarrow z^{-n_0}X_u(z)$（$n_0>0$）；解差分方程处理初始条件
- ROC 判定口诀：右边序列→最外极点之外；左边序列→最内极点之内；双边→圆环；有限长→全平面（端点处可能除去 $0$ 或 $\infty$）；含单位圆 ⟺ DTFT 存在

## 七、LTI 系统判定速查

| 判定 | 连续时间（$h(t)$ / $H(s)$） | 离散时间（$h[n]$ / $H(z)$） |
|---|---|---|
| 因果 | $h(t)=0\ (t<0)$；$H(s)$ 的 ROC 为最右极点之右 | $h[n]=0\ (n<0)$；$H(z)$ 的 ROC 为最外极点之外 |
| 稳定（BIBO） | $\int_{-\infty}^{\infty}\|h(t)\|dt<\infty$；ROC 含 $j\omega$ 轴 | $\sum_{n}\|h[n]\|<\infty$；ROC 含单位圆 |
| 因果且稳定 | 全部极点在左半平面 | 全部极点在单位圆内 |
| 无记忆 | $h(t)=c\delta(t)$ | $h[n]=c\delta[n]$ |
| 可逆 | 存在 $h_1$ 使 $h*h_1=\delta$ | 存在 $h_1$ 使 $h*h_1=\delta[n]$ |

- 微分方程系统：$H(s)=\frac{\sum_{k=0}^{M}b_k s^k}{\sum_{k=0}^{N}a_k s^k}$（因果要求 $M\le N$）
- 差分方程系统：$H(z)=\frac{\sum_{k=0}^{M}b_k z^{-k}}{\sum_{k=0}^{N}a_k z^{-k}}$
- 频率响应：$H(j\omega)=H(s)|_{s=j\omega}$；$H(e^{j\omega})=H(z)|_{z=e^{j\omega}}$（要求 ROC 包含相应曲线）
- 互联：级联 $H_1H_2$；并联 $H_1+H_2$；反馈（负反馈约定）$\frac{H_1}{1+H_1H_2}$；闭环 $Q=\frac{G}{1+GH}$

## 八、常用基础公式

- 欧拉公式：$e^{j\theta}=\cos\theta+j\sin\theta$；$\cos\theta=\frac{e^{j\theta}+e^{-j\theta}}{2}$，$\sin\theta=\frac{e^{j\theta}-e^{-j\theta}}{2j}$
- 冲激筛选：$\int_{-\infty}^{\infty}x(t)\delta(t-t_0)dt=x(t_0)$；$\sum_n x[n]\delta[n-n_0]=x[n_0]$
- $\delta(at)=\frac{1}{|a|}\delta(t)$；$\delta(t)=\delta(-t)$（偶函数）
- 卷积恒等元：$x(t)*\delta(t)=x(t)$；$x[n]*\delta[n]=x[n]$
- $x(t)*\delta(t-t_0)=x(t-t_0)$；$x(t)*\delta'(t)=\frac{dx(t)}{dt}$
- 采样定理：带限 $\omega_M$，$\omega_s>2\omega_M$ 无混叠；重建 $x(t)=\sum_n x(nT)\frac{\sin\omega_c(t-nT)}{\pi(t-nT)}$
- 奈奎斯特率 $=2\omega_M$
- 根轨迹角判据（$K>0$）：$\angle G(s)H(s)=(2k+1)\pi$；奈奎斯特判据：$Z=N+P$

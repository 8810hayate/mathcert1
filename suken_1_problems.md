# 数学検定1級（一次試験：計算技能）模擬問題・解答解説

数学検定1級の一次試験（計算技能）では、大学基礎課程レベル（線形代数、微積分、微分方程式、確率・統計など）の正確で素早い計算力が求められます。本問題集では、頻出パターンを踏まえた4つの模擬問題と、詳細な解答解説を提供します。

---

## 模擬問題一覧

### 【問題1】微積分学（重積分）
次の2重積分を計算せよ。
$$J = \iint_{\mathbb{R}^2} e^{-(x^2 + xy + y^2)} \,dx\,dy$$

---

### 【問題2】線形代数（行列式）
次の $n$ 次正方行列の行列式 $D_n$ を $n$ を用いて表せ。
$$D_n = \begin{vmatrix}
3 & 2 & 0 & 0 & \dots & 0 & 0 \\
1 & 3 & 2 & 0 & \dots & 0 & 0 \\
0 & 1 & 3 & 2 & \dots & 0 & 0 \\
\vdots & \vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & 0 & \dots & 3 & 2 \\
0 & 0 & 0 & 0 & \dots & 1 & 3
\end{vmatrix}$$

---

### 【問題3】微分方程式
次の微分方程式の初期値問題を解け。
$$x \frac{dy}{dx} - y = x^2 \cos x \quad (x > 0), \quad y(\pi) = 0$$

---

### 【問題4】確率・統計 / 級数
表が出る確率が $\frac{1}{2}$ である歪みのない硬貨を、表が2回出るまで投げ続ける。このとき、硬貨を投げる回数 $X$ の期待値 $E[X]$ を求めよ。

---
---

## 解答・解説

### 【問題1】微積分学（重積分）の解説

#### 解答
$$J = \frac{2\sqrt{3}}{3}\pi$$

#### 解説
被積分関数の指数部分にある 2次形式 $x^2 + xy + y^2$ を、変数変換によって対角化（直交変換）します。

2次形式を次のように行列で表します。
$$x^2 + xy + y^2 = \begin{pmatrix} x & y \end{pmatrix} A \begin{pmatrix} x \\ y \end{pmatrix}, \quad A = \begin{pmatrix} 1 & 1/2 \\ 1/2 & 1 \end{pmatrix}$$

対称行列 $A$ の固有値を求めます。固有多項式は、
$$\det(A - \lambda I) = (1-\lambda)^2 - \frac{1}{4} = 0$$
$$\lambda^2 - 2\lambda + \frac{3}{4} = 0 \implies \left(\lambda - \frac{3}{2}\right)\left(\lambda - \frac{1}{2}\right) = 0$$
よって、固有値は $\lambda_1 = \frac{3}{2}, \lambda_2 = \frac{1}{2}$ です。

対称行列は直交行列 $P$ を用いて対角化できます。
$$\begin{pmatrix} x \\ y \end{pmatrix} = P \begin{pmatrix} u \\ v \end{pmatrix}$$
直交変換において、ヤコビアン（Jacobian）の絶対値は $1$ になります（$|J| = |\det P| = 1$）。また、積分領域 $\mathbb{R}^2$ は $uv$ 平面でも全平面 $\mathbb{R}^2$ のままです。

したがって、積分 $J$ は以下のように変換されます。
$$J = \iint_{\mathbb{R}^2} e^{-\left(\frac{3}{2}u^2 + \frac{1}{2}v^2\right)} \,du\,dv$$

これは $u$ と $v$ に関して独立な積分の積に分解できます。
$$J = \left( \int_{-\infty}^{\infty} e^{-\frac{3}{2}u^2} \,du \right) \left( \int_{-\infty}^{\infty} e^{-\frac{1}{2}v^2} \,dv \right)$$

ここで、ガウス積分公式 $\int_{-\infty}^{\infty} e^{-a t^2} \,dt = \sqrt{\frac{\pi}{a}}$ を適用します。
* $u$ の積分: $\sqrt{\frac{\pi}{3/2}} = \sqrt{\frac{2\pi}{3}}$
* $v$ の積分: $\sqrt{\frac{\pi}{1/2}} = \sqrt{2\pi}$

よって、求める積分値は以下の通りです。
$$J = \sqrt{\frac{2\pi}{3}} \cdot \sqrt{2\pi} = \frac{2\pi}{\sqrt{3}} = \frac{2\sqrt{3}}{3}\pi$$

---

### 【問題2】線形代数（行列式）の解説

#### 解答
$$D_n = 2^{n+1} - 1$$

#### 解説
第1行に関して余因子展開を行い、隣接3項間の漸化式を導きます。

第1行で展開すると、
$$D_n = 3 D_{n-1} - 2 \begin{vmatrix}
1 & 2 & 0 & \dots & 0 \\
0 & 3 & 2 & \dots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \dots & 3
\end{vmatrix}_{(n-1)\text{次}}$$

右辺第2項の行列式の第1列に関してさらに展開すると、値は $1 \cdot D_{n-2}$ となります。したがって、次の漸化式が得られます。
$$D_n = 3 D_{n-1} - 2 D_{n-2} \quad (n \ge 3)$$

初期条件（$n=1, 2$）を求めます。
* $D_1 = |3| = 3$
* $D_2 = \begin{vmatrix} 3 & 2 \\ 1 & 3 \end{vmatrix} = 9 - 2 = 7$

この漸化式 $D_n - 3 D_{n-1} + 2 D_{n-2} = 0$ の特性方程式は、
$$t^2 - 3t + 2 = 0 \implies (t-1)(t-2) = 0$$
よって、特性根は $t = 1, 2$ です。
一般解は次のように置くことができます。
$$D_n = C_1 \cdot 1^n + C_2 \cdot 2^n = C_1 + C_2 2^n$$

初期条件を代入して定数 $C_1, C_2$ を決定します。
1. $n=1$ のとき： $C_1 + 2C_2 = 3$
2. $n=2$ のとき： $C_1 + 4C_2 = 7$

下式から上式を引くと、
$$2C_2 = 4 \implies C_2 = 2$$
これを代入して、
$$C_1 + 4 = 3 \implies C_1 = -1$$

したがって、求める行列式は次のようになります。
$$D_n = -1 + 2 \cdot 2^n = 2^{n+1} - 1$$

---

### 【問題3】微分方程式の解説

#### 解答
$$y = x \sin x$$

#### 解説
与えられた方程式は1階線形常微分方程式です。
$$x \frac{dy}{dx} - y = x^2 \cos x$$

$x > 0$ であるため、両辺を $x$ で割って標準形にします。
$$\frac{dy}{dx} - \frac{1}{x} y = x \cos x$$

この微分方程式を解くために、積分因子（integrating factor） $I(x)$ を用います。
$$I(x) = e^{\int -\frac{1}{x} \,dx} = e^{-\log x} = \frac{1}{x}$$

方程式の両辺に $I(x) = \frac{1}{x}$ を掛けます。
$$\frac{1}{x} \frac{dy}{dx} - \frac{1}{x^2} y = \cos x$$

左辺は積の微分公式より $\frac{d}{dx} \left( \frac{y}{x} \right)$ とまとめられます。
$$\frac{d}{dx} \left( \frac{y}{x} \right) = \cos x$$

両辺を $x$ で積分します。
$$\frac{y}{x} = \int \cos x \,dx = \sin x + C \quad (C\text{は任意定数})$$
$$y = x(\sin x + C)$$

初期条件 $y(\pi) = 0$ を用いて定数 $C$ を求めます。
$$0 = \pi(\sin \pi + C) = \pi(0 + C) \implies C = 0$$

したがって、求める特解は次の通りです。
$$y = x \sin x$$

---

### 【問題4】確率・統計 / 級数の解説

#### 解答
$$E[X] = 4$$

#### 解説
本問は確率変数の期待値計算をベキ級数の微分を用いて解く問題です。

確率変数 $X$（2回目の表が出るまでの総試行回数）が値 $k$（$k \ge 2$）をとるのは、「最初の $k-1$ 回の中でちょうど1回表が出て、かつ $k$ 回目に表が出る」ときです。
したがって、その確率質量関数 $P(X=k)$ は次のように表されます。
$$P(X=k) = \binom{k-1}{1} \left(\frac{1}{2}\right)^1 \left(\frac{1}{2}\right)^{k-2} \cdot \frac{1}{2} = (k-1)\left(\frac{1}{2}\right)^k$$
（これは負の二項分布 $NB(2, 1/2)$ に従います。）

期待値 $E[X]$ は定義より、
$$E[X] = \sum_{k=2}^{\infty} k \cdot P(X=k) = \sum_{k=2}^{\infty} k(k-1)\left(\frac{1}{2}\right)^k$$

この無限級数を求めるために、次の幾何級数を考えます（$|x| < 1$）。
$$f(x) = \sum_{k=0}^{\infty} x^k = \frac{1}{1-x}$$

両辺を $x$ で1回微分します。
$$f'(x) = \sum_{k=1}^{\infty} k x^{k-1} = \frac{1}{(1-x)^2}$$

さらにもう1回微分します。
$$f''(x) = \sum_{k=2}^{\infty} k(k-1) x^{k-2} = \frac{2}{(1-x)^3}$$

両辺に $x^2$ を掛けます。
$$\sum_{k=2}^{\infty} k(k-1) x^k = \frac{2x^2}{(1-x)^3}$$

ここで $x = \frac{1}{2}$ を代入すると、求める期待値 $E[X]$ が得られます。
$$E[X] = \frac{2 \left(\frac{1}{2}\right)^2}{\left(1 - \frac{1}{2}\right)^3} = \frac{2 \cdot \frac{1}{4}}{\frac{1}{8}} = \frac{1/2}{1/8} = 4$$

したがって、期待値は **4** （回）となります。

# 数学検定1級 合格のための「極限・計算・証明」究極ガイド

数学検定1級（一次試験：計算技能 / 二次試験：数理技能）で出題される全ての主要分野を徹底的にカバーした、合計23問の精選問題・解答解説集です。各分野における頻出パターンと、合格に必要な解法テクニックを詳細に解説します。

---

## 目次・網羅範囲

* **I. 線形代数 (Linear Algebra)**
  * 【問題1-1】$n$次ヴァンデルモンドの行列式（証明と帰納法）
  * 【問題1-2】内積空間と多項式のグラム・シュミットの直交化（ルジャンドル多項式）
  * 【問題1-3】行列の指数関数 $e^{tA}$ と連立線形微分方程式の解法
  * 【問題1-4】2次形式と正定値性（シルベスターの基準）
* **II. 微分積分学 (Calculus)**
  * 【問題2-1】マクローリン展開を利用した極限値の算出
  * 【問題2-2】置換積分とガンマ関数・広義積分
  * 【問題2-3】重積分における極座標変換（ヤコビアンの利用）
  * 【問題2-4】フーリエ級数展開と無限級数の和（バーゼル問題）
* **III. 微分方程式 (Differential Equations)**
  * 【問題3-1】完全微分方程式の判定と解法（ポテンシャル関数）
  * 【問題3-2】高階線形常微分方程式（特性方程式の三重根と特解）
  * 【問題3-3】ベルヌーイの微分方程式
* **IV. 複素解析 (Complex Analysis)**
  * 【問題4-1】コーシーの積分公式を用いた周回積分
  * 【問題4-2】留数定理を用いた三角関数・指数関数を含む実無限積分の算出
  * 【問題4-3】複素関数のローラン展開
* **V. ベクトル解析 (Vector Calculus)**
  * 【問題5-1】ストークスの定理を用いた線積分から面積分への変換
  * 【問題5-2】ガウスの発散定理を用いた閉曲面上の面積分の計算
* **VI. 幾何・微分幾何 (Differential Geometry)**
  * 【問題6-1】空間曲線（常螺旋）の弧長・曲率・捩率の算出
* **VII. 代数学・整数論 (Algebra & Number Theory)**
  * 【問題7-1】中国式剰余定理（CRT）による連立合同式の解法
  * 【問題7-2】群の準同型写像における核（Kernel）が正規部分群であることの証明
  * 【問題7-3】多項式環の剰余環と体の同型
* **VIII. 確率・統計 (Probability & Statistics)**
  * 【問題8-1】ベイズの定理（条件付き確率の応用問題）
  * 【問題8-2】ポアソン分布の最尤推定量（MLE）の導出と不偏性の証明
  * 【問題8-3】カイ二乗適合度検定による仮説検定
  * 【問題8-4】2次元連続型確率変数の同時分布・周辺分布・共分散

---
---

## I. 線形代数 (Linear Algebra)

### 【問題1-1】$n$次ヴァンデルモンドの行列式
実数 $x_1, x_2, \dots, x_n$ に対し、次の $n$ 次ヴァンデルモンド（Vandermonde）の行列式 $V_n$ の因数分解公式を証明せよ。
$$V_n = \begin{vmatrix}
1 & x_1 & x_1^2 & \dots & x_1^{n-1} \\
1 & x_2 & x_2^2 & \dots & x_2^{n-1} \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
1 & x_n & x_n^2 & \dots & x_n^{n-1}
\end{vmatrix} = \prod_{1 \le i < j \le n} (x_j - x_i)$$

#### 【解答・解説】
数学的帰納法を用いて証明します。

1. **$n=2$ のとき**
   $$V_2 = \begin{vmatrix} 1 & x_1 \\ 1 & x_2 \end{vmatrix} = x_2 - x_1$$
   これは公式 $\prod_{1 \le i < j \le 2} (x_j - x_i) = x_2 - x_1$ と一致するため、成り立ちます。

2. **$n-1$ のとき成立すると仮定し、$n$ のときを考える**
   行列式 $V_n$ に対して列基本変形を行います。右の列から順に、隣の列の $x_1$ 倍を引いていきます。具体的には、第 $k$ 列から第 $k-1$ 列の $x_1$ 倍を引く操作を $k = n, n-1, \dots, 2$ の順に行います。
   $$V_n = \begin{vmatrix}
   1 & 0 & 0 & \dots & 0 \\
   1 & x_2 - x_1 & x_2(x_2 - x_1) & \dots & x_2^{n-2}(x_2 - x_1) \\
   \vdots & \vdots & \vdots & \ddots & \vdots \\
   1 & x_n - x_1 & x_n(x_n - x_1) & \dots & x_n^{n-2}(x_n - x_1)
   \end{vmatrix}$$
   第1行に関して展開（余因子展開）すると、次のように $(n-1)$ 次行列式に帰着されます。
   $$V_n = \begin{vmatrix}
   x_2 - x_1 & x_2(x_2 - x_1) & \dots & x_2^{n-2}(x_2 - x_1) \\
   \vdots & \vdots & \ddots & \vdots \\
   x_n - x_1 & x_n(x_n - x_1) & \dots & x_n^{n-2}(x_n - x_1)
   \end{vmatrix}$$
   各行から共通因数 $(x_k - x_1)$ （$k=2, \dots, n$）を括り出します。
   $$V_n = (x_2 - x_1)(x_3 - x_1)\dots(x_n - x_1) \begin{vmatrix}
   1 & x_2 & \dots & x_2^{n-2} \\
   \vdots & \vdots & \ddots & \vdots \\
   1 & x_n & \dots & x_n^{n-2}
   \end{vmatrix}$$
   右側の行列式は、変数 $x_2, \dots, x_n$ に関する $(n-1)$ 次のヴァンデルモンド行列式 $V_{n-1}$ です。
   帰納法の仮定より、
   $$V_{n-1} = \prod_{2 \le i < j \le n} (x_j - x_i)$$
   であるため、
   $$V_n = \left( \prod_{j=2}^n (x_j - x_1) \right) \prod_{2 \le i < j \le n} (x_j - x_i) = \prod_{1 \le i < j \le n} (x_j - x_i)$$
   が得られます。これにより、$n$ のときも成立することが示されました。 (証明終)

---

### 【問題1-2】内積空間と多項式のグラム・シュミットの直交化
実係数高々2次の多項式空間 $P_2(\mathbb{R})$ において、内積を以下のように定義する。
$$\langle f, g \rangle = \int_{-1}^1 f(x)g(x) \,dx$$
このとき、標準的な基底 $\{v_0, v_1, v_2\} = \{1, x, x^2\}$ をグラム・シュミットの直交化法により正規直交化せよ。

#### 【解答・解説】
正規直交基底 $\{e_0, e_1, e_2\}$ を順に構築します。

1. **$e_0$ の決定**
   $$u_0 = v_0 = 1$$
   $$\|u_0\|^2 = \langle u_0, u_0 \rangle = \int_{-1}^1 1^2 \,dx = 2 \implies \|u_0\| = \sqrt{2}$$
   $$e_0 = \frac{u_0}{\|u_0\|} = \frac{1}{\sqrt{2}}$$

2. **$e_1$ の決定**
   $$u_1 = v_1 - \langle v_1, e_0 \rangle e_0$$
   ここで、 $\langle v_1, e_0 \rangle = \int_{-1}^1 x \cdot \frac{1}{\sqrt{2}} \,dx = 0$ （奇関数の積分）であるため、
   $$u_1 = v_1 = x$$
   $$\|u_1\|^2 = \int_{-1}^1 x^2 \,dx = \left[ \frac{x^3}{3} \right]_{-1}^1 = \frac{2}{3} \implies \|u_1\| = \sqrt{\frac{2}{3}}$$
   $$e_1 = \frac{u_1}{\|u_1\|} = \sqrt{\frac{3}{2}} x$$

3. **$e_2$ の決定**
   $$u_2 = v_2 - \langle v_2, e_0 \rangle e_0 - \langle v_2, e_1 \rangle e_1$$
   内積をそれぞれ計算します。
   * $\langle v_2, e_0 \rangle = \int_{-1}^1 x^2 \cdot \frac{1}{\sqrt{2}} \,dx = \frac{1}{\sqrt{2}} \left[ \frac{x^3}{3} \right]_{-1}^1 = \frac{\sqrt{2}}{3}$
   * $\langle v_2, e_1 \rangle = \int_{-1}^1 x^2 \cdot \sqrt{\frac{3}{2}} x \,dx = 0$ （奇関数の積分）
   したがって、
   $$u_2 = x^2 - \left(\frac{\sqrt{2}}{3}\right) \left(\frac{1}{\sqrt{2}}\right) = x^2 - \frac{1}{3}$$
   このノルムを求めます。
   $$\|u_2\|^2 = \int_{-1}^1 \left(x^2 - \frac{1}{3}\right)^2 \,dx = \int_{-1}^1 \left(x^4 - \frac{2}{3}x^2 + \frac{1}{9}\right) \,dx$$
   $$= \left[ \frac{x^5}{5} - \frac{2}{9}x^3 + \frac{x}{9} \right]_{-1}^1 = 2 \left( \frac{1}{5} - \frac{2}{9} + \frac{1}{9} \right) = 2 \left( \frac{9-5}{45} \right) = \frac{8}{45}$$
   よって、 $\|u_2\| = \sqrt{\frac{8}{45}} = \frac{2\sqrt{2}}{3\sqrt{5}}$。
   $$e_2 = \frac{u_2}{\|u_2\|} = \frac{3\sqrt{5}}{2\sqrt{2}} \left(x^2 - \frac{1}{3}\right) = \sqrt{\frac{5}{2}} \left( \frac{3x^2 - 1}{2} \right)$$

#### 【結果】
正規直交基底は以下の通りです。（これらはルジャンドル多項式を正規化したものです。）
$$e_0 = \frac{1}{\sqrt{2}}, \quad e_1 = \sqrt{\frac{3}{2}} x, \quad e_2 = \sqrt{\frac{5}{2}} \left(\frac{3x^2-1}{2}\right)$$

---

### 【問題1-3】行列の指数関数 $e^{tA}$
行列 $A = \begin{pmatrix} 0 & 1 \\ -2 & 3 \end{pmatrix}$ に対し、行列の指数関数 $e^{tA}$ を計算し、初期値問題 $\frac{d\mathbf{x}}{dt} = A\mathbf{x}, \; \mathbf{x}(0) = \begin{pmatrix} x_0 \\ y_0 \end{pmatrix}$ の解を求めよ。

#### 【解答・解説】
1. **$A$ の対角化**
   固有多項式は $\det(A - \lambda I) = \lambda^2 - 3\lambda + 2 = (\lambda - 1)(\lambda - 2) = 0$。
   固有値は $\lambda_1 = 1, \lambda_2 = 2$ です。
   * $\lambda = 1$ の固有ベクトル: $A - I = \begin{pmatrix} -1 & 1 \\ -2 & 2 \end{pmatrix} \implies \mathbf{p}_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$
   * $\lambda = 2$ の固有ベクトル: $A - 2I = \begin{pmatrix} -2 & 1 \\ -2 & 1 \end{pmatrix} \implies \mathbf{p}_2 = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$
   直交化行列 $P$ とその逆行列 $P^{-1}$ を定義します。
   $$P = \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix} \implies P^{-1} = \begin{pmatrix} 2 & -1 \\ -1 & 1 \end{pmatrix}$$
   これにより $P^{-1}AP = \begin{pmatrix} 1 & 0 \\ 0 & 2 \end{pmatrix} = D$ と対角化できます。

2. **$e^{tA}$ の計算**
   $$e^{tA} = P e^{tD} P^{-1} = P \begin{pmatrix} e^t & 0 \\ 0 & e^{2t} \end{pmatrix} P^{-1}$$
   $$= \begin{pmatrix} 1 & 1 \\ 1 & 2 \end{pmatrix} \begin{pmatrix} e^t & 0 \\ 0 & e^{2t} \end{pmatrix} \begin{pmatrix} 2 & -1 \\ -1 & 1 \end{pmatrix}$$
   $$= \begin{pmatrix} e^t & e^{2t} \\ e^t & 2e^{2t} \end{pmatrix} \begin{pmatrix} 2 & -1 \\ -1 & 1 \end{pmatrix} = \begin{pmatrix} 2e^t - e^{2t} & -e^t + e^{2t} \\ 2e^t - 2e^{2t} & -e^t + 2e^{2t} \end{pmatrix}$$

3. **微分方程式の解**
   連立微分方程式の一般解は $\mathbf{x}(t) = e^{tA} \mathbf{x}(0)$ で与えられます。
   $$\mathbf{x}(t) = \begin{pmatrix} 2e^t - e^{2t} & -e^t + e^{2t} \\ 2e^t - 2e^{2t} & -e^t + 2e^{2t} \end{pmatrix} \begin{pmatrix} x_0 \\ y_0 \end{pmatrix}$$
   すなわち、各成分は以下となります。
   $$\begin{cases}
   x(t) = (2x_0 - y_0)e^t + (y_0 - x_0)e^{2t} \\
   y(t) = (2x_0 - y_0)e^t + 2(y_0 - x_0)e^{2t}
   \end{cases}$$

---

### 【問題1-4】2次形式と正定値性（シルベスターの基準）
実数パラメータ $a$ に対し、3変数の2次形式
$$q(x, y, z) = x^2 + 2axy + y^2 + 2ayz + z^2$$
が正定値（任意の $(x, y, z) \neq (0, 0, 0)$ に対して $q(x, y, z) > 0$）となるような $a$ の値の範囲を求めよ。

#### 【解答・解説】
2次形式の実対称行列による表現と、シルベスターの基準（Sylvester's criterion）を用いて解きます。

1. **実対称行列による表現**
   2次形式 $q(x, y, z)$ は、以下のように対称行列 $A$ を用いて表すことができます。
   $$q(x, y, z) = \begin{pmatrix} x & y & z \end{pmatrix} A \begin{pmatrix} x \\ y \\ z \end{pmatrix}, \quad A = \begin{pmatrix} 1 & a & 0 \\ a & 1 & a \\ 0 & a & 1 \end{pmatrix}$$

2. **シルベスターの基準の適用**
   実対称行列 $A$ が正定値であるための必要十分条件は、**すべての首座小行列式（principal minors）が正**であることです。首座小行列式 $D_1, D_2, D_3$ を順に計算します。
   
   * **1次首座小行列式 $D_1$**
     $$D_1 = |1| = 1 > 0$$
     これは常に正です。
     
   * **2次首座小行列式 $D_2$**
     $$D_2 = \begin{vmatrix} 1 & a \\ a & 1 \end{vmatrix} = 1 - a^2$$
     $D_2 > 0$ となる条件は、
     $$1 - a^2 > 0 \implies a^2 < 1 \implies -1 < a < 1 \quad \cdots \text{(i)}$$
     
   * **3次首座小行列式 $D_3$ （すなわち行列式 $\det A$）**
     サラスの公式または第1行展開を行います。
     $$D_3 = \begin{vmatrix} 1 & a & 0 \\ a & 1 & a \\ 0 & a & 1 \end{vmatrix} = 1(1 - a^2) - a(a - 0) + 0 = 1 - 2a^2$$
     $D_3 > 0$ となる条件は、
     $$1 - 2a^2 > 0 \implies a^2 < \frac{1}{2} \implies -\frac{1}{\sqrt{2}} < a < \frac{1}{\sqrt{2}} \quad \cdots \text{(ii)}$$

3. **共通範囲の決定**
   条件 (i) と (ii) の共通範囲を求めます。
   $-\frac{1}{\sqrt{2}} \approx -0.707$、 $-1$ より大きいため、共通の範囲は以下のようになります。
   $$-\frac{1}{\sqrt{2}} < a < \frac{1}{\sqrt{2}}$$
   したがって、2次形式が正定値となる $a$ の範囲は $-\frac{1}{\sqrt{2}} < a < \frac{1}{\sqrt{2}}$ です。

---
---

## II. 微分積分学 (Calculus)

### 【問題2-1】マクローリン展開と極限
マクローリン展開（Taylor展開）を用いて、次の極限値を求めよ。
$$\lim_{x \to 0} \frac{e^x \sin x - x(1+x)}{x^3}$$

#### 【解答・解説】
分子の関数を $x = 0$ の周りで展開します。$x^3$ までの項を残して評価します。
* $e^x = 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + O(x^4)$
* $\sin x = x - \frac{x^3}{6} + O(x^5)$

これらの積をとります。
$$e^x \sin x = \left( 1 + x + \frac{x^2}{2} + \frac{x^3}{6} + O(x^4) \right) \left( x - \frac{x^3}{6} + O(x^5) \right)$$
$$= x\left(1 + x + \frac{x^2}{2}\right) - \frac{x^3}{6}(1) + O(x^4)$$
$$= x + x^2 + \frac{x^3}{2} - \frac{x^3}{6} + O(x^4) = x + x^2 + \frac{1}{3}x^3 + O(x^4)$$

分子全体を計算します。
$$e^x \sin x - x(1+x) = \left( x + x^2 + \frac{1}{3}x^3 + O(x^4) \right) - (x + x^2) = \frac{1}{3}x^3 + O(x^4)$$

これを極限の式に代入します。
$$\lim_{x \to 0} \frac{\frac{1}{3}x^3 + O(x^4)}{x^3} = \lim_{x \to 0} \left( \frac{1}{3} + O(x) \right) = \frac{1}{3}$$

---

### 【問題2-2】置換積分とガンマ関数
次の広義積分を計算せよ。
$$I = \int_0^{\infty} y^4 e^{-y^2} \,dy$$

#### 【解答・解説】
変数変換を行ってガンマ関数 $\Gamma(s) = \int_0^{\infty} x^{s-1} e^{-x} \,dx$ の形に変形します。
$x = y^2$ とおくと、 $y = \sqrt{x}$ であり、 $dy = \frac{1}{2\sqrt{x}} \,dx$ となります。積分範囲は $y: 0 \to \infty$ に対して $x: 0 \to \infty$ で不変です。

これらを代入します。
$$I = \int_0^{\infty} (\sqrt{x})^4 e^{-x} \left( \frac{1}{2\sqrt{x}} \,dx \right) = \frac{1}{2} \int_0^{\infty} x^{2 - \frac{1}{2}} e^{-x} \,dx = \frac{1}{2} \int_0^{\infty} x^{\frac{3}{2}} e^{-x} \,dx$$
これはガンマ関数を用いて以下のように表せます。
$$I = \frac{1}{2} \Gamma\left(\frac{5}{2}\right)$$

ガンマ関数の基本性質 $\Gamma(s+1) = s\Gamma(s)$ および $\Gamma\left(\frac{1}{2}\right) = \sqrt{\pi}$ を用います。
$$\Gamma\left(\frac{5}{2}\right) = \frac{3}{2} \Gamma\left(\frac{3}{2}\right) = \frac{3}{2} \cdot \frac{1}{2} \Gamma\left(\frac{1}{2}\right) = \frac{3}{4}\sqrt{\pi}$$
したがって、求める積分値は以下となります。
$$I = \frac{1}{2} \cdot \frac{3}{4}\sqrt{\pi} = \frac{3}{8}\sqrt{\pi}$$

---

### 【問題2-3】重積分における極座標変換
次の2重積分を計算せよ。
$$J = \iint_D \sqrt{x^2+y^2} \,dx\,dy, \quad D = \{ (x,y) \in \mathbb{R}^2 \mid x^2+y^2 \le 2x \}$$

#### 【解答・解説】
極座標 $x = r\cos\theta, y = r\sin\theta$ を導入します。ヤコビアンは $r$ です。
領域 $D$ の境界条件 $x^2+y^2 \le 2x$ を極座標で表すと、
$$r^2 \le 2r\cos\theta \implies r \le 2\cos\theta$$
$r \ge 0$ より $\cos\theta \ge 0$ が必要であるため、偏角 $\theta$ の範囲は $-\frac{\pi}{2} \le \theta \le \frac{\pi}{2}$ となります。
よって、積分領域は以下のように表されます。
$$D' = \left\{ (r, \theta) \;\middle|\; -\frac{\pi}{2} \le \theta \le \frac{\pi}{2}, \; 0 \le r \le 2\cos\theta \right\}$$

これを用いて重積分を累次積分に変換します。
$$J = \int_{-\frac{\pi}{2}}^{\frac{\pi}{2}} \int_0^{2\cos\theta} r \cdot r \,dr\,d\theta = \int_{-\frac{\pi}{2}}^{\frac{\pi}{2}} \left[ \frac{r^3}{3} \right]_0^{2\cos\theta} \,d\theta = \frac{8}{3} \int_{-\frac{\pi}{2}}^{\frac{\pi}{2}} \cos^3\theta \,d\theta$$
被積分関数は偶関数なので、
$$J = \frac{16}{3} \int_0^{\frac{\pi}{2}} \cos^3\theta \,d\theta$$
ウォリス（Wallis）の公式 $\int_0^{\frac{\pi}{2}} \cos^3\theta \,d\theta = \frac{2}{3}$ より、
$$J = \frac{16}{3} \cdot \frac{2}{3} = \frac{32}{9}$$

---

### 【問題2-4】フーリエ級数展開と無限級数の和（バーゼル問題）
1. 区間 $[-\pi, \pi]$ で定義された関数 $f(x) = x^2$ のフーリエ級数展開を求めよ。
2. その結果を利用して、無限級数の和（バーゼル問題）の公式を示せ。
$$\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}$$

#### 【解答・解説】
1. **フーリエ級数展開の計算**
   関数 $f(x) = x^2$ は偶関数なので、フーリエ展開の正弦成分（sin成分）の係数 $b_n$ はすべて $0$ となります。したがって、フーリエ展開は余弦級数（cos級数）の形になります。
   $$f(x) \sim \frac{a_0}{2} + \sum_{n=1}^{\infty} a_n \cos(nx)$$
   
   * **$a_0$ の計算**
     $$a_0 = \frac{1}{\pi} \int_{-\pi}^{\pi} x^2 \,dx = \frac{2}{\pi} \int_0^{\pi} x^2 \,dx = \frac{2}{\pi} \left[ \frac{x^3}{3} \right]_0^{\pi} = \frac{2\pi^2}{3}$$
     したがって、定数項は $\frac{a_0}{2} = \frac{\pi^2}{3}$ です。
     
   * **$a_n$ （$n \ge 1$）の計算**
     部分積分を2回行います。
     $$a_n = \frac{1}{\pi} \int_{-\pi}^{\pi} x^2 \cos(nx) \,dx = \frac{2}{\pi} \int_0^{\pi} x^2 \cos(nx) \,dx$$
     $$\int_0^{\pi} x^2 \cos(nx) \,dx = \left[ x^2 \frac{\sin(nx)}{n} \right]_0^{\pi} - \int_0^{\pi} 2x \frac{\sin(nx)}{n} \,dx = 0 - \frac{2}{n} \int_0^{\pi} x \sin(nx) \,dx$$
     さらに部分積分します。
     $$\int_0^{\pi} x \sin(nx) \,dx = \left[ x \frac{-\cos(nx)}{n} \right]_0^{\pi} - \int_0^{\pi} \frac{-\cos(nx)}{n} \,dx = -\frac{\pi \cos(n\pi)}{n} + \left[ \frac{\sin(nx)}{n^2} \right]_0^{\pi} = -\frac{\pi (-1)^n}{n}$$
     したがって、
     $$\int_0^{\pi} x^2 \cos(nx) \,dx = -\frac{2}{n} \left( -\frac{\pi (-1)^n}{n} \right) = \frac{2\pi (-1)^n}{n^2}$$
     これを $a_n$ の式に代入します。
     $$a_n = \frac{2}{\pi} \left( \frac{2\pi (-1)^n}{n^2} \right) = \frac{4(-1)^n}{n^2}$$
     
   以上より、 $f(x) = x^2$ のフーリエ級数展開は以下となります。
   $$x^2 = \frac{\pi^2}{3} + \sum_{n=1}^{\infty} \frac{4(-1)^n}{n^2} \cos(nx) \quad (-\pi \le x \le \pi)$$

2. **無限級数の和の計算**
   区間 $[-\pi, \pi]$ の端点である $x = \pi$ を代入します。（関数 $f(x) = x^2$ の周期 $2\pi$ への拡張は各点で連続であるため、ディリクレの収束定理より値は $f(\pi)$ に収束します。）
   $$\pi^2 = \frac{\pi^2}{3} + \sum_{n=1}^{\infty} \frac{4(-1)^n}{n^2} \cos(n\pi)$$
   $\cos(n\pi) = (-1)^n$ なので、 $(-1)^n \cos(n\pi) = (-1)^{2n} = 1$ となります。
   $$\pi^2 = \frac{\pi^2}{3} + 4 \sum_{n=1}^{\infty} \frac{1}{n^2}$$
   両辺から $\frac{\pi^2}{3}$ を引いて整理します。
   $$\frac{2\pi^2}{3} = 4 \sum_{n=1}^{\infty} \frac{1}{n^2}$$
   両辺を $4$ で割ることで、求める公式が得られます。
   $$\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}$$

---
---

## III. 微分方程式 (Differential Equations)

### 【問題3-1】完全微分方程式
次の微分方程式が完全微分方程式であることを確認し、その一般解を求めよ。
$$(2x \sin y + y^3 e^x)dx + (x^2 \cos y + 3y^2 e^x)dy = 0$$

#### 【解答・解説】
1. **完全性の判定**
   $M(x, y) = 2x \sin y + y^3 e^x$, $N(x, y) = x^2 \cos y + 3y^2 e^x$ とおきます。
   それぞれの偏導関数を求めます。
   * $\frac{\partial M}{\partial y} = 2x \cos y + 3y^2 e^x$
   * $\frac{\partial N}{\partial x} = 2x \cos y + 3y^2 e^x$
   $\frac{\partial M}{\partial y} = \frac{\partial N}{\partial x}$ が成立するため、この方程式は完全微分方程式です。

2. **一般解の導出**
   ポテンシャル関数 $u(x, y)$ を求めます。 $u(x, y)$ は $\frac{\partial u}{\partial x} = M$ および $\frac{\partial u}{\partial y} = N$ を満たします。
   第1式を $x$ で積分します。
   $$u(x, y) = \int (2x \sin y + y^3 e^x) \,dx = x^2 \sin y + y^3 e^x + g(y)$$
   （$g(y)$ は $y$ のみの関数）
   この式を $y$ で偏微分して $N$ と比較します。
   $$\frac{\partial u}{\partial y} = x^2 \cos y + 3y^2 e^x + g'(y) = x^2 \cos y + 3y^2 e^x$$
   これより、 $g'(y) = 0 \implies g(y) = C_0$ （定数）となります。
   したがって、微分方程式の一般解は次のようになります。
   $$x^2 \sin y + y^3 e^x = C \quad (C\text{は任意定数})$$

---

### 【問題3-2】高階線形常微分方程式
次の3階非同次線形微分方程式の一般解を求めよ。
$$y''' - 3y'' + 3y' - y = e^x$$

#### 【解答・解説】
1. **同次方程式の一般解 $y_h$**
   同次方程式 $y''' - 3y'' + 3y' - y = 0$ の特性方程式は、
   $$\lambda^3 - 3\lambda^2 + 3\lambda - 1 = 0 \implies (\lambda - 1)^3 = 0$$
   これは3重根 $\lambda = 1$ を持ちます。したがって、同次方程式の一般解は次の通りです。
   $$y_h = (C_1 + C_2 x + C_3 x^2)e^x \quad (C_1, C_2, C_3\text{は任意定数})$$

2. **非同次方程式の特解 $y_p$**
   右辺の非同次項 $e^x$ は同次方程式の解（特性方程式の3重根に対応）であるため、特解の形を次のように仮定します。
   $$y_p = A x^3 e^x$$
   Leibnizの公式や微分演算子法を用いると計算が容易です。微分演算子 $D = \frac{d}{dx}$ を用いると、方程式は $(D-1)^3 y = e^x$ と書けます。
   指数シフトの法則 $(D-1)^3 (e^x u) = e^x D^3 u$ より、
   $$(D-1)^3 (A x^3 e^x) = e^x D^3(A x^3) = e^x (6A)$$
   これが $e^x$ と等しくなるため、 $6A = 1 \implies A = \frac{1}{6}$ と決定されます。
   よって、特解は $y_p = \frac{1}{6} x^3 e^x$ です。

3. **一般解**
   $$y = y_h + y_p = (C_1 + C_2 x + C_3 x^2)e^x + \frac{1}{6}x^3 e^x$$

---

### 【問題3-3】ベルヌーイの微分方程式
次の非線形微分方程式の一般解を求めよ。
$$\frac{dy}{dx} + \frac{y}{x} = x y^2 \quad (x > 0)$$

#### 【解答・解説】
本問は、 $y' + P(x)y = Q(x)y^n$ の形をした**ベルヌーイの微分方程式**（$n=2$ の場合）です。適切な変数変換を行うことで、1階線形微分方程式に帰着させます。

1. **変数変換**
   $y \neq 0$ と仮定し、方程式の両辺を $y^2$ で割ります。
   $$y^{-2} \frac{dy}{dx} + \frac{1}{x} y^{-1} = x \quad \cdots \text{(i)}$$
   ここで、 $u = y^{-1}$ とおきます。両辺を $x$ で微分すると、
   $$\frac{du}{dx} = -y^{-2} \frac{dy}{dx} \implies y^{-2} \frac{dy}{dx} = -\frac{du}{dx}$$
   これを式 (i) に代入すると、 $u$ に関する次の1階線形微分方程式が得られます。
   $$-\frac{du}{dx} + \frac{u}{x} = x \implies \frac{du}{dx} - \frac{u}{x} = -x \quad \cdots \text{(ii)}$$

2. **線形微分方程式の解法**
   積分因子 $I(x)$ を用います。
   $$I(x) = e^{\int -\frac{1}{x} \,dx} = e^{-\log x} = \frac{1}{x}$$
   式 (ii) の両辺に $\frac{1}{x}$ を掛けます。
   $$\frac{1}{x} \frac{du}{dx} - \frac{u}{x^2} = -1 \implies \frac{d}{dx} \left( \frac{u}{x} \right) = -1$$
   両辺を $x$ で積分します。
   $$\frac{u}{x} = -x + C \implies u = -x^2 + Cx \quad (C\text{は任意定数})$$

3. **変数を $y$ に戻す**
   $u = y^{-1}$ だったので、
   $$y = \frac{1}{u} = \frac{1}{Cx - x^2}$$
   したがって、一般解は $y = \frac{1}{Cx - x^2}$ となります。（また、両辺を $y^2$ で割る過程で除外した $y = 0$ もこの方程式の自明な解（特異解）です。）

---
---

## IV. 複素解析 (Complex Analysis)

### 【問題4-1】コーシーの積分公式
複素平面上の反時計回りの単位円 $C: |z| = 1$ において、次の周回積分を計算せよ。
$$I = \oint_C \frac{e^z}{z^2(z-2)} \,dz$$

#### 【解答・解説】
被積分関数 $f(z) = \frac{e^z}{z^2(z-2)}$ の特異点（極）は $z=0$ （2位の極）と $z=2$ （1位の極）です。
積分経路である単位円 $C$ の内部に含まれる特異点は **$z=0$ のみ** です。

したがって、 $g(z) = \frac{e^z}{z-2}$ とおくと、 $g(z)$ は $C$ とその内部で正則（解析的）です。
コーシーの積分公式の導関数バージョン：
$$\oint_C \frac{g(z)}{(z-a)^{n+1}} \,dz = \frac{2\pi i}{n!} g^{(n)}(a)$$
を $a=0, n=1$ として適用します。
$$I = \oint_C \frac{g(z)}{z^2} \,dz = 2\pi i g'(0)$$

$g'(z)$ を計算します。商の微分公式より、
$$g'(z) = \frac{e^z(z-2) - e^z(1)}{(z-2)^2} = \frac{e^z(z-3)}{(z-2)^2}$$
$z=0$ を代入します。
$$g'(0) = \frac{e^0(0-3)}{(0-2)^2} = -\frac{3}{4}$$
よって、積分の値は以下となります。
$$I = 2\pi i \left(-\frac{3}{4}\right) = -\frac{3}{2}\pi i$$

---

### 【問題4-2】留数定理と実積分
次の定積分を留数定理を用いて求めよ（ただし $a > 0$ とする）。
$$I = \int_0^{\infty} \frac{\cos x}{x^2+a^2} \,dx$$

#### 【解答・解説】
被積分関数が偶関数であるため、積分範囲を全実数に広げます。
$$I = \frac{1}{2} \int_{-\infty}^{\infty} \frac{\cos x}{x^2+a^2} \,dx = \frac{1}{2} \operatorname{Re} \left( \int_{-\infty}^{\infty} \frac{e^{ix}}{x^2+a^2} \,dx \right)$$

複素関数 $f(z) = \frac{e^{iz}}{z^2+a^2}$ を考え、実数軸 $[-R, R]$ と上半平面の半円弧 $C_R$ からなる閉経路 $C$ に沿った積分を行います。
1. **極の決定**
   分母 $z^2+a^2 = (z-ia)(z+ia) = 0$ より、上半平面に含まれる極は $z = ia$ （1位の極）のみです。

2. **留数の計算**
   $$\operatorname{Res}(f, ia) = \lim_{z \to ia} (z-ia) \frac{e^{iz}}{(z-ia)(z+ia)} = \frac{e^{i(ia)}}{2ia} = \frac{e^{-a}}{2ia}$$

3. **留数定理の適用**
   $$\oint_C f(z) \,dz = 2\pi i \operatorname{Res}(f, ia) = 2\pi i \left( \frac{e^{-a}}{2ia} \right) = \frac{\pi e^{-a}}{a}$$

4. **極限**
   $R \to \infty$ のとき、ジョルダンの補題（Jordan's Lemma）より、半円弧 $C_R$ 上の積分は $0$ に収束します。
   $$\int_{-\infty}^{\infty} \frac{e^{ix}}{x^2+a^2} \,dx = \frac{\pi e^{-a}}{a}$$
   実部をとると、
   $$\int_{-\infty}^{\infty} \frac{\cos x}{x^2+a^2} \,dx = \frac{\pi e^{-a}}{a}$$
   したがって、求める積分値は以下の通りです。
   $$I = \frac{1}{2} \cdot \frac{\pi e^{-a}}{a} = \frac{\pi e^{-a}}{2a}$$

---

### 【問題4-3】複素関数のローラン展開
複素関数 $f(z) = \frac{1}{z(z-2)}$ について、次の各領域における $z=0$ を中心とするローラン（Laurent）展開を求めよ。
1. 領域 $0 < |z| < 2$
2. 領域 $|z| > 2$

#### 【解答・解説】
特異点 $z = 2$ の影響を考慮し、それぞれの領域で級数が収束するように展開を行います（等比級数の収束条件 $|w| < 1$ を利用します）。

1. **領域 $0 < |z| < 2$ における展開**
   この領域では $\left|\frac{z}{2}\right| < 1$ であるため、 $\frac{z}{2}$ のべき級数として展開します。
   $$f(z) = \frac{1}{z} \cdot \frac{1}{z-2} = -\frac{1}{2z} \cdot \frac{1}{1 - \frac{z}{2}}$$
   ここで、無限等比級数の和の公式 $\frac{1}{1-w} = \sum_{n=0}^{\infty} w^n$ （$|w| < 1$）において $w = \frac{z}{2}$ とします。
   $$f(z) = -\frac{1}{2z} \sum_{n=0}^{\infty} \left( \frac{z}{2} \right)^n = -\sum_{n=0}^{\infty} \frac{z^{n-1}}{2^{n+1}}$$
   具体的に書き下すと以下のようになり、主要部（マイナス乗の項）として $\frac{1}{z}$ の項が現れます。
   $$f(z) = -\frac{1}{2z} - \frac{1}{4} - \frac{z}{8} - \frac{z^2}{16} - \cdots$$

2. **領域 $|z| > 2$ における展開**
   この領域では $\left|\frac{2}{z}\right| < 1$ であるため、 $\frac{2}{z}$ のべき級数として展開します。
   $$f(z) = \frac{1}{z} \cdot \frac{1}{z-2} = \frac{1}{z^2} \cdot \frac{1}{1 - \frac{2}{z}}$$
   $w = \frac{2}{z}$ として等比級数展開を行います。
   $$f(z) = \frac{1}{z^2} \sum_{n=0}^{\infty} \left( \frac{2}{z} \right)^n = \sum_{n=0}^{\infty} \frac{2^n}{z^{n+2}}$$
   具体的に書き下すと以下のようになり、すべての項が $z$ のマイナス乗（主要部のみ）で構成されます。
   $$f(z) = \frac{1}{z^2} + \frac{2}{z^3} + \frac{4}{z^4} + \frac{8}{z^5} + \cdots$$

---
---

## V. ベクトル解析 (Vector Calculus)

### 【問題5-1】ストークスの定理
ベクトル場 $\mathbf{F}(x,y,z) = (-y^3, x^3, -z^3)$ に対し、曲線 $C$ を円柱 $x^2+y^2=1$ と平面 $z=1$ の交線とする（上から見て反時計回り）。ストークスの定理を用いて、次の線積分を計算せよ。
$$\oint_C \mathbf{F} \cdot d\mathbf{r}$$

#### 【解答・解説】
ストークスの定理（Stokes' Theorem）は以下のように表されます。
$$\oint_C \mathbf{F} \cdot d\mathbf{r} = \iint_S (\nabla \times \mathbf{F}) \cdot \mathbf{n} \,dS$$
ここで $S$ は境界が $C$ であるような曲面であり、今回は平面 $z=1$ 上の円領域（ディスク） $D = \{ (x,y,1) \mid x^2+y^2 \le 1 \}$ とします。

1. **回転（curl）の計算**
   $$\nabla \times \mathbf{F} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ -y^3 & x^3 & -z^3 \end{vmatrix}$$
   $$= (0 - 0)\mathbf{i} + (0 - 0)\mathbf{j} + \left( \frac{\partial(x^3)}{\partial x} - \frac{\partial(-y^3)}{\partial y} \right) \mathbf{k} = 3(x^2 + y^2)\mathbf{k}$$

2. **法線ベクトルと面積要素**
   平面 $z=1$ 上の領域なので、単位法線ベクトルは $\mathbf{n} = \mathbf{k}$ です。また $dS = dx\,dy$ です。
   したがって、被積分関数は、
   $$(\nabla \times \mathbf{F}) \cdot \mathbf{n} = 3(x^2 + y^2)\mathbf{k} \cdot \mathbf{k} = 3(x^2 + y^2)$$

3. **面積分の計算**
   単位円板上での重積分を極座標（$x = r\cos\theta, y = r\sin\theta$）で計算します。
   $$\iint_S 3(x^2+y^2) \,dS = \int_0^{2\pi} \int_0^1 3r^2 \cdot r \,dr\,d\theta$$
   $$= 3 \left( \int_0^{2\pi} d\theta \right) \left( \int_0^1 r^3 \,dr \right) = 3 \cdot 2\pi \cdot \left[ \frac{r^4}{4} \right]_0^1 = \frac{3\pi}{2}$$

---

### 【問題5-2】ガウスの発散定理
ベクトル場 $\mathbf{F}(x,y,z) = (x^3, y^3, z^3)$ に対し、曲面 $S$ を単位球面 $x^2+y^2+z^2=1$ とし、 $\mathbf{n}$ を外向き単位法線ベクトルとする。ガウスの発散定理を用いて、次の面積分を計算せよ。
$$\iint_S \mathbf{F} \cdot \mathbf{n} \,dS$$

#### 【解答・解説】
ガウスの発散定理（Divergence Theorem）は以下のように表されます。
$$\iint_S \mathbf{F} \cdot \mathbf{n} \,dS = \iiint_V (\nabla \cdot \mathbf{F}) \,dV$$
ここで $V$ は単位球面 $S$ の内部である単位球体 $x^2+y^2+z^2 \le 1$ です。

1. **発散（div）の計算**
   $$\nabla \cdot \mathbf{F} = \frac{\partial(x^3)}{\partial x} + \frac{\partial(y^3)}{\partial y} + \frac{\partial(z^3)}{\partial z} = 3x^2 + 3y^2 + 3z^2 = 3(x^2 + y^2 + z^2)$$

2. **3重積分の計算**
   球座標（極座標） $x = \rho\sin\phi\cos\theta, y = \rho\sin\phi\sin\theta, z = \rho\cos\phi$ を導入します。
   ヤコビアンは $\rho^2\sin\phi$ であり、被積分関数は $3\rho^2$ です。積分範囲は $\rho: 0 \to 1$, $\theta: 0 \to 2\pi$, $\phi: 0 \to \pi$ です。
   $$\iiint_V 3(x^2+y^2+z^2) \,dV = \int_0^{\pi} \int_0^{2\pi} \int_0^1 3\rho^2 \cdot \rho^2 \sin\phi \,d\rho\,d\theta\,d\phi$$
   各変数の積分は独立に計算できます。
   $$\iiint_V 3(x^2+y^2+z^2) \,dV = 3 \left( \int_0^1 \rho^4 \,d\rho \right) \left( \int_0^{2\pi} d\theta \right) \left( \int_0^{\pi} \sin\phi \,d\phi \right)$$
   * $\int_0^1 \rho^4 \,d\rho = \frac{1}{5}$
   * $\int_0^{2\pi} d\theta = 2\pi$
   * $\int_0^{\pi} \sin\phi \,d\phi = [-\cos\phi]_0^{\pi} = 2$
   よって、積分の値は以下となります。
   $$\iint_S \mathbf{F} \cdot \mathbf{n} \,dS = 3 \cdot \frac{1}{5} \cdot 2\pi \cdot 2 = \frac{12}{5}\pi$$

---
---

## VI. 幾何・微分幾何 (Differential Geometry)

### 【問題6-1】空間曲線の曲率と捩率
次のパラメータ表示をもつ空間曲線（常螺旋） $\mathbf{r}(t)$ を考える（ただし $a > 0, b > 0$とする）。
$$\mathbf{r}(t) = (a\cos t, a\sin t, bt)$$
1. $t=0$ から $t=2\pi$ までの曲線の弧長 $s$ を求めよ。
2. 任意の $t$ における曲率 $\kappa(t)$ および捩率（ねじれ率） $\tau(t)$ を求めよ。

#### 【解答・解説】
1. **弧長 $s$ の計算**
   速度ベクトルとそのノルム（速さ）を求めます。
   $$\mathbf{r}'(t) = (-a\sin t, a\cos t, b)$$
   $$\|\mathbf{r}'(t)\| = \sqrt{(-a\sin t)^2 + (a\cos t)^2 + b^2} = \sqrt{a^2(\sin^2 t + \cos^2 t) + b^2} = \sqrt{a^2+b^2}$$
   速さは一定値 $\sqrt{a^2+b^2}$ です。よって弧長 $s$ は、
   $$s = \int_0^{2\pi} \|\mathbf{r}'(t)\| \,dt = \int_0^{2\pi} \sqrt{a^2+b^2} \,dt = 2\pi\sqrt{a^2+b^2}$$

2. **曲率 $\kappa$ と捩率 $\tau$ の計算**
   微分幾何学における以下のベクトル公式を用います。
   $$\kappa = \frac{\|\mathbf{r}' \times \mathbf{r}''\|}{\|\mathbf{r}'\|^3}, \quad \tau = \frac{(\mathbf{r}' \times \mathbf{r}'') \cdot \mathbf{r}'''}{\|\mathbf{r}' \times \mathbf{r}''\|^2}$$
   各階の微分ベクトルを求めます。
   * $\mathbf{r}'(t) = (-a\sin t, \; a\cos t, \; b)$
   * $\mathbf{r}''(t) = (-a\cos t, \; -a\sin t, \; 0)$
   * $\mathbf{r}'''(t) = (a\sin t, \; -a\cos t, \; 0)$

   外積 $\mathbf{r}' \times \mathbf{r}''$ を求めます。
   $$\mathbf{r}' \times \mathbf{r}'' = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ -a\sin t & a\cos t & b \\ -a\cos t & -a\sin t & 0 \end{vmatrix} = (ab\sin t)\mathbf{i} - (ab\cos t)\mathbf{j} + a^2\mathbf{k}$$
   このベクトルのノルムは、
   $$\|\mathbf{r}' \times \mathbf{r}''\| = \sqrt{a^2 b^2\sin^2 t + a^2 b^2\cos^2 t + a^4} = \sqrt{a^2 b^2 + a^4} = a\sqrt{a^2+b^2}$$

   * **曲率 $\kappa$**
     $$\kappa = \frac{a\sqrt{a^2+b^2}}{(\sqrt{a^2+b^2})^3} = \frac{a}{a^2+b^2}$$
   * **捩率 $\tau$**
     3重積 $(\mathbf{r}' \times \mathbf{r}'') \cdot \mathbf{r}'''$ を計算します。
     $$(\mathbf{r}' \times \mathbf{r}'') \cdot \mathbf{r}''' = (ab\sin t)(a\sin t) + (-ab\cos t)(-a\cos t) + a^2(0) = a^2 b(\sin^2 t + \cos^2 t) = a^2 b$$
     公式に代入します。
     $$\tau = \frac{a^2 b}{\|\mathbf{r}' \times \mathbf{r}''\|^2} = \frac{a^2 b}{a^2(a^2+b^2)} = \frac{b}{a^2+b^2}$$

   曲率・捩率ともに $t$ に依らない一定値となります。

---
---

## VII. 代数学・整数論 (Algebra & Number Theory)

### 【問題7-1】中国式剰余定理（合同式の計算）
次の連立合同式を満たす最小の正の整数 $x$ を求めよ。
$$\begin{cases}
x \equiv 2 \pmod 3 \\
x \equiv 3 \pmod 5 \\
x \equiv 5 \pmod 7
\end{cases}$$

#### 【解答・解説】
法 $3, 5, 7$ は互いに素であるため、中国式剰余定理（CRT）により一意の解が存在します。全体を $M = 3 \times 5 \times 7 = 105$ の法で考えます。

1. **各項の重みの決定**
   * **法 3 に関して**： $M_1 = 105 / 3 = 35$。
     合同式 $35y_1 \equiv 1 \pmod 3 \implies 2y_1 \equiv 1 \pmod 3 \implies y_1 \equiv 2 \pmod 3$。
   * **法 5 に関して**： $M_2 = 105 / 5 = 21$。
     合同式 $21y_2 \equiv 1 \pmod 5 \implies 1y_2 \equiv 1 \pmod 5 \implies y_2 \equiv 1 \pmod 5$。
   * **法 7 に関して**： $M_3 = 105 / 7 = 15$。
     合同式 $15y_3 \equiv 1 \pmod 7 \implies 1y_3 \equiv 1 \pmod 7 \implies y_3 \equiv 1 \pmod 7$。

2. **一般解の構築**
   $$x \equiv a_1 M_1 y_1 + a_2 M_2 y_2 + a_3 M_3 y_3 \pmod M$$
   より、数値を代入します。
   $$x \equiv 2 \cdot 35 \cdot 2 + 3 \cdot 21 \cdot 1 + 5 \cdot 15 \cdot 1 \pmod{105}$$
   $$x \equiv 140 + 63 + 75 \pmod{105}$$
   $$x \equiv 278 \pmod{105}$$

3. **最小の正の整数の決定**
   $$278 = 2 \times 105 + 68$$
   よって、 $x \equiv 68 \pmod{105}$。
   最小の正の整数は **68** となります。
   （検算： $68 = 3 \times 22 + 2$, $68 = 5 \times 13 + 3$, $68 = 7 \times 9 + 5$ となり、確かに条件を満たします。）

---

### 【問題7-2】群の準同型写像と正規部分群
$G, G'$ を群とし、 $\phi: G \to G'$ を群準同型写像とする。
このとき、 $\phi$ の核（Kernel） $\operatorname{Ker}(\phi) = \{ g \in G \mid \phi(g) = e' \}$ （ただし $e'$ は $G'$ の単位元）は、 $G$ の正規部分群であることを証明せよ。

#### 【解答・解説】
$\operatorname{Ker}(\phi) = K$ とおきます。 $K$ が正規部分群であることを示すために、「(1) $K$ が $G$ の部分群であること」および「(2) $K$ が共役変換に関して閉じていること（正規性）」を示します。

1. **部分群であることの証明**
   * **(i) 単位元の存在**： 準同型写像の性質より、 $\phi(e) = e'$ です。よって $e \in K$ です。
   * **(ii) 積と逆元について閉じていること**： $x, y \in K$ とします。このとき $\phi(x) = e'$, $\phi(y) = e'$ です。
     積 $xy^{-1}$ について写像を計算します。準同型の性質 $\phi(y^{-1}) = \phi(y)^{-1}$ を用います。
     $$\phi(xy^{-1}) = \phi(x)\phi(y^{-1}) = \phi(x)\phi(y)^{-1} = e'(e')^{-1} = e'e' = e'$$
     したがって $xy^{-1} \in K$ となり、 $K$ は $G$ の部分群です。

2. **正規性（共役に関して閉じていること）の証明**
   任意の $g \in G$ および任意の $k \in K$ に対し、 $gkg^{-1} \in K$ となることを示します。
   写像 $\phi(gkg^{-1})$ を計算します。
   $$\phi(gkg^{-1}) = \phi(g)\phi(k)\phi(g^{-1})$$
   $k \in K \implies \phi(k) = e'$ なので、
   $$\phi(gkg^{-1}) = \phi(g) e' \phi(g)^{-1} = \phi(g)\phi(g)^{-1} = e'$$
   $\phi(gkg^{-1}) = e'$ より、 $gkg^{-1} \in K$ であることが示されました。

以上より、 $\operatorname{Ker}(\phi)$ は $G$ の正規部分群です。 (証明終)

---

### 【問題7-3】多項式環の剰余環と体の同型
実数体 $\mathbb{R}$ 上の多項式環を $\mathbb{R}[x]$ とし、多項式 $x^2+1$ で生成される単項イデアルを $I = (x^2+1)$ とする。
このとき、剰余環 $\mathbb{R}[x]/I$ が複素数体 $\mathbb{C}$ と同型であること、すなわち
$$\mathbb{R}[x]/I \cong \mathbb{C}$$
を証明せよ。

#### 【解答・解説】
環の準同型定理（第一同型定理）を用いて証明します。

1. **写像の定義**
   写像 $\phi: \mathbb{R}[x] \to \mathbb{C}$ を、各多項式 $p(x) \in \mathbb{R}[x]$ に対して $x$ に虚数単位 $i$ を代入する写像として定義します。
   $$\phi(p(x)) = p(i)$$
   この写像 $\phi$ は、複素数に対する通常の代入および四則演算の性質より、環準同型写像（任意の $p(x), q(x)$ に対して $\phi(p+q) = \phi(p)+\phi(q)$ かつ $\phi(pq) = \phi(p)\phi(q)$）となります。

2. **全射（Surjectivity）の証明**
   任意の複素数 $a + bi \in \mathbb{C}$ （$a, b \in \mathbb{R}$）に対し、 1次多項式 $g(x) = a + bx \in \mathbb{R}[x]$ を考えると、
   $$\phi(g(x)) = g(i) = a + bi$$
   となるため、 $\phi$ は全射です。

3. **核（Kernel）の決定**
   写像の核 $\operatorname{Ker}(\phi)$ を求めます。定義より、
   $$\operatorname{Ker}(\phi) = \{ p(x) \in \mathbb{R}[x] \mid p(i) = 0 \}$$
   * $p(x) \in I = (x^2+1)$ のとき、 $p(x) = (x^2+1)q(x)$ と書けるため、 $\phi(p(x)) = (i^2+1)q(i) = 0$ となり、 $p(x) \in \operatorname{Ker}(\phi)$ です。したがって、 $I \subset \operatorname{Ker}(\phi)$。
   * 逆に、 $p(x) \in \operatorname{Ker}(\phi)$ のとき、 $p(i) = 0$ です。 $p(x)$ は実数係数多項式なので、共役複素数である $-i$ も $p(x)$ の根になります（$p(-i) = 0$）。
     したがって、因数定理より $p(x)$ は複素数体上で $(x-i)(x+i) = x^2+1$ で割り切れます。 $x^2+1$ は実数係数多項式であるため、多項式の除法により、 $\mathbb{R}[x]$ 上でも $p(x)$ は $x^2+1$ で割り切れます。すなわち、 $p(x) \in (x^2+1) = I$。したがって、 $\operatorname{Ker}(\phi) \subset I$。
   以上より、 $\operatorname{Ker}(\phi) = I = (x^2+1)$ となります。

4. **準同型定理の適用**
   写像 $\phi$ は全射環準同型であり、その核は $\operatorname{Ker}(\phi) = I$ です。
   環の第一同型定理より、
   $$\mathbb{R}[x]/\operatorname{Ker}(\phi) \cong \operatorname{Im}(\phi) \implies \mathbb{R}[x]/I \cong \mathbb{C}$$
   が成り立ちます。 (証明終)

---
---

## VIII. 確率・統計 (Probability & Statistics)

### 【問題8-1】ベイズの定理
ある感染症の検査において、罹患者が正しく陽性と判定される確率（感度）は $99\%$、非罹患者が正しく陰性と判定される確率（特異度）は $95\%$ であるとする。全人口に対するこの感染症の罹患率が $0.5\%$ であるとき、ある人が検査を受けて陽性となった場合、その人が実際に罹患している確率を求めよ。

#### 【解答・解説】
事象を次のように定義します。
* $D$：感染症に罹患している事象
* $T$：検査結果が陽性である事象

問題文から得られる確率は以下の通りです。
* 罹患率： $P(D) = 0.005 \implies P(D^c) = 0.995$
* 感度： $P(T \mid D) = 0.99$
* 特異度： $P(T^c \mid D^c) = 0.95 \implies P(T \mid D^c) = 0.05$ （偽陽性率）

ベイズの定理（Bayes' Theorem）を用いて、陽性判定が出たもとで実際に罹患している条件付き確率 $P(D \mid T)$ を求めます。
$$P(D \mid T) = \frac{P(T \mid D)P(D)}{P(T)}$$
全確率の公式から、陽性となる確率 $P(T)$ は次のようになります。
$$P(T) = P(T \mid D)P(D) + P(T \mid D^c)P(D^c)$$
$$= 0.99 \times 0.005 + 0.05 \times 0.995 = 0.00495 + 0.04975 = 0.0547$$

したがって、求める確率は、
$$P(D \mid T) = \frac{0.00495}{0.0547} = \frac{495}{5470} = \frac{99}{1094} \approx 0.0905$$
実際に罹患している確率は約 **$9.05\%$** です。

---

### 【問題8-2】ポアソン分布の最尤推定
パラメータ $\lambda > 0$ を持つポアソン分布からの大きさ $n$ のランダム標本 $X_1, X_2, \dots, X_n$ がある。この分布の確率質量関数は以下の通りである。
$$P(X_i = x_i) = \frac{e^{-\lambda} \lambda^{x_i}}{x_i!}$$
1. パラメータ $\lambda$ の最尤推定量 $\hat{\lambda}$ を求めよ。
2. その最尤推定量が $\lambda$ の不偏推定量（unbiased estimator）であることを示せ。

#### 【解答・解説】
1. **最尤推定量 $\hat{\lambda}$ の導出**
   尤度関数 $L(\lambda)$ は各サンプルの確率の積です。
   $$L(\lambda) = \prod_{i=1}^n \frac{e^{-\lambda} \lambda^{x_i}}{x_i!} = e^{-n\lambda} \lambda^{\sum_{i=1}^n x_i} \prod_{i=1}^n \frac{1}{x_i!}$$
   対数尤度関数 $\ell(\lambda) = \log L(\lambda)$ を計算します。
   $$\ell(\lambda) = -n\lambda + \left( \sum_{i=1}^n x_i \right) \log\lambda - \sum_{i=1}^n \log(x_i!)$$
   $\lambda$ について微分して $0$ とおきます。
   $$\frac{d\ell}{d\lambda} = -n + \frac{\sum_{i=1}^n x_i}{\lambda} = 0 \implies \lambda = \frac{1}{n} \sum_{i=1}^n x_i = \bar{x}$$
   2階微分は $\frac{d^2\ell}{d\lambda^2} = -\frac{\sum x_i}{\lambda^2} < 0$ となり、対数尤度を最大化します。
   したがって、最尤推定量は標本平均 $\bar{X}$ となります。
   $$\hat{\lambda} = \bar{X} = \frac{1}{n} \sum_{i=1}^n X_i$$

2. **不偏性の証明**
   期待値 $E[\hat{\lambda}]$ を求めます。各 $X_i$ の期待値は元のポアソン分布の期待値 $E[X_i] = \lambda$ です。
   $$E[\hat{\lambda}] = E\left[ \frac{1}{n} \sum_{i=1}^n X_i \right] = \frac{1}{n} \sum_{i=1}^n E[X_i] = \frac{1}{n} \sum_{i=1}^n \lambda = \frac{n\lambda}{n} = \lambda$$
   期待値がパラメータ $\lambda$ と一致するため、最尤推定量 $\hat{\lambda}$ は $\lambda$ の不偏推定量です。 (証明終)

---

### 【問題8-3】カイ二乗適合度検定
あるサイコロを 120 回投げたところ、各目（1〜6）の出た回数が以下のようになった。
* 1の目：12回、 2の目：28回、 3の目：15回、 4の目：25回、 5の目：18回、 6の目：22回

このサイコロの目が均等に出る（公平なサイコロである）という仮説を、有意水準 $5\%$ でカイ二乗適合度検定せよ。
（自由度 5 のカイ二乗分布の右側 $5\%$ 点は $\chi^2_{0.05}(5) = 11.07$ とする。）

#### 【解答・解説】
1. **仮説の設定**
   * 帰無仮説 $H_0$：サイコロの目は均等に出る（各目の出る確率 $p_i = \frac{1}{6}$）
   * 対立仮説 $H_1$：サイコロの目は均等ではない

2. **期待度数 $E_i$ の計算**
   試行回数 $N = 120$ なので、均等に出る場合の各目の期待度数は以下となります。
   $$E_i = 120 \times \frac{1}{6} = 20 \quad (i = 1, 2, \dots, 6)$$

3. **検定統計量 $\chi^2$ の計算**
   観測度数を $O_i$ とすると、検定統計量は次のように定義されます。
   $$\chi^2 = \sum_{i=1}^6 \frac{(O_i - E_i)^2}{E_i}$$
   計算を行います。
   * $i=1$: $\frac{(12 - 20)^2}{20} = \frac{64}{20} = 3.2$
   * $i=2$: $\frac{(28 - 20)^2}{20} = \frac{64}{20} = 3.2$
   * $i=3$: $\frac{(15 - 20)^2}{20} = \frac{25}{20} = 1.25$
   * $i=4$: $\frac{(25 - 20)^2}{20} = \frac{25}{20} = 1.25$
   * $i=5$: $\frac{(18 - 20)^2}{20} = \frac{4}{20} = 0.2$
   * $i=6$: $\frac{(22 - 20)^2}{20} = \frac{4}{20} = 0.2$

   これらを合計します。
   $$\chi^2 = 3.2 + 3.2 + 1.25 + 1.25 + 0.2 + 0.2 = 9.3$$

4. **判定と結論**
   自由度は カテゴリ数 $- 1 = 6 - 1 = 5$ です。
   有意水準 $5\%$ における棄却限界値は $\chi^2_{0.05}(5) = 11.07$ です。
   計算された統計量 $\chi^2 = 9.3$ は棄却限界値より小さいため（$\chi^2 = 9.3 < 11.07$）、帰無仮説 $H_0$ は棄却されません。

したがって、「有意水準 5% において、このサイコロの目は均等ではないとは言えない（公平なサイコロであるという仮説は否定されない）」と結論づけられます。

---

### 【問題8-4】2次元連続型確率変数の同時分布・周辺分布・共分散
連続型確率変数 $X$ と $Y$ の同時確率密度関数 $f(x, y)$ が以下のように与えられている。
$$f(x, y) = \begin{cases} c(x+y) & (0 \le x \le 1, \; 0 \le y \le 1) \\ 0 & (\text{その他}) \end{cases}$$
1. 定数 $c$ の値を求めよ。
2. $X$ および $Y$ の周辺確率密度関数 $f_X(x), f_Y(y)$ をそれぞれ求めよ。
3. $X$ と $Y$ は独立であるか判定せよ。
4. $X$ と $Y$ の共分散 $\operatorname{Cov}(X, Y)$ を求めよ。

#### 【解答・解説】
1. **定数 $c$ の計算**
   確率の全領域における重積分（総和）は $1$ になる性質（全確率の条件）を利用します。
   $$\int_0^1 \int_0^1 c(x+y) \,dx\,dy = 1$$
   内側の $x$ について積分します。
   $$\int_0^1 c(x+y) \,dx = c \left[ \frac{x^2}{2} + xy \right]_0^1 = c \left( \frac{1}{2} + y \right)$$
   これを $y$ について積分します。
   $$\int_0^1 c \left( \frac{1}{2} + y \right) \,dy = c \left[ \frac{y}{2} + \frac{y^2}{2} \right]_0^1 = c \left( \frac{1}{2} + \frac{1}{2} \right) = c$$
   したがって、 $c = 1$ と決定されます。

2. **周辺確率密度関数 $f_X(x), f_Y(y)$**
   * **$f_X(x)$ （$0 \le x \le 1$）の計算**
     $$f_X(x) = \int_{-\infty}^{\infty} f(x, y) \,dy = \int_0^1 (x+y) \,dy = \left[ xy + \frac{y^2}{2} \right]_0^1 = x + \frac{1}{2}$$
   * **$f_Y(y)$ （$0 \le y \le 1$）の計算**
     対称性より、同様に求まります。
     $$f_Y(y) = \int_0^1 (x+y) \,dx = y + \frac{1}{2}$$
     
   周辺確率密度関数はそれぞれ、 $f_X(x) = x + \frac{1}{2}$ （$0 \le x \le 1$）、 $f_Y(y) = y + \frac{1}{2}$ （$0 \le y \le 1$）であり、それ以外の領域では $0$ です。

3. **独立性の判定**
   $X$ と $Y$ が独立であるための必要十分条件は、すべての $(x, y)$ において $f(x, y) = f_X(x)f_Y(y)$ が成立することです。
   $$f_X(x)f_Y(y) = \left(x+\frac{1}{2}\right)\left(y+\frac{1}{2}\right) = xy + \frac{x}{2} + \frac{y}{2} + \frac{1}{4}$$
   これは同時確率密度関数 $f(x, y) = x+y$ と一致しません（例： $x=0, y=0$ で $f(0,0)=0$ に対し $f_X(0)f_Y(0)=1/4 \neq 0$）。
   したがって、 $X$ と $Y$ は**独立ではありません（相関・依存関係がある）**。

4. **共分散 $\operatorname{Cov}(X, Y)$ の計算**
   共分散の公式 $\operatorname{Cov}(X, Y) = E[XY] - E[X]E[Y]$ を用います。
   
   * **期待値 $E[X]$ （対称性より $E[Y] = E[X]$）**
     $$E[X] = \int_0^1 x f_X(x) \,dx = \int_0^1 x \left( x + \frac{1}{2} \right) \,dx = \int_0^1 \left( x^2 + \frac{x}{2} \right) \,dx = \left[ \frac{x^3}{3} + \frac{x^2}{4} \right]_0^1 = \frac{1}{3} + \frac{1}{4} = \frac{7}{12}$$
     対称性より $E[Y] = \frac{7}{12}$ です。
     
   * **積の期待値 $E[XY]$**
     $$E[XY] = \int_0^1 \int_0^1 xy f(x, y) \,dx\,dy = \int_0^1 \int_0^1 xy(x+y) \,dx\,dy = \int_0^1 \int_0^1 (x^2 y + xy^2) \,dx\,dy$$
     内側の $x$ について積分します。
     $$\int_0^1 (x^2 y + xy^2) \,dx = \left[ \frac{x^3}{3}y + \frac{x^2}{2}y^2 \right]_0^1 = \frac{y}{3} + \frac{y^2}{2}$$
     これを $y$ について積分します。
     $$E[XY] = \int_0^1 \left( \frac{y}{3} + \frac{y^2}{2} \right) \,dy = \left[ \frac{y^2}{6} + \frac{y^3}{6} \right]_0^1 = \frac{1}{6} + \frac{1}{6} = \frac{1}{3}$$
     
   * **共分散 $\operatorname{Cov}(X, Y)$**
     $$\operatorname{Cov}(X, Y) = \frac{1}{3} - \left(\frac{7}{12}\right)\left(\frac{7}{12}\right) = \frac{1}{3} - \frac{49}{144} = \frac{48 - 49}{144} = -\frac{1}{144}$$
     したがって、共分散は $-\frac{1}{144}$ です。

# 数学検定1級 一次試験（計算技能）模擬試験［第7回］

数学検定1級一次試験（計算技能）対策のための、第7回模擬試験問題（全7問）と詳細な解答解説です。今回の模擬試験では、曲線の包絡線方程式、ケーリー・ハミルトンの定理を用いた高次行列多項式の次数下げ、オイラー・コーシーの可変係数微分方程式、メビウスの複素一次分数変換、射影やフラックスを直接計算する面積分、極大イデアルと商体の同型証明、および離散共同分布の相関係数の計算など、試験で差がつきやすい応用パターンを集中的に扱います。

---

## 模擬試験問題（制限時間：60分）

### 【問題1】微分積分学（曲線の包絡線）
実数パラメータ $\theta$ に対する次の直線群の包絡線（envelope）の方程式を求めよ（ただし $a > 0$ とする）。
$$x \cos \theta + y \sin \theta = a$$

### 【問題2】線形代数（ケーリー・ハミルトンの定理と多項式）
行列 $A = \begin{pmatrix} 3 & 1 \\ 1 & 2 \end{pmatrix}$ に対し、ケーリー・ハミルトンの定理および多項式の除法を用いて、次の行列多項式の値を求めよ。
$$P(A) = A^4 - 5A^3 + 7A^2 - 3I$$

### 【問題3】微分方程式（オイラー・コーシーの微分方程式）
次の可変係数微分方程式の一般解を求めよ。
$$x^2 y'' - 2x y' + 2y = 0 \quad (x > 0)$$

### 【問題4】複素解析（メビウス変換・一次分数変換）
複素平面上の点 $z_1 = 0, z_2 = 1, z_3 = \infty$ を、それぞれ $w_1 = -1, w_2 = i, w_3 = 1$ に写す一次分数変換（メビウス変換） $w = f(z) = \frac{az+b}{cz+d}$ を求めよ。

### 【問題5】ベクトル解析（面積分・曲面を通るフラックス）
ベクトル場 $\mathbf{F}(x, y, z) = (0, \; 0, \; z)$ に対し、 $S$ を半径 $R$ の上半球面 $x^2 + y^2 + z^2 = R^2 \; (z \ge 0)$ とし、 $\mathbf{n}$ を外向き単位法線ベクトルとする。発散定理を用いず、**面積分を直接計算**して、次のフラックス（流束）を求めよ。
$$\iint_S \mathbf{F} \cdot \mathbf{n} \,dS$$

### 【問題6】代数学（多項式環の極大イデアルと体）
実数体 $\mathbb{R}$ 上の多項式環 $\mathbb{R}[x]$ を考える。元 $x-2$ が生成する単項イデアルを $I = (x-2)$ とするとき、剰余環 $\mathbb{R}[x]/I$ が実数体 $\mathbb{R}$ と同型であることを示し、これよりイデアル $I$ が極大イデアルであることを証明せよ。

### 【問題7】確率・統計（離散型共同分布と相関係数）
2つの離散型確率変数 $X$ と $Y$ の同時確率分布が以下の表で与えられている。
$$\begin{array}{c|ccc}
     Y \backslash X & -1 & 0 & 1 \\
     \hline
     0 & 0.1 & 0.2 & 0.1 \\
     1 & 0.2 & 0.0 & 0.2 \\
     2 & 0.1 & 0.1 & 0.0
     \end{array}$$
このとき、 $X$ と $Y$ の共分散 $\operatorname{Cov}(X, Y)$ および相関係数 $\rho(X, Y)$ を求めよ。（端数は小数第3位までで答えよ。）

---
---

## 解答・解説

### 【問題1】の解答・解説
#### 解答
$$x^2 + y^2 = a^2$$

#### 詳細な計算ステップ
1. **包絡線の定義と立式**
   媒介変数（パラメータ） $\theta$ を含む曲線群の方程式を $F(x, y, \theta) = 0$ とおきます。この曲線群の包絡線（すべての曲線に接する曲線）は、次の連立方程式から $\theta$ を消去することで得られます：
   $$\begin{cases} F(x, y, \theta) = 0 \\ \frac{\partial F}{\partial \theta}(x, y, \theta) = 0 \end{cases}$$

2. **直線の偏微分**
   与えられた直線の式より、 $F(x, y, \theta) = x \cos \theta + y \sin \theta - a = 0 \quad \cdots \text{(1)}$ とします。
   これをパラメータ $\theta$ で偏微分して $0$ とおきます：
   $$\frac{\partial F}{\partial \theta} = -x \sin \theta + y \cos \theta = 0 \quad \cdots \text{(2)}$$

3. **パラメータ $\theta$ の消去**
   式 (1) を $x \cos\theta + y \sin\theta = a$、式 (2) を $-x \sin\theta + y \cos\theta = 0$ と変形し、両辺をそれぞれ平方します：
   * 式 (1) の平方：
     $$(x \cos\theta + y \sin\theta)^2 = a^2 \implies x^2 \cos^2\theta + 2xy \sin\theta\cos\theta + y^2 \sin^2\theta = a^2$$
   * 式 (2) の平方：
     $$(-x \sin\theta + y \cos\theta)^2 = 0 \implies x^2 \sin^2\theta - 2xy \sin\theta\cos\theta + y^2 \cos^2\theta = 0$$
   
   これら2つの式を足し合わせることで、交差項 $2xy\sin\theta\cos\theta$ を相殺します：
   $$(x^2 \cos^2\theta + 2xy \sin\theta\cos\theta + y^2 \sin^2\theta) + (x^2 \sin^2\theta - 2xy \sin\theta\cos\theta + y^2 \cos^2\theta) = a^2 + 0$$
   $$x^2(\cos^2\theta + \sin^2\theta) + y^2(\sin^2\theta + \cos^2\theta) = a^2$$
   三角関数の基本性質 $\cos^2\theta + \sin^2\theta = 1$ を適用すると、次の包絡線の方程式が得られます：
   $$x^2(1) + y^2(1) = a^2 \implies x^2 + y^2 = a^2$$

---

### 【問題2】の解答・解説
#### 解答
$$\begin{pmatrix} 17 & 10 \\ 10 & 7 \end{pmatrix}$$

#### 詳細な計算ステップ
1. **ケーリー・ハミルトンの定理の適用**
   $2 \times 2$ 行列 $A = \begin{pmatrix} 3 & 1 \\ 1 & 2 \end{pmatrix}$ について、ケーリー・ハミルトンの定理 $A^2 - \operatorname{tr}(A)A + \det(A)I = O$ を用います：
   * トレース： $\operatorname{tr}(A) = 3 + 2 = 5$
   * 行列式： $\det(A) = 3(2) - 1(1) = 5$
   したがって、次の行列等式が成り立ちます：
   $$A^2 - 5A + 5I = O \quad \cdots \text{(3)}$$

2. **多項式の除法（次数下げ）**
   求めたい次数 $4$ の行列多項式 $P(x) = x^4 - 5x^3 + 7x^2 - 3$ を、特性多項式 $Q(x) = x^2 - 5x + 5$ で割る多項式の割り算を行います：
   $$x^4 - 5x^3 + 7x^2 - 3 = (x^2 - 5x + 5)x^2 + 2x^2 - 3$$
   さらに、余り $2x^2 - 3$ から $x^2$ を消去するため $2(x^2 - 5x + 5)$ で割ると、次のようになります：
   $$x^4 - 5x^3 + 7x^2 - 3 = (x^2 - 5x + 5)(x^2 + 2) + 10x - 13$$

3. **行列の代入と簡略化**
   この多項式等式に行列 $A$ を代入します。定数項は単位行列 $I$ に置き換わります：
   $$P(A) = (A^2 - 5A + 5I)(A^2 + 2I) + 10A - 13I$$
   式 (3) より $A^2 - 5A + 5I = O$ なので、第1項は零行列 $O$ となり消去されます：
   $$P(A) = O \cdot (A^2 + 2I) + 10A - 13I = 10A - 13I$$

4. **行列値の計算**
   具体的な行列の成分を代入して計算します：
   $$P(A) = 10 \begin{pmatrix} 3 & 1 \\ 1 & 2 \end{pmatrix} - 13 \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 30 & 10 \\ 10 & 20 \end{pmatrix} - \begin{pmatrix} 13 & 0 \\ 0 & 13 \end{pmatrix} = \begin{pmatrix} 17 & 10 \\ 10 & 7 \end{pmatrix}$$

---

### 【問題3】の解答・解説
#### 解答
$$y = C_1 x + C_2 x^2 \quad (C_1, C_2\text{は任意定数})$$

#### 詳細な計算ステップ
1. **微分方程式の分類**
   本方程式 $x^2 y'' - 2x y' + 2y = 0$ は、各項の $x$ の次数と微分の階数が等しい「オイラー・コーシーの微分方程式」です。

2. **解の仮定と代入**
   解を $y = x^r$ と仮定します。それぞれ $x$ で微分します：
   * $y' = r x^{r-1}$
   * $y'' = r(r-1) x^{r-2}$
   
   これらを元の微分方程式に代入します：
   $$x^2 (r(r-1) x^{r-2}) - 2x (r x^{r-1}) + 2 (x^r) = 0$$
   $$r(r-1) x^r - 2r x^r + 2 x^r = 0$$
   共通因数の $x^r$ でくくります：
   $$x^r [ r(r-1) - 2r + 2 ] = 0 \implies x^r [ r^2 - 3r + 2 ] = 0$$
   $x > 0$ であるため $x^r \neq 0$ です。したがって、特性方程式は以下のようになります：
   $$r^2 - 3r + 2 = 0$$

3. **特性方程式の解**
   因数分解して特性根を求めます：
   $$(r-1)(r-2) = 0 \implies r = 1, \; 2$$
   これにより、2つの独立な基本解 $y_1 = x$ と $y_2 = x^2$ が得られます。

4. **一般解**
   基本解の線形結合として一般解を表します：
   $$y = C_1 x + C_2 x^2$$

---

### 【問題4】の解答・解説
#### 解答
$$w = \frac{iz-1}{iz+1} \quad \left( \text{または } w = \frac{z+i}{z-i} \text{ も同様} \right)$$

#### 詳細な計算ステップ
1. **メビウス変換の定義**
   求める一次分数変換は $w = f(z) = \frac{az+b}{cz+d}$ （$ad - bc \neq 0$）の形をしています。

2. **無限遠点 $z_3 = \infty \to w_3 = 1$ の適用**
   $z \to \infty$ の極限を考えます：
   $$\lim_{z \to \infty} \frac{az+b}{cz+d} = \lim_{z \to \infty} \frac{a + b/z}{c + d/z} = \frac{a}{c}$$
   これが $w_3 = 1$ に写るため：
   $$\frac{a}{c} = 1 \implies a = c$$
   これより、変換式は次のように簡略化されます：
   $$w = \frac{az+b}{az+d}$$

3. **原点 $z_1 = 0 \to w_1 = -1$ の適用**
   $z = 0$ を代入します：
   $$f(0) = \frac{a(0)+b}{a(0)+d} = \frac{b}{d} = -1 \implies b = -d$$
   これより、変換式は次のようになります：
   $$w = \frac{az-d}{az+d}$$
   分母・分子を $d$ で割り、比を $k = \frac{a}{d}$ とおきます：
   $$w = \frac{kz-1}{kz+1}$$

4. **$z_2 = 1 \to w_2 = i$ の適用**
   $z = 1$ を代入します：
   $$f(1) = \frac{k(1)-1}{k(1)+1} = \frac{k-1}{k+1} = i$$
   両辺に $k+1$ を掛けて整理します：
   $$k-1 = i(k+1) \implies k-1 = ik + i \implies k(1-i) = 1+i$$
   $$k = \frac{1+i}{1-i}$$
   分母を有理化するために分母・分子に $1+i$ を掛けます：
   $$k = \frac{(1+i)^2}{(1-i)(1+i)} = \frac{1 + 2i + i^2}{1 - i^2} = \frac{1 + 2i - 1}{1 - (-1)} = \frac{2i}{2} = i$$

5. **変換式の決定**
   $k = i$ を代入します：
   $$w = \frac{iz-1}{iz+1}$$
   （※分母分子に $-i$ を掛けると $w = \frac{z+i}{z-i}$ となり、これも同じ変換を表します。）

---

### 【問題5】の解答・解説
#### 解答
$$\frac{2}{3}\pi R^3$$

#### 詳細な計算ステップ
1. **球面のパラメータ化と法線ベクトル**
   上半球面 $S$ （$x^2+y^2+z^2 = R^2, \; z \ge 0$）を球面座標（球座標）を用いてパラメータ化します：
   * $x = R \sin\phi\cos\theta$
   * $y = R \sin\phi\sin\theta$
   * $z = R \cos\phi$
   
   パラメータの定義域は以下の通りです：
   * 水平角： $0 \le \theta \le 2\pi$
   * 天頂角： $0 \le \phi \le \frac{\pi}{2}$ （上半球面 $z \ge 0 \implies \cos\phi \ge 0$ より）
   
   球面の各点における外向き単位法線ベクトル $\mathbf{n}$ は、位置ベクトルを半径 $R$ で割ったものです：
   $$\mathbf{n} = \frac{1}{R}\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} \sin\phi\cos\theta \\ \sin\phi\sin\theta \\ \cos\phi \end{pmatrix}$$

2. **被積分関数の計算**
   ベクトル場 $\mathbf{F} = (0, 0, z) = (0, 0, R\cos\phi)$ と法線ベクトル $\mathbf{n}$ の内積を計算します：
   $$\mathbf{F} \cdot \mathbf{n} = \begin{pmatrix} 0 \\ 0 \\ R\cos\phi \end{pmatrix} \cdot \begin{pmatrix} \sin\phi\cos\theta \\ \sin\phi\sin\theta \\ \cos\phi \end{pmatrix} = R\cos^2\phi$$

3. **面積分の立式と計算**
   球面座標系における面積要素 $dS$ は $dS = R^2 \sin\phi \,d\phi\,d\theta$ です。面積分を累次積分に変形します：
   $$\iint_S \mathbf{F} \cdot \mathbf{n} \,dS = \int_0^{2\pi} \int_0^{\frac{\pi}{2}} (R\cos^2\phi)(R^2\sin\phi) \,d\phi\,d\theta = R^3 \int_0^{2\pi} d\theta \int_0^{\frac{\pi}{2}} \cos^2\phi \sin\phi \,d\phi$$
   * $\theta$ の積分：
     $$\int_0^{2\pi} d\theta = 2\pi$$
   * $\phi$ の積分：
     $t = \cos\phi$ とおくと、 $dt = -\sin\phi \,d\phi$ です。積分範囲は $\phi: 0 \to \frac{\pi}{2}$ のとき $t: 1 \to 0$ となります：
     $$\int_0^{\frac{\pi}{2}} \cos^2\phi \sin\phi \,d\phi = \int_1^0 t^2 (-dt) = \int_0^1 t^2 \,dt = \left[ \frac{t^3}{3} \right]_0^1 = \frac{1}{3}$$

4. **最終的な計算結果**
   $$\iint_S \mathbf{F} \cdot \mathbf{n} \,dS = R^3 \cdot 2\pi \cdot \frac{1}{3} = \frac{2}{3}\pi R^3$$

---

### 【問題6】の解答・解説
#### 証明
1. **環準同型写像 $\phi$ の定義**
   多項式環 $\mathbb{R}[x]$ から実数体 $\mathbb{R}$ への写像 $\phi$ を、 $x = 2$ を代入する写像として定義します：
   $$\phi: \mathbb{R}[x] \to \mathbb{R}, \quad \phi(p(x)) = p(2)$$
   多項式の和と積に対する代入の性質から、任意の $p(x), q(x) \in \mathbb{R}[x]$ について次が成り立ちます：
   * $\phi(p(x) + q(x)) = p(2) + q(2) = \phi(p(x)) + \phi(q(x))$
   * $\phi(p(x)q(x)) = p(2)q(2) = \phi(p(x))\phi(q(x))$
   * $\phi(1) = 1$
   したがって、 $\phi$ は環準同型写像です。

2. **全射性の証明**
   任意の実数 $r \in \mathbb{R}$ に対し、定数多項式 $g(x) = r \in \mathbb{R}[x]$ を考えると $\phi(g) = g(2) = r$ となるため、写像 $\phi$ は全射です。

3. **核（Kernel）の決定**
   準同型写像 $\phi$ の核を求めます：
   $$\operatorname{Ker}(\phi) = \{ p(x) \in \mathbb{R}[x] \mid \phi(p(x)) = 0 \} = \{ p(x) \in \mathbb{R}[x] \mid p(2) = 0 \}$$
   因数定理より、 $p(2) = 0$ であるための必要十分条件は $p(x)$ が一次式 $x-2$ で割り切れることです。
   これは、 $p(x)$ が $x-2$ によって生成される単項イデアル $I = (x-2)$ に属することと同値です：
   $$\operatorname{Ker}(\phi) = (x-2) = I$$

4. **同型と極大イデアルの証明**
   環の第一同型定理 $\mathbb{R}[x]/\operatorname{Ker}(\phi) \cong \operatorname{Im}(\phi)$ より、次の環同型が得られます：
   $$\mathbb{R}[x]/I \cong \mathbb{R}$$
   剰余環と同型である実数体 $\mathbb{R}$ は「体（field）」です。
   可換環論における一般的な定理「可換環 $R$ のイデアル $M$ について、剰余環 $R/M$ が体であることと、 $M$ が極大イデアルであることは必要十分条件である」を適用します。
   剰余環 $\mathbb{R}[x]/I$ は体 $\mathbb{R}$ と同型で体となるため、単項イデアル $I = (x-2)$ は $\mathbb{R}[x]$ の極大イデアルです。 (証明終)

---

### 【問題7】の解答・解説
#### 解答
* **共分散**： $\operatorname{Cov}(X, Y) = -0.12$
* **相関係数**： $\rho(X, Y) \approx -0.193$

#### 詳細な計算ステップ
1. **周辺分布の計算**
   同時確率 $P(X=x, Y=y)$ の表から、それぞれの周辺確率（各列・各行の合計）を計算します：
   * **$X$ の周辺分布**（列の合計）：
     * $P(X=-1) = 0.1 \text{ (row 0)} + 0.2 \text{ (row 1)} + 0.1 \text{ (row 2)} = 0.4$
     * $P(X=0) = 0.2 \text{ (row 0)} + 0.0 \text{ (row 1)} + 0.1 \text{ (row 2)} = 0.3$
     * $P(X=1) = 0.1 \text{ (row 0)} + 0.2 \text{ (row 1)} + 0.0 \text{ (row 2)} = 0.3$
   * **$Y$ の周辺分布**（行の合計）：
     * $P(Y=0) = 0.1 \text{ (col -1)} + 0.2 \text{ (col 0)} + 0.1 \text{ (col 1)} = 0.4$
     * $P(Y=1) = 0.2 \text{ (col -1)} + 0.0 \text{ (col 0)} + 0.2 \text{ (col 1)} = 0.4$
     * $P(Y=2) = 0.1 \text{ (col -1)} + 0.1 \text{ (col 0)} + 0.0 \text{ (col 1)} = 0.2$

2. **期待値と分散の計算**
   * **$X$ の期待値と分散**：
     $$E[X] = (-1)(0.4) + 0(0.3) + 1(0.3) = -0.1$$
     $$E[X^2] = (-1)^2(0.4) + 0^2(0.3) + 1^2(0.3) = 0.4 + 0.3 = 0.7$$
     $$V[X] = E[X^2] - (E[X])^2 = 0.7 - (-0.1)^2 = 0.69 \implies \sigma_X = \sqrt{0.69} \approx 0.83066$$
   * **$Y$ の期待値と分散**：
     $$E[Y] = 0(0.4) + 1(0.4) + 2(0.2) = 0.8$$
     $$E[Y^2] = 0^2(0.4) + 1^2(0.4) + 2^2(0.2) = 1.2$$
     $$V[Y] = E[Y^2] - (E[Y])^2 = 1.2 - (0.8)^2 = 0.56 \implies \sigma_Y = \sqrt{0.56} \approx 0.74833$$

3. **積の期待値 $E[XY]$ の計算**
     $$E[XY] = \sum x y P(X=x, Y=y)$$
     $x = 0$ または $y = 0$ の項は $0$ となるため、 $x \neq 0$ かつ $y \neq 0$ のセルのみを計算します：
     * $X = -1, Y = 1$： $(-1)(1)(0.2) = -0.2$
     * $X = -1, Y = 2$： $(-1)(2)(0.1) = -0.2$
     * $X = 1, Y = 1$： $(1)(1)(0.2) = 0.2$
     * $X = 1, Y = 2$： $(1)(2)(0.0) = 0$
     
     これらを足し合わせます：
     $$E[XY] = -0.2 - 0.2 + 0.2 = -0.2$$

4. **共分散と相関係数の計算**
   * **共分散 $\operatorname{Cov}(X, Y)$**：
     $$\operatorname{Cov}(X, Y) = E[XY] - E[X]E[Y] = -0.2 - (-0.1)(0.8) = -0.2 + 0.08 = -0.12$$
   * **相関係数 $\rho(X, Y)$**：
     $$\rho(X, Y) = \frac{\operatorname{Cov}(X, Y)}{\sigma_X \sigma_Y} = \frac{-0.12}{\sqrt{0.69 \times 0.56}} = \frac{-0.12}{\sqrt{0.3864}}$$
     $\sqrt{0.3864} \approx 0.62161$ なので：
     $$\rho(X, Y) \approx \frac{-0.12}{0.62161} \approx -0.19304$$
     四捨五入して小数第3位まで求めると：
     $$\rho(X, Y) \approx -0.193$$

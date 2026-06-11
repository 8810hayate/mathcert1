# 数学検定1級 範囲網羅・総合問題セット（解答解説付き）

数学検定1級（一次試験および二次試験）の出題範囲を広くカバーする全11問の総合演習問題セットです。線形代数、微積分、複素解析、微分方程式、ベクトル解析、整数論、確率・統計、抽象代数学（群論）から重要テーマを網羅しています。

---

## 網羅する分野と問題一覧

* **【問題1】線形代数**：ジョルダン標準形と変換行列の決定
* **【問題2】線形代数**：線形写像の表現行列・核（Kernel）と像（Image）の基底と次元
* **【問題3】微分積分**：多変数関数の極値問題（ラグランジュの未定乗数法・条件付き極値）
* **【問題4】微分積分**：広義積分・ベータ関数とガンマ関数の関係
* **【問題5】複素解析**：留数定理を利用した実関数の広義積分
* **&nbsp;【問題6】微分方程式**：定数係数2階非同次線形常微分方程式（未定係数法）
* **【問題7】ベクトル解析**：グリーンの定理を用いた線積分の計算
* **【問題8】整数論**：オイラーの定理と中国式剰余定理（合同式の計算）
* **【問題9】確率論**：連続型確率変数（指数分布）の累積分布関数・期待値・分散の導出
* **【問題10】統計学**：正規分布における母平均の仮説検定（両側検定）
* **【問題11】群論**：部分群の共通部分に関する証明とラグランジュの定理の応用

---

## 演習問題

### 【問題1】線形代数（ジョルダン標準形）
次の行列 $A$ のジョルダン標準形 $J$、および $P^{-1}AP = J$ を満たす正則行列 $P$ を求めよ。
$$A = \begin{pmatrix} 3 & 1 & 0 \\ -1 & 1 & 0 \\ 0 & 0 & 2 \end{pmatrix}$$

### 【問題2】線形代数（線形写像の核と像）
線形写像 $f: \mathbb{R}^3 \to \mathbb{R}^3$ を以下のように定義する。
$$f\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} x + 2y - z \\ 2x + 3y + z \\ 3x + 5y \end{pmatrix}$$
このとき、以下を求めよ。
1. $f$ の階数（rank）
2. $f$ の像 $\operatorname{Im}(f)$ の基底の1組
3. $f$ の核 $\operatorname{Ker}(f)$ の基底の1組

### 【問題3】微分積分（ラグランジュの未定乗数法）
制約条件 $x^2 + y^2 + z^2 = 1$ および $x + y + z = 0$ のもとで、3変数関数 $f(x, y, z) = xyz$ の最大値と最小値を求めよ。

### 【問題4】微分積分（特殊関数）
次の定積分を計算せよ。
$$I = \int_0^1 x^3 (1-x^2)^{3/2} \,dx$$

### 【問題5】複素解析（留数定理）
留数定理を用いて、次の広義積分を求めよ。
$$I = \int_{-\infty}^{\infty} \frac{x^2}{(x^2+1)(x^2+9)} \,dx$$

### 【問題6】微分方程式（2階線形）
次の微分方程式の一般解を求めよ。
$$y'' - 4y' + 4y = e^{2x} + \sin x$$

### 【問題7】ベクトル解析（グリーンの定理）
$xy$ 平面上の領域 $D$ を放物線 $y = x^2$ と $x = y^2$ で囲まれた領域とする。$D$ の境界 $C$ を反時計回りに1周するとき、次の線積分を計算せよ。
$$\oint_C \left( (y + e^{\sqrt{x}}) \,dx + (2x + \cos(y^2)) \,dy \right)$$

### 【問題8】整数論（合同式）
$13^{2026}$ を $35$ で割ったときの余りを求めよ。

### 【問題9】確率論（確率分布）
パラメータ（ハザード率） $\lambda > 0$ を持つ指数分布に従う連続型確率変数 $X$ の確率密度関数 $f(x)$ は以下で与えられる。
$$f(x) = \begin{cases} \lambda e^{-\lambda x} & (x \ge 0) \\ 0 & (x < 0) \end{cases}$$
このとき、以下を計算せよ。
1. 累積分布関数 $F(x) = P(X \le x)$
2. 期待値 $E[X]$
3. 分散 $V[X]$

### 【問題10】統計学（仮説検定）
ある製品の長さは標準偏差 $\sigma = 0.2\text{ cm}$ の正常分布に従うことが知られている。機械の調整状態を確認するため、ランダムに 100 個の製品を抽出して測定したところ、標本平均は $\bar{x} = 10.05\text{ cm}$ であった。
機械の設定基準である母平均 $\mu_0 = 10.00\text{ cm}$ に対し、「母平均は基準と異なる（$\mu \neq 10.00$）」と言えるか、有意水準 $5\%$ で両側検定を行え。
ただし、標準正規分布の上側 $2.5\%$ 点を $z_{0.025} = 1.96$ とし、検定統計量の数値を明記して結論を述べよ。

### 【問題11】群論（代数学・証明問題）
$G$ を群とし、$H$ と $K$ を $G$ の部分群とする。
1. 共通部分 $H \cap K$ も $G$ の部分群であることを証明せよ。
2. $H$ の位数が 12、$K$ の位数が 35 であるとき、$H \cap K = \{e\}$ （$e$ は $G$ の単位元）となることを証明せよ。

---
---

## 解答・解説

### 【問題1】の解答・解説
#### 解答
$$J = \begin{pmatrix} 2 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix}, \quad P = \begin{pmatrix} 1 & 1 & 0 \\ -1 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}$$
※ $P$ の取り方は一意ではありませんが、積 $AP = PJ$ を満たす必要があります。

#### 解説
1. **固有値の算出**
   行列 $A$ の固有多項式を計算します。
   $$\det(A - \lambda I) = \begin{vmatrix} 3-\lambda & 1 & 0 \\ -1 & 1-\lambda & 0 \\ 0 & 0 & 2-\lambda \end{vmatrix} = (2-\lambda) \begin{vmatrix} 3-\lambda & 1 \\ -1 & 1-\lambda \end{vmatrix}$$
   $$= (2-\lambda)((3-\lambda)(1-\lambda) + 1) = (2-\lambda)(\lambda^2 - 4\lambda + 4) = (2-\lambda)(\lambda-2)^2 = -(\lambda-2)^3$$
   したがって、固有値は $\lambda = 2$ （重複度 3）となります。

2. **固有空間の次元（幾何学的重複度）の確認**
   $$\operatorname{rank}(A - 2I) = \operatorname{rank} \begin{pmatrix} 1 & 1 & 0 \\ -1 & -1 & 0 \\ 0 & 0 & 0 \end{pmatrix} = 1$$
   次元定理より、固有空間の次元（固有ベクトルの自由度）は $3 - 1 = 2$ となり、ジョルダン細胞の個数は 2 個（サイズ 2 が 1 つ、サイズ 1 が 1 つ）になります。
   したがって、ジョルダン標準形は次の通りです。
   $$J = \begin{pmatrix} 2 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix}$$

3. **変換行列 $P = (\mathbf{p}_1, \mathbf{p}_2, \mathbf{p}_3)$ の決定**
   $AP = PJ$ より、各列ベクトルに関して以下の関係式が成り立ちます。
   * $A\mathbf{p}_1 = 2\mathbf{p}_1 \implies (A-2I)\mathbf{p}_1 = \mathbf{0}$
   * $A\mathbf{p}_2 = \mathbf{p}_1 + 2\mathbf{p}_2 \implies (A-2I)\mathbf{p}_2 = \mathbf{p}_1$
   * $A\mathbf{p}_3 = 2\mathbf{p}_3 \implies (A-2I)\mathbf{p}_3 = \mathbf{0}$

   $(A-2I)\mathbf{p}_2 = \mathbf{p}_1$ を満たすためには、$\mathbf{p}_1$ が $A-2I$ の値域に含まれている必要があります。
   $$A-2I = \begin{pmatrix} 1 & 1 & 0 \\ -1 & -1 & 0 \\ 0 & 0 & 0 \end{pmatrix} \implies \text{値域の基底は} \begin{pmatrix} 1 \\ -1 \\ 0 \end{pmatrix}$$
   よって、固有ベクトル $\mathbf{p}_1$ として $\mathbf{p}_1 = \begin{pmatrix} 1 \\ -1 \\ 0 \end{pmatrix}$ を選択します。
   このとき、$(A-2I)\mathbf{p}_2 = \mathbf{p}_1$ は以下の通りです。
   $$\begin{pmatrix} 1 & 1 & 0 \\ -1 & -1 & 0 \\ 0 & 0 & 0 \end{pmatrix} \begin{pmatrix} y_1 \\ y_2 \\ y_3 \end{pmatrix} = \begin{pmatrix} 1 \\ -1 \\ 0 \end{pmatrix} \implies y_1 + y_2 = 1$$
   ここで $y_1 = 1, y_2 = 0, y_3 = 0$ とすれば、広義固有ベクトル $\mathbf{p}_2 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$ が得られます。
   また、$\mathbf{p}_3$ は $\mathbf{p}_1$ と線形独立な固有ベクトル（$A-2I$ の核の元）として、$\mathbf{p}_3 = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$ を選べます。
   以上より、正則行列 $P$ は以下になります。
   $$P = \begin{pmatrix} 1 & 1 & 0 \\ -1 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}$$

---

### 【問題2】の解答・解説
#### 解答
1. $\operatorname{rank}(f) = 2$
2. $\operatorname{Im}(f)$ の基底： $\left\{ \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}, \begin{pmatrix} 2 \\ 3 \\ 5 \end{pmatrix} \right\}$
3. $\operatorname{Ker}(f)$ の基底： $\left\{ \begin{pmatrix} -5 \\ 3 \\ 1 \end{pmatrix} \right\}$

#### 解説
標準基底に対する表現行列 $A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 3 & 1 \\ 3 & 5 & 0 \end{pmatrix}$ を行基本変形します。

第1列の掃き出し：
$$\begin{pmatrix} 1 & 2 & -1 \\ 2 & 3 & 1 \\ 3 & 5 & 0 \end{pmatrix} \xrightarrow{\text{第2行}-2\times\text{第1行}, \text{第3行}-3\times\text{第1行}} \begin{pmatrix} 1 & 2 & -1 \\ 0 & -1 & 3 \\ 0 & -1 & 3 \end{pmatrix}$$

第2列の掃き出し：
$$\xrightarrow{\text{第2行}\times(-1)} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & -3 \\ 0 & -1 & 3 \end{pmatrix} \xrightarrow{\text{第1行}-2\times\text{第2行}, \text{第3行}+\text{第2行}} \begin{pmatrix} 1 & 0 & 5 \\ 0 & 1 & -3 \\ 0 & 0 & 0 \end{pmatrix}$$

1. **階数の決定**
   行基本変形結果の非ゼロ行数が 2 であるため、$\operatorname{rank}(f) = 2$ です。
2. **$\operatorname{Im}(f)$ の基底**
   元の行列 $A$ の第1列と第2列（ピボットがある列）が線形独立なベクトルとなり、像の基底を構成します。
   $$\operatorname{Im}(f) \text{の基底} = \left\{ \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}, \begin{pmatrix} 2 \\ 3 \\ 5 \end{pmatrix} \right\}$$
3. **$\operatorname{Ker}(f)$ の基底**
   $A\mathbf{x} = \mathbf{0}$ を解きます。変形後の階段行列より、
   $$x + 5z = 0 \implies x = -5z$$
   $$y - 3z = 0 \implies y = 3z$$
   $z = t$ とおくと、$\mathbf{x} = t \begin{pmatrix} -5 \\ 3 \\ 1 \end{pmatrix}$ となるため、核の基底は以下となります。
   $$\operatorname{Ker}(f) \text{の基底} = \left\{ \begin{pmatrix} -5 \\ 3 \\ 1 \end{pmatrix} \right\}$$

---

### 【問題3】の解答・解説
#### 解答
最大値： $\frac{\sqrt{6}}{18}$、 最小値： $-\frac{\sqrt{6}}{18}$

#### 解説
ラグランジュの未定乗数法を用います。制約条件を $g(x,y,z) = x^2+y^2+z^2-1 = 0$, $h(x,y,z) = x+y+z = 0$ とおき、ラグランジュ関数 $L$ を以下のように設定します。
$$L(x, y, z, \lambda, \mu) = xyz - \lambda(x^2 + y^2 + z^2 - 1) - \mu(x + y + z)$$

各変数について偏微分して $0$ とおきます。
1. $\frac{\partial L}{\partial x} = yz - 2\lambda x - \mu = 0 \implies yz = 2\lambda x + \mu$
2. $\frac{\partial L}{\partial y} = xz - 2\lambda y - \mu = 0 \implies xz = 2\lambda y + \mu$
3. $\frac{\partial L}{\partial z} = xy - 2\lambda z - \mu = 0 \implies xy = 2\lambda z + \mu$

(1) $-$ (2) より：
$$z(y - x) = 2\lambda(x - y) \implies (x - y)(2\lambda + z) = 0$$
同様に、(2) $-$ (3) および (3) $-$ (1) より：
$$(y - z)(2\lambda + x) = 0$$
$$(z - x)(2\lambda + y) = 0$$

もし $x, y, z$ がすべて互いに異なるならば、$2\lambda + z = 0$ かつ $2\lambda + x = 0$ となり、$x = z$ となって矛盾します。
したがって、極値を与える点では、**少なくとも2つの変数が等しい**必要があります。

対称性より、$x = y$ と仮定します。
制約条件 $x + y + z = 0$ に代入すると、 $2x + z = 0 \implies z = -2x$。
これをもう1つの制約条件 $x^2 + y^2 + z^2 = 1$ に代入します。
$$x^2 + x^2 + (-2x)^2 = 1 \implies 6x^2 = 1 \implies x = \pm \frac{1}{\sqrt{6}}$$

* **ケースA： $x = \frac{1}{\sqrt{6}}$ のとき**
  $$y = \frac{1}{\sqrt{6}}, \quad z = -\frac{2}{\sqrt{6}}$$
  このとき、関数の値は次のようになります。
  $$f(x, y, z) = \left(\frac{1}{\sqrt{6}}\right) \left(\frac{1}{\sqrt{6}}\right) \left(-\frac{2}{\sqrt{6}}\right) = -\frac{2}{6\sqrt{6}} = -\frac{\sqrt{6}}{18}$$

* **ケースB： $x = -\frac{1}{\sqrt{6}}$ のとき**
  $$y = -\frac{1}{\sqrt{6}}, \quad z = \frac{2}{\sqrt{6}}$$
  このとき、関数の値は次のようになります。
  $$f(x, y, z) = \left(-\frac{1}{\sqrt{6}}\right) \left(-\frac{1}{\sqrt{6}}\right) \left(\frac{2}{\sqrt{6}}\right) = \frac{2}{6\sqrt{6}} = \frac{\sqrt{6}}{18}$$

変数 $y=z$ または $z=x$ の場合も対称性から同様の値を持ちます。
したがって、最大値は $\frac{\sqrt{6}}{18}$、最小値は $-\frac{\sqrt{6}}{18}$ です。

---

### 【問題4】の解答・解説
#### 解答
$$I = \frac{2}{35}$$

#### 解説
置換積分により、積分をベータ関数（Beta function）の形に変形します。
$u = x^2$ とおくと、$du = 2x \,dx \implies x \,dx = \frac{1}{2} \,du$ となります。
積分範囲は $x: 0 \to 1$ に対し $u: 0 \to 1$ です。

$$I = \int_0^1 x^2 (1-x^2)^{3/2} (x\,dx) = \int_0^1 u (1-u)^{3/2} \left(\frac{1}{2}\,du\right) = \frac{1}{2} \int_0^1 u^{2-1} (1-u)^{\frac{5}{2}-1} \,du$$
これはベータ関数 $B\left(2, \frac{5}{2}\right)$ の定義式そのものです。
$$I = \frac{1}{2} B\left(2, \frac{5}{2}\right)$$

ベータ関数とガンマ関数の関係式 $B(p, q) = \frac{\Gamma(p)\Gamma(q)}{\Gamma(p+q)}$ を利用します。
* $\Gamma(2) = 1! = 1$
* $\Gamma\left(\frac{5}{2}\right) = \frac{3}{2} \cdot \frac{1}{2} \Gamma\left(\frac{1}{2}\right) = \frac{3}{4} \sqrt{\pi}$
* $\Gamma\left(2 + \frac{5}{2}\right) = \Gamma\left(\frac{9}{2}\right) = \frac{7}{2} \cdot \frac{5}{2} \cdot \frac{3}{2} \cdot \frac{1}{2} \Gamma\left(\frac{1}{2}\right) = \frac{105}{16} \sqrt{\pi}$

これらを代入します。
$$B\left(2, \frac{5}{2}\right) = \frac{1 \cdot \frac{3}{4}\sqrt{\pi}}{\frac{105}{16}\sqrt{\pi}} = \frac{3}{4} \cdot \frac{16}{105} = \frac{4}{35}$$
したがって、求める積分値は以下となります。
$$I = \frac{1}{2} \cdot \frac{4}{35} = \frac{2}{35}$$

---

### 【問題5】の解答・解説
#### 解答
$$I = \frac{\pi}{4}$$

#### 解説
複素関数 $f(z) = \frac{z^2}{(z^2+1)(z^2+9)}$ を定義し、上半平面の半円経路（実数軸上の $-R \to R$ および半径 $R$ の半円弧 $C_R$）に沿った閉曲線 $C$ で積分します。

1. **極の選定**
   分母 $(z^2+1)(z^2+9) = 0$ の解は $z = \pm i, \pm 3i$ です。
   このうち、上半平面 ($\operatorname{Im}(z) > 0$) に含まれる単純極（1位の極）は $z = i$ と $z = 3i$ の2つです。

2. **留数の計算**
   * **$z = i$ における留数**
     $$\operatorname{Res}(f, i) = \lim_{z \to i} (z-i) \frac{z^2}{(z-i)(z+i)(z^2+9)} = \frac{i^2}{(2i)(i^2+9)} = \frac{-1}{2i(8)} = \frac{i}{16}$$
   * **$z = 3i$ における留数**
     $$\operatorname{Res}(f, 3i) = \lim_{z \to 3i} (z-3i) \frac{z^2}{(z^2+1)(z-3i)(z+3i)} = \frac{(3i)^2}{((3i)^2+1)(6i)} = \frac{-9}{(-8)(6i)} = \frac{3}{16i} = -\frac{3i}{16}$$

3. **留数定理の適用**
   $$\oint_C f(z) \,dz = 2\pi i (\operatorname{Res}(f, i) + \operatorname{Res}(f, 3i)) = 2\pi i \left( \frac{i}{16} - \frac{3i}{16} \right) = 2\pi i \left( -\frac{i}{8} \right) = \frac{\pi}{4}$$

4. **半円弧の極限**
   $R \to \infty$ のとき、被積分関数の次数評価（分母4次、分子2次）より $|f(z)| \sim O(R^{-2})$ となり、ジョルダンの補題（または直接の不等式評価）より $\int_{C_R} f(z) \,dz \to 0$ となります。
   したがって、求める広義積分は以下になります。
   $$I = \int_{-\infty}^{\infty} \frac{x^2}{(x^2+1)(x^2+9)} \,dx = \frac{\pi}{4}$$

---

### 【問題6】の解答・解説
#### 解答
$$y = (C_1 + C_2 x)e^{2x} + \frac{1}{2} x^2 e^{2x} + \frac{4}{25}\cos x + \frac{3}{25}\sin x \quad (C_1, C_2 \text{は任意定数})$$

#### 解説
非同次方程式 $y'' - 4y' + 4y = e^{2x} + \sin x$ を重ね合わせの原理を用いて解きます。

1. **同次方程式の一般解 $y_h$**
   特性方程式は $r^2 - 4r + 4 = 0 \implies (r-2)^2 = 0$ より、重解 $r=2$ を持ちます。
   $$y_h = (C_1 + C_2 x)e^{2x}$$

2. **非同次項 $e^{2x}$ に対する特解 $y_{p1}$**
   $e^{2x}$ は同次方程式の解（特性方程式の2重根に対応）であるため、特解の形を次のように仮定します。
   $$y_{p1} = A x^2 e^{2x}$$
   微分を計算します。
   $$y_{p1}' = A(2x + 2x^2)e^{2x}$$
   $$y_{p1}'' = A(2 + 8x + 4x^2)e^{2x}$$
   これらを方程式の左辺に代入します。
   $$y_{p1}'' - 4y_{p1}' + 4y_{p1} = A e^{2x} [ (2+8x+4x^2) - 4(2x+2x^2) + 4x^2 ] = 2A e^{2x}$$
   これが $e^{2x}$ と一致することから、 $2A = 1 \implies A = \frac{1}{2}$。
   $$y_{p1} = \frac{1}{2} x^2 e^{2x}$$

3. **非同次項 $\sin x$ に対する特解 $y_{p2}$**
   特解の形を $y_{p2} = B \cos x + C \sin x$ と仮定します。
   $$y_{p2}' = -B \sin x + C \cos x$$
   $$y_{p2}'' = -B \cos x - C \sin x$$
   これらを方程式に代入して整理します。
   $$(-B \cos x - C \sin x) - 4(-B \sin x + C \cos x) + 4(B \cos x + C \sin x) = \sin x$$
   $$(3B - 4C)\cos x + (4B + 3C)\sin x = \sin x$$
   係数を比較して連立方程式を解きます。
   $$\begin{cases} 3B - 4C = 0 \\ 4B + 3C = 1 \end{cases} \implies B = \frac{4}{25}, \quad C = \frac{3}{25}$$
   $$y_{p2} = \frac{4}{25}\cos x + \frac{3}{25}\sin x$$

4. **一般解の合成**
   $$y = y_h + y_{p1} + y_{p2} = (C_1 + C_2 x)e^{2x} + \frac{1}{2} x^2 e^{2x} + \frac{4}{25}\cos x + \frac{3}{25}\sin x$$

---

### 【問題7】の解答・解説
#### 解答
$$\frac{1}{3}$$

#### 解説
グリーンの定理（Green's Theorem）を適用します。与えられた線積分において、
$$P(x,y) = y + e^{\sqrt{x}}, \quad Q(x,y) = 2x + \cos(y^2)$$
とおきます。偏導関数を計算すると、
$$\frac{\partial P}{\partial y} = 1, \quad \frac{\partial Q}{\partial x} = 2$$
グリーンの定理より：
$$\oint_C (P\,dx + Q\,dy) = \iint_D \left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right) \,dx\,dy = \iint_D (2 - 1) \,dx\,dy = \iint_D 1 \,dx\,dy$$
これは領域 $D$ の面積そのものです。
領域 $D$ の境界は $y = x^2$ と $x = y^2 \implies y = \sqrt{x}$ （$x \ge 0$）であり、交点は $(0,0)$ と $(1,1)$ です。
したがって、面積は次のように計算できます。
$$\iint_D 1 \,dx\,dy = \int_0^1 \left( \sqrt{x} - x^2 \right) \,dx = \left[ \frac{2}{3}x^{3/2} - \frac{1}{3}x^3 \right]_0^1 = \frac{2}{3} - \frac{1}{3} = \frac{1}{3}$$

---

### 【問題8】の解答・解説
#### 解答
$$29$$

#### 解説
$35 = 5 \times 7$ であり、互いに素な法であるため、中国式剰余定理（CRT）とフェルマーの小定理を用いて解きます。

1. **法 5 について**
   $$13 \equiv 3 \equiv -2 \pmod 5$$
   フェルマーの小定理より $13^4 \equiv 1 \pmod 5$ です。指数を 4 で割った余りを考えます。
   $$2026 = 4 \times 506 + 2 \implies 13^{2026} \equiv 13^2 \equiv (-2)^2 = 4 \pmod 5$$

2. **法 7 について**
   $$13 \equiv 6 \equiv -1 \pmod 7$$
   より、指数計算は直接行えます。
   $$13^{2026} \equiv (-1)^{2026} = 1 \pmod 7$$

3. **連立合同式の解消**
   求める余りを $x$ とします。
   * $x \equiv 4 \pmod 5$
   * $x \equiv 1 \pmod 7$

   第2式より $x = 7k + 1$ （$k$ は整数）とおき、第1式に代入します。
   $$7k + 1 \equiv 4 \pmod 5 \implies 2k \equiv 3 \equiv 8 \pmod 5 \implies k \equiv 4 \pmod 5$$
   したがって、$k = 5m + 4$ （$m$ は整数）となります。
   $$x = 7(5m + 4) + 1 = 35m + 29$$
   よって、求める余りは **29** となります。
   ※なお、オイラーの定理から直接 $\phi(35) = 24$ を求めて $13^{24} \equiv 1 \pmod{35}$ より $13^{10} \pmod{35}$ を計算することも可能です。

---

### 【問題9】の解答・解説
#### 解答
1. $F(x) = \begin{cases} 1 - e^{-\lambda x} & (x \ge 0) \\ 0 & (x < 0) \end{cases}$
2. $E[X] = \frac{1}{\lambda}$
3. $V[X] = \frac{1}{\lambda^2}$

#### 解説
1. **累積分布関数 $F(x)$**
   $x < 0$ のときは $F(x) = 0$ です。 $x \ge 0$ においては、
   $$F(x) = \int_0^x \lambda e^{-\lambda t} \,dt = \left[ -e^{-\lambda t} \right]_0^x = 1 - e^{-\lambda x}$$

2. **期待値 $E[X]$**
   部分積分を行います。
   $$E[X] = \int_0^{\infty} x \cdot \lambda e^{-\lambda x} \,dx = \left[ -x e^{-\lambda x} \right]_0^{\infty} - \int_0^{\infty} (-e^{-\lambda x}) \,dx$$
   $$= 0 + \left[ -\frac{1}{\lambda} e^{-\lambda x} \right]_0^{\infty} = \frac{1}{\lambda}$$

3. **分散 $V[X]$**
   $V[X] = E[X^2] - (E[X])^2$ を利用するため、まず2次モーメント $E[X^2]$ を求めます。
   $$E[X^2] = \int_0^{\infty} x^2 \cdot \lambda e^{-\lambda x} \,dx = \left[ -x^2 e^{-\lambda x} \right]_0^{\infty} - \int_0^{\infty} 2x (-e^{-\lambda x}) \,dx$$
   $$= 0 + \frac{2}{\lambda} \int_0^{\infty} x \lambda e^{-\lambda x} \,dx = \frac{2}{\lambda} E[X] = \frac{2}{\lambda^2}$$
   したがって、分散は次の通りです。
   $$V[X] = E[X^2] - (E[X])^2 = \frac{2}{\lambda^2} - \left(\frac{1}{\lambda}\right)^2 = \frac{1}{\lambda^2}$$

---

### 【問題10】の解答・解説
#### 解答
* **検定統計量（実現値）**： $Z = 2.50$
* **判定**： 帰無仮説 $H_0$ は棄却され、「母平均は基準（10.00 cm）と異なる」と判断される。

#### 解説
1. **仮説の設定**
   * 帰無仮説 $H_0: \mu = 10.00$ （製品の平均長さは基準通り）
   * 対立仮説 $H_1: \mu \neq 10.00$ （製品の平均長さは基準と異なる）

2. **検定統計量の選定と計算**
   母分散 $\sigma^2 = 0.2^2$ は既知であり、サンプルサイズ $n = 100$ は十分に大きいため、標本平均 $\bar{X}$ の標準化変数は標準正規分布に従います。
   $$Z = \frac{\bar{x} - \mu_0}{\sigma / \sqrt{n}}$$
   与えられた数値を代入します。
   $$Z = \frac{10.05 - 10.00}{0.2 / \sqrt{100}} = \frac{0.05}{0.02} = 2.5$$

3. **棄却限界値との比較**
   有意水準 $\alpha = 0.05$ の両側検定における棄却域は $|Z| \ge 1.96$ です。
   計算された検定統計量は $|Z| = 2.5 \ge 1.96$ となり、棄却域に入ります。

4. **結論**
   帰無仮説 $H_0$ を棄却し、対立仮説 $H_1$ を採択します。したがって、「有意水準 5% において、製品の平均長さは基準の 10.00 cm と有意に異なる」と結論づけられます。

---

### 【問題11】の解答・解説
#### 証明
1. **共通部分が部分群であることの証明**
   部分群の判定条件「(i) 単位元 $e$ を含む」「(ii) 積について閉じている」「(iii) 逆元について閉じている」を示します。
   * **(i)** $H, K$ は $G$ の部分群なので、$e \in H$ かつ $e \in K$ です。したがって $e \in H \cap K$ となり、$H \cap K \neq \emptyset$ です。
   * **(ii), (iii)** $x, y \in H \cap K$ とします。
     このとき $x, y \in H$ かつ $x, y \in K$ です。
     $H$ は部分群なので $xy^{-1} \in H$ です。同様に $K$ も部分群なので $xy^{-1} \in K$ です。
     したがって、 $xy^{-1} \in H \cap K$ となります。
   * 以上より、 $H \cap K$ は $G$ の部分群です。

2. **$H \cap K = \{e\}$ であることの証明**
   * (1) より、 $H \cap K$ は $G$ の部分群です。
   * また、$H \cap K \subset H$ かつ $H \cap K \subset K$ なので、 $H \cap K$ は $H$ の部分群であり、同時に $K$ の部分群でもあります。
   * ラグランジュの定理（Lagrange's Theorem）より、部分群の位数は元の群の位数を割り切る必要があります。
     * $|H \cap K|$ は $|H| = 12$ の約数。
     * $|H \cap K|$ は $|K| = 35$ の約数。
   * したがって、$|H \cap K|$ は 12 と 35 の公約数、すなわち最大公約数 $\gcd(12, 35)$ の約数でなければなりません。
   * $12 = 2^2 \times 3$ と $35 = 5 \times 7$ は互いに素であるため、 $\gcd(12, 35) = 1$ です。
   * 位数は正の整数なので、 $|H \cap K| = 1$ と決定されます。
   * 部分群は必ず単位元 $e$ を含むため、 $H \cap K = \{e\}$ となります。 (証明終)

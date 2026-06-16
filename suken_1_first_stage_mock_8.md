# 数学検定1級 一次試験（計算技能）模擬試験［第8回］

数学検定1級一次試験（計算技能）対策のための、第8回模擬試験問題（全7問）と詳細な解答解説です。今回の模擬試験では、試験で差がつきやすい高度な計算問題を集中的に扱います（テイラー展開を用いた極限、グラム・シュミットの直交化法、完全微分方程式、複素線積分による直接計算、ストークスの定理、合同式における位数と剰余、指数分布のモーメント母関数）。

---

## 模擬試験問題（制限時間：60分）

### 【問題1】微分積分学（テイラー展開と不定形の極限）
次の極限値を求めよ。
$$L = \lim_{x \to 0} \frac{\cos x - e^{-x^2/2}}{x^4}$$

### 【問題2】線形代数（グラム・シュミットの直交化法）
$\mathbb{R}^3$ の次の 3つの一次独立なベクトル $\mathbf{u}_1, \mathbf{u}_2, \mathbf{u}_3$ を、グラム・シュミットの直交化法を用いて正規直交化し、正規直交基底 $\{\mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3\}$ を求めよ。
$$\mathbf{u}_1 = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}, \quad \mathbf{u}_2 = \begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix}, \quad \mathbf{u}_3 = \begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix}$$

### 【問題3】微分方程式（完全微分方程式）
次の微分方程式の一般解を求めよ。
$$(3x^2 + 2y^2) \,dx + (4xy + 6y^2) \,dy = 0$$

### 【問題4】複素解析（複素線積分・非正則関数の経路積分）
被積分関数 $f(z) = \bar{z}$ （複素共役）について、実軸上の $0$ から出発し、 $1 \to 1+i \to i$ を通り、 $0$ に戻る正方形の閉経路 $C$ （反時計回り）に沿った複素線積分 $\oint_C \bar{z} \,dz$ の値を求めよ。

### 【問題5】ベクトル解析（ストークスの定理）
ベクトル場 $\mathbf{F}(x, y, z) = (y, \; z, \; x)$ に対し、 $C$ を第1象限（$x, y, z \ge 0$）にある平面 $x + y + z = 1$ の境界（三角形の辺）とし、 $xy$ 平面上から見て反時計回り（正の向き）に方向づける。ストークスの定理を用いて、次の線積分の値を求めよ。
$$I = \oint_C (y \,dx + z \,dy + x \,dz)$$

◎### 【問題6】代数学・整数論（合同式の周期と剰余）
$7^{2026}$ の下2桁（100で割った余り）を求めよ。

### 【問題7】確率・統計（モーメント母関数とモーメント）
確率変数 $X$ の確率密度関数 $f(x)$ が、パラメータ $\lambda > 0$ を持つ次の指数分布に従うとする。
$$f(x) = \begin{cases} \lambda e^{-\lambda x} & (x \ge 0) \\ 0 & (x < 0) \end{cases}$$
1. $X$ のモーメント母関数 $M_X(t) = E[e^{tX}]$ を求めよ（ただし $t < \lambda$ とする）。
2. モーメント母関数の微分を利用して、 $X$ の3次モーメントの期待値 $E[X^3]$ を求めよ。

---
---

## 解答・解説

### 【問題1】の解答・解説
#### 解答
$$L = -\frac{1}{12}$$

#### 詳細な計算ステップ
1. **マクローリン展開（$x=0$ 付近でのテイラー展開）の適用**
   被積分関数の極限を求めるため、各項を $x=0$ の周りで展開します。
   * $\cos x$ のマクローリン展開：
     $$\cos x = 1 - \frac{x^2}{2} + \frac{x^4}{24} + O(x^6)$$
   * $e^t$ のマクローリン展開は $e^t = 1 + t + \frac{t^2}{2} + O(t^3)$ なので、 $t = -\frac{x^2}{2}$ とおくと：
     $$e^{-x^2/2} = 1 + \left(-\frac{x^2}{2}\right) + \frac{1}{2}\left(-\frac{x^2}{2}\right)^2 + O(x^6) = 1 - \frac{x^2}{2} + \frac{x^4}{8} + O(x^6)$$

2. **分子の差の計算**
   展開式を代入し、 $x^4$ までの項を計算します。 $1$ と $x^2$ の項が相殺されることがわかります：
   $$\cos x - e^{-x^2/2} = \left( 1 - \frac{x^2}{2} + \frac{x^4}{24} \right) - \left( 1 - \frac{x^2}{2} + \frac{x^4}{8} \right) + O(x^6)$$
   $$= \left( \frac{1}{24} - \frac{1}{8} \right) x^4 + O(x^6) = \left( \frac{1 - 3}{24} \right) x^4 + O(x^6) = -\frac{2}{24}x^4 + O(x^6) = -\frac{1}{12}x^4 + O(x^6)$$

3. **極限の計算**
   分子を $x^4$ で割り、 $x \to 0$ の極限をとります：
   $$L = \lim_{x \to 0} \frac{-\frac{1}{12}x^4 + O(x^6)}{x^4} = \lim_{x \to 0} \left( -\frac{1}{12} + O(x^2) \right) = -\frac{1}{12}$$

---

### 【問題2】の解答・解説
#### 解答
$$\mathbf{e}_1 = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}, \quad \mathbf{e}_2 = \frac{1}{\sqrt{6}}\begin{pmatrix} -1 \\ 1 \\ 2 \end{pmatrix}, \quad \mathbf{e}_3 = \frac{1}{\sqrt{3}}\begin{pmatrix} 1 \\ -1 \\ 1 \end{pmatrix}$$

#### 詳細な計算ステップ
1. **グラム・シュミットの手順の整理**
   一次独立な基底 $\{\mathbf{u}_1, \mathbf{u}_2, \mathbf{u}_3\}$ から正規直交基底 $\{\mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3\}$ を以下の手順で求めます：
   * $\mathbf{v}_1 = \mathbf{u}_1 \implies \mathbf{e}_1 = \frac{\mathbf{v}_1}{\|\mathbf{v}_1\|}$
   * $\mathbf{v}_2 = \mathbf{u}_2 - (\mathbf{u}_2 \cdot \mathbf{e}_1)\mathbf{e}_1 \implies \mathbf{e}_2 = \frac{\mathbf{v}_2}{\|\mathbf{v}_2\|}$
   * $\mathbf{v}_3 = \mathbf{u}_3 - (\mathbf{u}_3 \cdot \mathbf{e}_1)\mathbf{e}_1 - (\mathbf{u}_3 \cdot \mathbf{e}_2)\mathbf{e}_2 \implies \mathbf{e}_3 = \frac{\mathbf{v}_3}{\|\mathbf{v}_3\|}$

2. **第1の直交ベクトルの決定**
   $$\mathbf{v}_1 = \mathbf{u}_1 = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}$$
   長さ（ノルム）を計算します：
   $$\|\mathbf{v}_1\| = \sqrt{1^2 + 1^2 + 0^2} = \sqrt{2}$$
   したがって、最初の単位ベクトルは：
   $$\mathbf{e}_1 = \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}$$

3. **第2の直交ベクトルの決定**
   $\mathbf{u}_2$ から $\mathbf{e}_1$ 方向の射影成分を引きます：
   * 内積の計算：
     $$\mathbf{u}_2 \cdot \mathbf{e}_1 = 0 \cdot \frac{1}{\sqrt{2}} + 1 \cdot \frac{1}{\sqrt{2}} + 1 \cdot 0 = \frac{1}{\sqrt{2}}$$
   * 直交成分 $\mathbf{v}_2$ の計算：
     $$\mathbf{v}_2 = \mathbf{u}_2 - (\mathbf{u}_2 \cdot \mathbf{e}_1)\mathbf{e}_1 = \begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix} - \frac{1}{\sqrt{2}} \left( \frac{1}{\sqrt{2}}\begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix} \right) = \begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix} - \begin{pmatrix} 1/2 \\ 1/2 \\ 0 \end{pmatrix} = \begin{pmatrix} -1/2 \\ 1/2 \\ 1 \end{pmatrix}$$
   長さ（ノルム）を計算します：
   $$\|\mathbf{v}_2\| = \sqrt{(-1/2)^2 + (1/2)^2 + 1^2} = \sqrt{1/4 + 1/4 + 1} = \sqrt{6/4} = \frac{\sqrt{6}}{2}$$
   単位化を行います：
   $$\mathbf{e}_2 = \frac{2}{\sqrt{6}}\begin{pmatrix} -1/2 \\ 1/2 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{6}}\begin{pmatrix} -1 \\ 1 \\ 2 \end{pmatrix}$$

4. **第3の直交ベクトルの決定**
   $\mathbf{u}_3$ から $\mathbf{e}_1, \mathbf{e}_2$ 方向の射影成分を引きます：
   * 各内積の計算：
     $$\mathbf{u}_3 \cdot \mathbf{e}_1 = 1 \cdot \frac{1}{\sqrt{2}} + 0 \cdot \frac{1}{\sqrt{2}} + 1 \cdot 0 = \frac{1}{\sqrt{2}}$$
     $$\mathbf{u}_3 \cdot \mathbf{e}_2 = 1 \cdot \left(-\frac{1}{\sqrt{6}}\right) + 0 \cdot \frac{1}{\sqrt{6}} + 1 \cdot \frac{2}{\sqrt{6}} = \frac{1}{\sqrt{6}}$$
   * 直交成分 $\mathbf{v}_3$ の計算：
     $$\mathbf{v}_3 = \mathbf{u}_3 - (\mathbf{u}_3 \cdot \mathbf{e}_1)\mathbf{e}_1 - (\mathbf{u}_3 \cdot \mathbf{e}_2)\mathbf{e}_2$$
     $$\mathbf{v}_3 = \begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix} - \frac{1}{2}\begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix} - \frac{1}{6}\begin{pmatrix} -1 \\ 1 \\ 2 \end{pmatrix} = \begin{pmatrix} 1 - 1/2 + 1/6 \\ 0 - 1/2 - 1/6 \\ 1 - 0 - 2/6 \end{pmatrix} = \begin{pmatrix} 2/3 \\ -2/3 \\ 2/3 \end{pmatrix} = \frac{2}{3}\begin{pmatrix} 1 \\ -1 \\ 1 \end{pmatrix}$$
   長さ（ノルム）を計算します：
   $$\|\mathbf{v}_3\| = \frac{2}{3}\sqrt{1^2 + (-1)^2 + 1^2} = \frac{2\sqrt{3}}{3}$$
   単位化を行います：
   $$\mathbf{e}_3 = \frac{3}{2\sqrt{3}} \cdot \frac{2}{3}\begin{pmatrix} 1 \\ -1 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{3}}\begin{pmatrix} 1 \\ -1 \\ 1 \end{pmatrix}$$

---

### 【問題3】の解答・解説
#### 解答
$$x^3 + 2xy^2 + 2y^3 = C \quad (C\text{は任意定数})$$

#### 詳細な計算ステップ
1. **完全微分方程式であることの判定**
   微分方程式 $M(x, y) \,dx + N(x, y) \,dy = 0$ において、各項を定義します：
   $$M(x, y) = 3x^2 + 2y^2, \quad N(x, y) = 4xy + 6y^2$$
   それぞれの偏導関数を計算します：
   * $\frac{\partial M}{\partial y} = \frac{\partial}{\partial y}(3x^2 + 2y^2) = 4y$
   * $\frac{\partial N}{\partial x} = \frac{\partial}{\partial x}(4xy + 6y^2) = 4y$
   $\frac{\partial M}{\partial y} = \frac{\partial N}{\partial x} = 4y$ が成り立つため、この方程式は完全微分方程式（exact ODE）です。

2. **一般解の関数 $u(x, y)$ の決定**
   求める解を $u(x, y) = C$ とすると、偏微分の条件は以下の通りです：
   * $\frac{\partial u}{\partial x} = M(x, y) = 3x^2 + 2y^2 \quad \cdots \text{(A)}$
   * $\frac{\partial u}{\partial y} = N(x, y) = 4xy + 6y^2 \quad \cdots \text{(B)}$

3. **$x$ についての積分**
   条件式 (A) を変数 $x$ で積分します。このとき $y$ は定数として扱います：
   $$u(x, y) = \int (3x^2 + 2y^2) \,dx = x^3 + 2xy^2 + \phi(y)$$
   （※ $\phi(y)$ は $y$ のみを含む任意の微分可能関数です。）

4. **$\phi(y)$ の決定**
   求めた $u(x, y)$ の式を、今度は変数 $y$ について偏微分します：
   $$\frac{\partial u}{\partial y} = 4xy + \phi'(y)$$
   これを条件式 (B) と比較します：
   $$4xy + \phi'(y) = 4xy + 6y^2 \implies \phi'(y) = 6y^2$$
   両辺を $y$ について積分します：
   $$\phi(y) = \int 6y^2 \,dy = 2y^3 + C_0$$
   （定数 $C_0$ は一般解の右辺の定数に含めるため、省略して構いません。）

5. **一般解の組み立て**
   得られた $\phi(y)$ を $u(x, y)$ に戻します：
   $$u(x, y) = x^3 + 2xy^2 + 2y^3$$
   したがって、求める一般解は次のようになります：
   $$x^3 + 2xy^2 + 2y^3 = C$$

---

### 【問題4】の解答・解説
#### 解答
$$2i$$

#### 詳細な計算ステップ
1. **被積分関数の非正則性と線積分の方向性**
   被積分関数 $f(z) = \bar{z} = x - iy$ は複素平面全体で正則ではありません（コーシー・リーマンの関係式 $\frac{\partial u}{\partial x} \neq \frac{\partial v}{\partial y}$ より）。
   したがって、留数定理やコーシーの積分定理を適用することはできず、正方形の4つの辺に沿って個別に実パラメータを用いて線積分を行います。
   経路 $C$ は反時計回りの正方形で、4つの区間に分割されます：
   * $C_1$： $0 \to 1$ （実軸上、 $y = 0, \; dx$ のみ）
   * $C_2$： $1 \to 1+i$ （直線 $x = 1, \; i\,dy$）
   * $C_3$： $1+i \to i$ （直線 $y = 1, \; dx$ のみ）
   * $C_4$： $i \to 0$ （虚軸上、 $x = 0, \; i\,dy$）

2. **各辺における積分の実行**
   * **辺1 ($C_1$)**： $z = x \implies \bar{z} = x, \; dz = dx$。 $x$ は $0 \to 1$。
     $$I_1 = \int_0^1 x \,dx = \left[ \frac{x^2}{2} \right]_0^1 = \frac{1}{2}$$
   * **辺2 ($C_2$)**： $z = 1 + iy \implies \bar{z} = 1 - iy, \; dz = i\,dy$。 $y$ は $0 \to 1$。
     $$I_2 = \int_0^1 (1 - iy) i \,dy = i \int_0^1 (1 - iy) \,dy = i \left[ y - i\frac{y^2}{2} \right]_0^1 = i \left( 1 - \frac{i}{2} \right) = i + \frac{1}{2}$$
   * **辺3 ($C_3$)**： $z = x + i \implies \bar{z} = x - i, \; dz = dx$。 $x$ は $1 \to 0$ （向きに注意）。
     $$I_3 = \int_1^0 (x - i) \,dx = \left[ \frac{x^2}{2} - ix \right]_1^0 = 0 - \left( \frac{1}{2} - i \right) = -\frac{1}{2} + i$$
   * **辺4 ($C_4$)**： $z = iy \implies \bar{z} = -iy, \; dz = i\,dy$。 $y$ は $1 \to 0$ （向きに注意）。
     $$I_4 = \int_1^0 (-iy) i \,dy = \int_1^0 y \,dy = \left[ \frac{y^2}{2} \right]_1^0 = -\frac{1}{2}$$

3. **積分の合計**
   各辺の積分値を合算します：
   $$I = I_1 + I_2 + I_3 + I_4 = \frac{1}{2} + \left( i + \frac{1}{2} \right) + \left( -\frac{1}{2} + i \right) + \left( -\frac{1}{2} \right) = 2i$$

---

### 【問題5】の解答・解説
#### 解答
$$-\frac{3}{2}$$

#### 詳細な計算ステップ
1. **ストークスの定理の定義**
   ベクトル場 $\mathbf{F} = (P, Q, R) = (y, z, x)$ に対し、閉経路 $C$ に沿った線積分は、その境界を囲む曲面 $S$ 上の面積分に変換できます：
   $$\oint_C \mathbf{F} \cdot d\mathbf{r} = \iint_S (\nabla \times \mathbf{F}) \cdot \mathbf{n} \,dS$$

2. **回転（curl） $\nabla \times \mathbf{F}$ の計算**
   $$\nabla \times \mathbf{F} = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ \frac{\partial}{\partial x} & \frac{\partial}{\partial y} & \frac{\partial}{\partial z} \\ y & z & x \end{vmatrix}$$
   $$= \left( \frac{\partial x}{\partial y} - \frac{\partial z}{\partial z} \right) \mathbf{i} + \left( \frac{\partial y}{\partial z} - \frac{\partial x}{\partial x} \right) \mathbf{j} + \left( \frac{\partial z}{\partial x} - \frac{\partial y}{\partial y} \right) \mathbf{k}$$
   $$= (0 - 1)\mathbf{i} + (0 - 1)\mathbf{j} + (0 - 1)\mathbf{k} = \begin{pmatrix} -1 \\ -1 \\ -1 \end{pmatrix}$$

3. **法線ベクトル $\mathbf{n}$ の決定**
   曲面 $S$ は平面 $x + y + z - 1 = 0$ の第1八分限の部分（三角形の領域）です。
   平面の勾配から、上向き単位法線ベクトル $\mathbf{n}$ を求めます：
   $$\mathbf{n} = \frac{\nabla(x+y+z-1)}{\|\nabla(x+y+z-1)\|} = \frac{1}{\sqrt{1^2+1^2+1^2}} \begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix} = \frac{1}{\sqrt{3}}\begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix}$$

4. **内積の計算と積分式の整理**
   $$\nabla \times \mathbf{F} \cdot \mathbf{n} = \begin{pmatrix} -1 \\ -1 \\ -1 \end{pmatrix} \cdot \frac{1}{\sqrt{3}}\begin{pmatrix} 1 \\ 1 \\ 1 \end{pmatrix} = -\frac{3}{\sqrt{3}} = -\sqrt{3}$$
   したがって、積分式は曲面の面積を用いて表せます：
   $$I = \iint_S (-\sqrt{3}) \,dS = -\sqrt{3} \iint_S dS$$
   ここで $\iint_S dS$ は、3点 $(1,0,0), (0,1,0), (0,0,1)$ を頂点とする三角形の面積を表します。

5. **三角形の面積の計算**
   この三角形は、一辺の長さが $\sqrt{1^2 + 1^2} = \sqrt{2}$ である正三角形です。
   正三角形の面積公式 $S = \frac{\sqrt{3}}{4} a^2$ に代入します：
   $$\text{面積} = \frac{\sqrt{3}}{4} (\sqrt{2})^2 = \frac{\sqrt{3}}{2}$$

6. **最終計算**
   $$I = -\sqrt{3} \times \frac{\sqrt{3}}{2} = -\frac{3}{2}$$

---

### 【問題6】の解答・解説
#### 解答
$$49$$

#### 詳細な計算ステップ
1. **合同式の定式化**
   下2桁を求めることは、法 $100$ における合同式 $7^{2026} \pmod{100}$ を求めることと同じです。
   $7$ と $100$ は互いに素であるため、オイラーの定理 $a^{\phi(m)} \equiv 1 \pmod m$ を利用して剰余計算を簡略化できます。

2. **オイラーの $\phi$ 関数の計算**
   法 $m=100$ を素因数分解します：
   $$100 = 2^2 \times 5^2$$
   $$\phi(100) = 100 \left(1 - \frac{1}{2}\right)\left(1 - \frac{1}{5}\right) = 100 \times \frac{1}{2} \times \frac{4}{5} = 40$$
   したがって、オイラーの定理より $7^{40} \equiv 1 \pmod{100}$ です。

3. **合同式の位数の精査**
   オイラーの定理による周期は最大 40 ですが、実際には周期がこれより小さい可能性があります。 $7$ のべき乗を直接計算して周期を探します：
   * $7^2 = 49$
   * $7^3 = 343 \equiv 43 \pmod{100}$
   * $7^4 = 7 \times 43 = 301 \equiv 1 \pmod{100}$
   
   したがって、法 $100$ における $7$ の位数（周期）は **4** であることがわかりました：
   $$7^4 \equiv 1 \pmod{100}$$

4. **べき指数の簡単化と余りの決定**
   指数 $2026$ を周期 $4$ で割ります：
   $$2026 = 4 \times 506 + 2$$
   これを利用してべき乗を分解し、 $\pmod{100}$ をとります：
   $$7^{2026} = (7^4)^{506} \times 7^2 \equiv 1^{506} \times 49 \equiv 49 \pmod{100}$$
   よって、下2桁は **49** です。

---

### 【問題7】の解答・解説
#### 解答
1. $M_X(t) = \frac{\lambda}{\lambda - t} \quad (t < \lambda)$
2. $E[X^3] = \frac{6}{\lambda^3}$

#### 詳細な計算ステップ
1. **モーメント母関数の導出**
   定義に従って積分を計算します：
   $$M_X(t) = E[e^{tX}] = \int_0^{\infty} e^{tx} \cdot \lambda e^{-\lambda x} \,dx = \lambda \int_0^{\infty} e^{-(\lambda - t)x} \,dx$$
   積分が収束するためには、指数の係数が負、すなわち $\lambda - t > 0 \implies t < \lambda$ である必要があります：
   $$M_X(t) = \lambda \left[ -\frac{1}{\lambda - t} e^{-(\lambda - t)x} \right]_0^{\infty}$$
   $x \to \infty$ のとき $e^{-(\lambda-t)x} \to 0$ となるため：
   $$M_X(t) = \lambda \left( 0 - \left(-\frac{1}{\lambda - t}\right) \right) = \frac{\lambda}{\lambda - t} = \left( 1 - \frac{t}{\lambda} \right)^{-1}$$

2. **期待値と微分の性質の利用**
   モーメント母関数と期待値（モーメント）の間には、 $n$ 階微分して $t=0$ を代入することで $n$ 次モーメントが得られる性質があります：
   $$E[X^n] = M_X^{(n)}(0)$$
   これを利用して、 $3$ 階導関数を求めます：
   * **1階微分**：
     $$M_X'(t) = \frac{d}{dt}\left[ \lambda(\lambda-t)^{-1} \right] = \lambda(-1)(\lambda-t)^{-2}(-1) = \lambda(\lambda-t)^{-2}$$
   * **2階微分**：
     $$M_X''(t) = \frac{d}{dt}\left[ \lambda(\lambda-t)^{-2} \right] = \lambda(-2)(\lambda-t)^{-3}(-1) = 2\lambda(\lambda-t)^{-3}$$
   * **3階微分**：
     $$M_X'''(t) = \frac{d}{dt}\left[ 2\lambda(\lambda-t)^{-3} \right] = 2\lambda(-3)(\lambda-t)^{-4}(-1) = 6\lambda(\lambda-t)^{-4} = \frac{6\lambda}{(\lambda-t)^4}$$

3. **$3$ 次モーメントの期待値 $E[X^3]$ の計算**
   $3$ 階導関数に $t = 0$ を代入します：
   $$E[X^3] = M_X'''(0) = \frac{6\lambda}{(\lambda - 0)^4} = \frac{6\lambda}{\lambda^4} = \frac{6}{\lambda^3}$$

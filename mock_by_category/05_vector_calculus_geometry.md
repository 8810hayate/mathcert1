# 数学検定1級 一次試験 模擬問題：ベクトル解析・幾何 (Vector Calculus & Geometry)

数検1級一次試験対策のための、**ベクトル解析・幾何 (Vector Calculus & Geometry)**分野の模擬・演習問題（全12問）と詳細な解答解説です。

[分野別問題集トップに戻る](README.md)

---

## 【問題 1】ベクトル解析（線積分・グリーンの定理） （第1回 模擬試験・問題5）

### 問題
$xy$ 平面上の円 $C: (x-1)^2 + y^2 = 4$ を反時計回りに1周するとき、次の線積分の値を求めよ。
$$\oint_C \left( (y + \sin(x^2)) \,dx + (3x - e^{y^3}) \,dy \right)$$

### 解答・解説
#### 解答
$$8\pi$$

#### 詳細な計算ステップ
1. **グリーンの定理の適用条件確認**
   線積分 $\oint_C (P\,dx + Q\,dy)$ において：
   * $P(x, y) = y + \sin(x^2)$
   * $Q(x, y) = 3x - e^{y^3}$
   円 $C$ およびその内部の領域 $D$ で $P, Q$ は無限回微分可能で連続です。グリーンの定理を適用します。
   $$\oint_C (P\,dx + Q\,dy) = \iint_D \left( \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right) \,dx\,dy$$

2. **偏導関数の計算**
   * $\frac{\partial Q}{\partial x} = \frac{\partial}{\partial x}(3x - e^{y^3}) = 3$
   * $\frac{\partial P}{\partial y} = \frac{\partial}{\partial y}(y + \sin(x^2)) = 1$
   これより被積分関数は：
   $$\frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} = 3 - 1 = 2$$

3. **重積分の計算と面積**
   $$I = \iint_D 2 \,dx\,dy = 2 \iint_D 1 \,dx\,dy$$
   ここで、 $\iint_D 1 \,dx\,dy$ は領域 $D$ （円の内部）の面積を表します。
   積分領域 $D$ は $(x-1)^2 + y^2 \le 4$ であり、これは半径 $R = 2$ の円の内部です。
   円の面積は $\pi R^2 = \pi (2^2) = 4\pi$ です。
   したがって：
   $$I = 2 \times 4\pi = 8\pi$$

---

## 【問題 2】ベクトル解析（保存力場とポテンシャル） （第3回 模擬試験・問題5）

### 問題
次のベクトル場 $\mathbf{F}(x, y, z)$ について、以下の問いに答えよ。
$$\mathbf{F}(x, y, z) = (2xy + z^2)\mathbf{i} + (x^2 + 2yz)\mathbf{j} + (2xz + y^2)\mathbf{k}$$
1. $\mathbf{F}$ が保存力場であること（$\nabla \times \mathbf{F} = \mathbf{0}$）を示せ。
2. $\mathbf{F} = \nabla \phi$ を満たすポテンシャル関数 $\phi(x, y, z)$ を求めよ。ただし、初期条件は $\phi(0, 0, 0) = 0$ とする。

### 解答・解説
#### 解答
1. （証明略、解説参照）
2. $\phi(x, y, z) = x^2y + xz^2 + y^2z$

#### 詳細な計算ステップ
1. **第1問：保存力場の証明**
   ベクトル場 $\mathbf{F} = (P, Q, R)$ に対し、回転 $\nabla \times \mathbf{F} = \mathbf{0}$ を計算します。
   * $P = 2xy + z^2$
   * $Q = x^2 + 2yz$
   * $R = 2xz + y^2$
   $$\nabla \times \mathbf{F} = \left( \frac{\partial R}{\partial y} - \frac{\partial Q}{\partial z}, \; \frac{\partial P}{\partial z} - \frac{\partial R}{\partial x}, \; \frac{\partial Q}{\partial x} - \frac{\partial P}{\partial y} \right)$$
   各成分を個別に計算します。
   * $x$ 成分： $\frac{\partial}{\partial y}(2xz+y^2) - \frac{\partial}{\partial z}(x^2+2yz) = 2y - 2y = 0$
   * $y$ 成分： $\frac{\partial}{\partial z}(2xy+z^2) - \frac{\partial}{\partial x}(2xz+y^2) = 2z - 2z = 0$
   * $z$ 成分： $\frac{\partial}{\partial x}(x^2+2yz) - \frac{\partial}{\partial y}(2xy+z^2) = 2x - 2x = 0$
   したがって、 $\nabla \times \mathbf{F} = (0, 0, 0) = \mathbf{0}$ となり、保存力場です。

2. **第2問：ポテンシャル関数の決定**
   $\nabla \phi = \mathbf{F} \implies \left( \frac{\partial\phi}{\partial x}, \frac{\partial\phi}{\partial y}, \frac{\partial\phi}{\partial z} \right) = (P, Q, R)$ より：
   $$\frac{\partial \phi}{\partial x} = 2xy + z^2$$
   これを $x$ について積分します。
   $$\phi(x, y, z) = x^2y + xz^2 + g(y, z) \quad \cdots \text{(I)}$$
   （$g(y, z)$ は $y, z$ のみの関数）
   式(I) を $y$ で微分し、 $Q$ と比較します。
   $$\frac{\partial \phi}{\partial y} = x^2 + \frac{\partial g}{\partial y} = x^2 + 2yz \implies \frac{\partial g}{\partial y} = 2yz$$
   これを $y$ で積分します。
   $$g(y, z) = y^2z + h(z) \quad (h(z)\text{は}z\text{のみの関数})$$
   これを式(I) に戻します。
   $$\phi(x, y, z) = x^2y + xz^2 + y^2z + h(z) \quad \cdots \text{(J)}$$
   式(J) を $z$ で微分し、 $R$ と比較します。
   $$\frac{\partial \phi}{\partial z} = 2xz + y^2 + h'(z) = 2xz + y^2 \implies h'(z) = 0 \implies h(z) = C \quad (C\text{は定数})$$
   初期条件 $\phi(0, 0, 0) = 0$ を代入します。
   $$\phi(0, 0, 0) = 0^2(0) + 0(0^2) + 0^2(0) + C = 0 \implies C = 0$$
   よって、求めるポテンシャル関数は：
   $$\phi(x, y, z) = x^2y + xz^2 + y^2z$$

---

## 【問題 3】ベクトル解析・幾何（曲面の面積） （第5回 模擬試験・問題5）

### 問題
放物面 $z = x^2 + y^2$ のうち、平面 $z = 1$ より下にある部分の曲面積 $A$ を求めよ。

### 解答・解説
#### 解答
$$A = \frac{\pi}{6}(5\sqrt{5} - 1)$$

#### 詳細な計算ステップ
1. **曲面積の公式の提示**
   曲面 $z = f(x, y)$ の、 $xy$ 平面上の領域 $D$ における曲面積 $A$ は次の重積分で与えられます：
   $$A = \iint_D \sqrt{1 + \left(\frac{\partial z}{\partial x}\right)^2 + \left(\frac{\partial z}{\partial y}\right)^2} \,dx\,dy$$

2. **偏導関数の計算と代入**
   $z = x^2 + y^2$ より：
   $$\frac{\partial z}{\partial x} = 2x, \quad \frac{\partial z}{\partial y} = 2y$$
   これを公式に代入すると、被積分関数は次のようになります：
   $$\sqrt{1 + (2x)^2 + (2y)^2} = \sqrt{1 + 4(x^2 + y^2)}$$

3. **積分領域 $D$ の決定**
   平面 $z = 1$ より下にある部分という条件は $x^2 + y^2 \le 1$ となります。
   したがって、積分領域 $D$ は $xy$ 平面上の半径 $1$ の閉円板です：
   $$D = \{ (x, y) \in \mathbb{R}^2 \mid x^2 + y^2 \le 1 \}$$

4. **極座標への変換**
   $x = r\cos\theta, y = r\sin\theta$ とおきます。ヤコビ行列式（ヤコビアン）は $r$ です。
   積分の範囲は $0 \le r \le 1$, $0 \le \theta \le 2\pi$ となります：
   $$A = \int_{0}^{2\pi} \int_{0}^{1} \sqrt{1 + 4r^2} \cdot r \,dr\,d\theta$$

5. **積分の実行**
   $\theta$ と $r$ の積分はそれぞれ独立しているため、積の形で分離して計算します：
   $$A = \left( \int_{0}^{2\pi} d\theta \right) \left( \int_{0}^{1} r\sqrt{1 + 4r^2} \,dr \right) = 2\pi \int_{0}^{1} r(1 + 4r^2)^{1/2} \,dr$$
   $r$ の積分に関して $u = 1 + 4r^2$ とおきます：
   * $du = 8r \,dr \implies r \,dr = \frac{1}{8} \,du$
   * 積分範囲の変換： $r: 0 \to 1 \implies u: 1 \to 5$
   
   これらを代入して計算します：
   $$\int_{0}^{1} r(1 + 4r^2)^{1/2} \,dr = \int_{1}^{5} u^{1/2} \left( \frac{1}{8} \,du \right) = \frac{1}{8} \left[ \frac{2}{3}u^{3/2} \right]_1^5 = \frac{1}{12}(5^{3/2} - 1^{3/2}) = \frac{1}{12}(5\sqrt{5} - 1)$$

6. **最終的な計算結果**
   $$A = 2\pi \times \frac{1}{12}(5\sqrt{5} - 1) = \frac{\pi}{6}(5\sqrt{5} - 1)$$

---

## 【問題 4】ベクトル解析・幾何（方向微分係数） （第6回 模擬試験・問題5）

### 問題
3変数関数 $f(x, y, z) = x y^2 + y z^2 + z x^2$ の、点 $P(1, 2, 0)$ におけるベクトル $\mathbf{u} = 2\mathbf{i} - \mathbf{j} + 2\mathbf{k}$ 方向の方向微分係数 $D_{\mathbf{u}} f(P)$ を求めよ。

### 解答・解説
#### 解答
$$2$$

#### 詳細な計算ステップ
1. **方向微分係数の定義**
   多変数関数 $f(x, y, z)$ の、点 $P$ における単位方向ベクトル $\mathbf{e}$ に対する方向微分係数 $D_{\mathbf{e}} f(P)$ は、勾配ベクトル $\nabla f(P)$ と単位ベクトル $\mathbf{e}$ の内積で与えられます：
   $$D_{\mathbf{e}} f(P) = \nabla f(P) \cdot \mathbf{e}$$

2. **勾配ベクトル $\nabla f$ の計算**
   各変数に関して偏微分を行います：
   * $\frac{\partial f}{\partial x} = y^2 + 2zx$
   * $\frac{\partial f}{\partial y} = 2xy + z^2$
   * $\frac{\partial f}{\partial z} = 2yz + x^2$
   
   点 $P(1, 2, 0)$ の座標を代入します（$x=1, y=2, z=0$）：
   * $f_x(1, 2, 0) = 2^2 + 2(0)(1) = 4$
   * $f_y(1, 2, 0) = 2(1)(2) + 0^2 = 4$
   * $f_z(1, 2, 0) = 2(2)(0) + 1^2 = 1$
   
   したがって、勾配ベクトルは以下の通りです：
   $$\nabla f(1, 2, 0) = \begin{pmatrix} 4 \\ 4 \\ 1 \end{pmatrix}$$

3. **方向ベクトルの単位化**
   与えられた方向ベクトル $\mathbf{u} = \begin{pmatrix} 2 \\ -1 \\ 2 \end{pmatrix}$ のノルム（長さ）を求めます：
   $$\|\mathbf{u}\| = \sqrt{2^2 + (-1)^2 + 2^2} = \sqrt{4 + 1 + 4} = 3$$
   $\mathbf{u}$ 方向の単位ベクトル $\mathbf{e}$ は次のようになります：
   $$\mathbf{e} = \frac{\mathbf{u}}{\|\mathbf{u}\|} = \begin{pmatrix} 2/3 \\ -1/3 \\ 2/3 \end{pmatrix}$$

4. **内積の計算**
   勾配ベクトル $\nabla f(P)$ と単位ベクトル $\mathbf{e}$ の内積を求めます：
   $$D_{\mathbf{u}} f(P) = \begin{pmatrix} 4 \\ 4 \\ 1 \end{pmatrix} \cdot \begin{pmatrix} 2/3 \\ -1/3 \\ 2/3 \end{pmatrix} = 4\left(\frac{2}{3}\right) + 4\left(-\frac{1}{3}\right) + 1\left(\frac{2}{3}\right) = \frac{8 - 4 + 2}{3} = \frac{6}{3} = 2$$

---

## 【問題 5】微分積分学（曲線の包絡線） （第7回 模擬試験・問題1）

### 問題
実数パラメータ $\theta$ に対する次の直線群の包絡線（envelope）の方程式を求めよ（ただし $a > 0$ とする）。
$$x \cos \theta + y \sin \theta = a$$

### 解答・解説
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

## 【問題 6】ベクトル解析（面積分・曲面を通るフラックス） （第7回 模擬試験・問題5）

### 問題
ベクトル場 $\mathbf{F}(x, y, z) = (0, \; 0, \; z)$ に対し、 $S$ を半径 $R$ の上半球面 $x^2 + y^2 + z^2 = R^2 \; (z \ge 0)$ とし、 $\mathbf{n}$ を外向き単位法線ベクトルとする。発散定理を用いず、**面積分を直接計算**して、次のフラックス（流束）を求めよ。
$$\iint_S \mathbf{F} \cdot \mathbf{n} \,dS$$

### 解答・解説
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

## 【問題 7】ベクトル解析（ストークスの定理） （第8回 模擬試験・問題5）

### 問題
ベクトル場 $\mathbf{F}(x, y, z) = (y, \; z, \; x)$ に対し、 $C$ を第1象限（$x, y, z \ge 0$）にある平面 $x + y + z = 1$ の境界（三角形の辺）とし、 $xy$ 平面上から見て反時計回り（正の向き）に方向づける。ストークスの定理を用いて、次の線積分の値を求めよ。
$$I = \oint_C (y \,dx + z \,dy + x \,dz)$$

### 解答・解説
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

## 【問題 8】ベクトル解析（ガウスの発散定理とフラックス） （第9回 模擬試験・問題5）

### 問題
ベクトル場 $\mathbf{F}(x, y, z) = (x^3, \; y^3, \; z^3)$ に対し、 $S$ を半径 $R$ の球面 $x^2 + y^2 + z^2 = R^2$ とし、 $\mathbf{n}$ を外向き単位法線ベクトルとする。ガウスの発散定理を用いて、次の面積分（フラックス）の値を求めよ。
$$I = \iint_S \mathbf{F} \cdot \mathbf{n} \,dS$$

### 解答・解説
#### 解答
$$\frac{12}{5}\pi R^5$$

#### 詳細な計算ステップ
1. **ガウスの発散定理の適用**
   ベクトル場 $\mathbf{F}$ の閉曲面 $S$ （球）を通る外向きのフラックスは、球の内部の領域 $V$ における発散（divergence）の体積積分に等しくなります：
   $$\iint_S \mathbf{F} \cdot \mathbf{n} \,dS = \iiint_V \nabla \cdot \mathbf{F} \,dV$$

2. **発散（divergence） $\nabla \cdot \mathbf{F}$ の計算**
   $\mathbf{F}(x, y, z) = (x^3, y^3, z^3)$ より：
   $$\nabla \cdot \mathbf{F} = \frac{\partial(x^3)}{\partial x} + \frac{\partial(y^3)}{\partial y} + \frac{\partial(z^3)}{\partial z} = 3x^2 + 3y^2 + 3z^2 = 3(x^2 + y^2 + z^2)$$

3. **3重積分の計算（球面座標系への変換）**
   積分領域 $V$ は半径 $R$ の球の内部 $x^2 + y^2 + z^2 \le R^2$ です。
   球面座標系 $x = \rho \sin\phi\cos\theta, \; y = \rho \sin\phi\sin\theta, \; z = \rho \cos\phi$ を用いて積分を書き換えます。
   このとき、被積分関数は $3(x^2 + y^2 + z^2) = 3\rho^2$ であり、ヤコビアンは $\rho^2 \sin\phi$ です：
   $$I = \iiint_V 3(x^2 + y^2 + z^2) \,dx\,dy\,dz = \int_0^{2\pi} \int_0^{\pi} \int_0^R (3\rho^2) \cdot \rho^2 \sin\phi \,d\rho\,d\phi\,d\theta$$
   $$I = \int_0^{2\pi} \int_0^{\pi} \int_0^R 3\rho^4 \sin\phi \,d\rho\,d\phi\,d\theta$$

4. **各変数の積分の計算**
   変数は独立して積分可能です：
   $$I = 3 \left( \int_0^{2\pi} d\theta \right) \left( \int_0^{\pi} \sin\phi \,d\phi \right) \left( \int_0^R \rho^4 \,d\rho \right)$$
   * **$\theta$ の積分**：
     $$\int_0^{2\pi} d\theta = 2\pi$$
   * **$\phi$ の積分**：
     $$\int_0^{\pi} \sin\phi \,d\phi = \Big[ -\cos\phi \Big]_0^{\pi} = -(-1) - (-1) = 2$$
   * **$\rho$ の積分**：
     $$\int_0^R \rho^4 \,d\rho = \left[ \frac{\rho^5}{5} \right]_0^R = \frac{R^5}{5}$$

5. **積の計算**
   $$I = 3 \times 2\pi \times 2 \times \frac{R^5}{5} = \frac{12}{5}\pi R^5$$

---

## 【問題 9】ベクトル解析（ベクトルポテンシャルの決定） （第10回 模擬試験・問題5）

### 問題
湧き出しのない（非圧縮な）ベクトル場 $\mathbf{F}(x, y, z) = (y-z, \; z-x, \; x-y)$ に対し、 $\nabla \times \mathbf{A} = \mathbf{F}$ を満たすベクトルポテンシャル $\mathbf{A}(x, y, z)$ の1つを求めよ。

### 解答・解説
#### 解答
$$\mathbf{A} = \begin{pmatrix} \frac{y^2 + z^2}{2} - zx \\ \frac{x^2 + z^2}{2} - yz \\ 0 \end{pmatrix} \quad (\text{※代表的な1つ、定数ベクトルや勾配の加算による別表現も可})$$

#### 詳細な計算ステップ
1. **ベクトルポテンシャルの定義**
   $\nabla \cdot \mathbf{F} = \frac{\partial(y-z)}{\partial x} + \frac{\partial(z-x)}{\partial y} + \frac{\partial(x-y)}{\partial z} = 0 + 0 + 0 = 0$ なので、 $\mathbf{F}$ はソレノイダル（湧き出しなし）であり、 $\mathbf{F} = \nabla \times \mathbf{A}$ を満たすベクトルポテンシャル $\mathbf{A} = (A_x, A_y, A_z)$ が存在します。
   回転の定義式より、次の連立偏微分方程式が得られます：
   * $\frac{\partial A_z}{\partial y} - \frac{\partial A_y}{\partial z} = y-z \quad \cdots \text{(1)}$
   * $\frac{\partial A_x}{\partial z} - \frac{\partial A_z}{\partial x} = z-x \quad \cdots \text{(2)}$
   * $\frac{\partial A_y}{\partial x} - \frac{\partial A_x}{\partial y} = x-y \quad \cdots \text{(3)}$

2. **簡略化のための仮定（ゲージの選択）**
   ベクトルポテンシャルの決定にはゲージ自由度があるため、計算を容易にするために $A_z = 0$ と仮定します。

3. **各成分の偏積分**
   $A_z = 0$ を式 (1), (2) に代入します：
   * 式 (1) より：
     $$-\frac{\partial A_y}{\partial z} = y-z \implies \frac{\partial A_y}{\partial z} = z-y$$
     これを $z$ について積分します：
     $$A_y = \frac{z^2}{2} - yz + f(x) \quad \cdots \text{(4)}$$
   * 式 (2) より：
     $$\frac{\partial A_x}{\partial z} = z-x$$
     これを $z$ について積分します：
     $$A_x = \frac{z^2}{2} - zx + g(y) \quad \cdots \text{(5)}$$
     （※ $f(x), g(y)$ はそれぞれ $x, y$ のみの未知関数です。）

4. **未知関数の決定**
   式 (4), (5) を式 (3) に代入します：
   $$\frac{\partial A_y}{\partial x} = f'(x), \quad \frac{\partial A_x}{\partial y} = g'(y)$$
   $$\frac{\partial A_y}{\partial x} - \frac{\partial A_x}{\partial y} = f'(x) - g'(y) = x-y$$
   この式は変数 $x$ と $y$ について分離可能なので：
   $$f'(x) - x = g'(y) - y = C \quad (C\text{は定数})$$
   $C = 0$ とおいてそれぞれの関数を決定します（積分定数も $0$ とします）：
   $$f'(x) = x \implies f(x) = \frac{x^2}{2}$$
   $$g'(y) = y \implies g(y) = \frac{y^2}{2}$$

5. **ポテンシャルの構成**
   求めた $f(x), g(y)$ を式 (4), (5) に代入します：
   * $A_x = \frac{z^2}{2} - zx + \frac{y^2}{2} = \frac{y^2 + z^2}{2} - zx$
   * $A_y = \frac{z^2}{2} - yz + \frac{x^2}{2} = \frac{x^2 + z^2}{2} - yz$
   * $A_z = 0$
   これらをベクトルとしてまとめると、求めるポテンシャルが得られます。

---

## 【問題 10】ベクトル解析（グリーンの定理） （総合問題セット・問題7）

### 問題
$xy$ 平面上の領域 $D$ を放物線 $y = x^2$ と $x = y^2$ で囲まれた領域とする。$D$ の境界 $C$ を反時計回りに1周するとき、次の線積分を計算せよ。
$$\oint_C \left( (y + e^{\sqrt{x}}) \,dx + (2x + \cos(y^2)) \,dy \right)$$

### 解答・解説
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

## 【問題 11】ベクトル解析・幾何（空間曲線の曲率と捩率の計算） （新規追加問題）

### 問題
3次元空間内の曲線 $\mathbf{r}(t) = (3\cos t, 3\sin t, 4t)$ について、任意の $t$ における曲率 $\kappa(t)$ および捩率（ねじれ率） $\tau(t)$ を求めよ。

### 解答・解説
#### 解答
$$\kappa(t) = \frac{3}{25}, \quad \tau(t) = \frac{4}{25}$$

#### 解説
1. **微分ベクトルの計算**
   曲線 $\mathbf{r}(t)$ の各階微分ベクトルを計算します：
   * $\mathbf{r}'(t) = (-3\sin t, \; 3\cos t, \; 4)$
   * \mathbf{r}''(t) = (-3\cos t, \; -3\sin t, \; 0)$
   * \mathbf{r}'''(t) = (3\sin t, \; -3\cos t, \; 0)$

2. **速度ベクトルのノルム（速さ）の計算**
   $$\|\mathbf{r}'(t)\| = \sqrt{(-3\sin t)^2 + (3\cos t)^2 + 4^2} = \sqrt{9(\sin^2 t + \cos^2 t) + 16} = \sqrt{9 + 16} = 5$$

3. **外積 $\mathbf{r}' \times \mathbf{r}''$ の計算**
   曲率・捩率の公式に必要な外積ベクトルを求めます：
   $$\mathbf{r}' \times \mathbf{r}'' = \begin{vmatrix} \mathbf{i} & \mathbf{j} & \mathbf{k} \\ -3\sin t & 3\cos t & 4 \\ -3\cos t & -3\sin t & 0 \end{vmatrix}$$
   $$= (4\cdot 3\sin t)\mathbf{i} - (-4\cdot(-3\cos t))\mathbf{j} + ((-3\sin t)(-3\sin t) - 3\cos t(-3\cos t))\mathbf{k}$$
   $$= (12\sin t)\mathbf{i} - (12\cos t)\mathbf{j} + 9(\sin^2 t + \cos^2 t)\mathbf{k}$$
   $$= (12\sin t)\mathbf{i} - (12\cos t)\mathbf{j} + 9\mathbf{k}$$
   
   この外積ベクトルのノルムは以下の通りです：
   $$\|\mathbf{r}' \times \mathbf{r}''\| = \sqrt{(12\sin t)^2 + (-12\cos t)^2 + 9^2} = \sqrt{144(\sin^2 t + \cos^2 t) + 81} = \sqrt{144 + 81} = \sqrt{225} = 15$$

4. **曲率 $\kappa(t)$ の計算**
   曲率の定義公式に計算値を代入します：
   $$\kappa(t) = \frac{\|\mathbf{r}' \times \mathbf{r}''\|}{\|\mathbf{r}'\|^3} = \frac{15}{5^3} = \frac{15}{125} = \frac{3}{25}$$

5. **捩率 $\tau(t)$ の計算**
   3重積 $(\mathbf{r}' \times \mathbf{r}''$) \cdot \mathbf{r}'''$ を計算します：
   $$(\mathbf{r}' \times \mathbf{r}'') \cdot \mathbf{r}''' = \begin{pmatrix} 12\sin t \\ -12\cos t \\ 9 \end{pmatrix} \cdot \begin{pmatrix} 3\sin t \\ -3\cos t \\ 0 \end{pmatrix}$$
   $$= (12\sin t)(3\sin t) + (-12\cos t)(-3\cos t) + 9(0) = 36\sin^2 t + 36\cos^2 t = 36$$
   
   捩率（ねじれ率）の定義公式に代入します：
   $$\tau(t) = \frac{(\mathbf{r}' \times \mathbf{r}'') \cdot \mathbf{r}'''}{\|\mathbf{r}' \times \mathbf{r}''\|^2} = \frac{36}{15^2} = \frac{36}{225} = \frac{4}{25}$$
   （※曲率・捩率ともに $t$ に依存しない一定値をとる、典型的な円螺旋（ヘリックス）の性質を示す結果です。）

---

## 【問題 12】ベクトル解析・幾何（曲面の接平面の方程式） （新規追加問題）

### 問題
3次元空間内の曲面 $x^2 + 2y^2 - 3z^2 = 3$ 上の点 $(2, 1, 1)$ における接平面の方程式を求めよ。

### 解答・解説
#### 解答
$$2x + 2y - 3z = 3$$

#### 解説
1. **勾配ベクトル（Gradient）による法線ベクトルの算出**
   曲面が陰関数形式 $F(x, y, z) = 0$ で定義されているとき、曲面上の点 $P(x_0, y_0, z_0)$ における法線ベクトル $mathbf{n}$ は、 $F$ の勾配ベクトル $
abla F(P)$ に一致します。
   与えられた曲面の式より、 $F(x, y, z) = x^2 + 2y^2 - 3z^2 - 3$ と定義します。
   偏導関数を計算します：
   $$rac{partial F}{partial x} = 2x, quad rac{partial F}{partial y} = 4y, quad rac{partial F}{partial z} = -6z$$
   これより、勾配ベクトルは以下となります：
   $$
abla F(x, y, z) = (2x, ; 4y, ; -6z)$$

2. **点 $(2, 1, 1)$ における法線ベクトルの決定**
   点 $P(2, 1, 1)$ を代入して、その点での法線ベクトルを求めます：
   $$mathbf{n} = 
abla F(2, 1, 1) = (2(2), ; 4(1), ; -6(1)) = (4, ; 4, ; -6)$$
   計算を簡略化するため、このベクトルを $2$ で割った $mathbf{n}' = (2, ; 2, ; -3)$ を法線ベクトルとして用います。

3. **接平面の方程式の立式**
   点 $(x_0, y_0, z_0)$ を通り、法線ベクトルが $(A, B, C)$ である平面の方程式は以下で与えられます：
   $$A(x - x_0) + B(y - y_0) + C(z - z_0) = 0$$
   点 $(2, 1, 1)$ と法線ベクトル $(2, 2, -3)$ を代入します：
   $$2(x - 2) + 2(y - 1) - 3(z - 1) = 0$$
   展開して整理します：
   $$2x - 4 + 2y - 2 - 3z + 3 = 0 implies 2x + 2y - 3z = 3$$
   したがって、求める接平面の方程式は $2x + 2y - 3z = 3$ です。

---


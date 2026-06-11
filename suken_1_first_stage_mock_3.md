# 数学検定1級 一次試験（計算技能）模擬試験［第3回］

数学検定1級一次試験（計算技能）対策のための、第3回模擬試験問題（全7問）と詳細な解答解説です。第1回、第2回の模擬試験とは異なる応用分野や理論的背景を持つ計算問題をカバーしています。

---

## 模擬試験問題（制限時間：60分）

### 【問題1】微分積分学（曲線の長さ）
次の媒介変数表示で表される平面曲線（サイクロイド）の長さ $L$ を求めよ。
$$x(t) = a(t - \sin t), \quad y(t) = a(1 - \cos t) \quad (0 \le t \le 2\pi, \; a > 0)$$

### 【問題2】線形代数（正射影行列）
3次元数ベクトル空間 $\mathbb{R}^3$ において、ベクトル $\mathbf{v} = \begin{pmatrix} 1 \\ 2 \\ 2 \end{pmatrix}$ が生成する部分空間を $W$ とする。このとき、 $W$ への直交射影（正射影）を表す行列 $P$ を求めよ。

### 【問題3】微分方程式（連立常微分方程式）
次の連立微分方程式の一般解を求めよ。
$$\begin{cases} \frac{dx}{dt} = 3x - y \\ \frac{dy}{dt} = x + y \end{cases}$$

### 【問題4】複素解析（コーシー・リーマンの関係式）
実2変数関数 $u(x, y) = x^2 - y^2 + 2x$ について、以下の問いに答えよ。
1. $u(x, y)$ が調和関数であることを示せ（ラプラス方程式 $\Delta u = 0$ を満たすことを示す）。
2. $f(z) = u(x, y) + i v(x, y)$ が複素数 $z = x + iy$ の正則関数となるような、 $u(x, y)$ の共役調和関数 $v(x, y)$ を求めよ。ただし、初期条件は $v(0, 0) = 0$ とする。

### 【問題5】ベクトル解析（保存力場とポテンシャル）
次のベクトル場 $\mathbf{F}(x, y, z)$ について、以下の問いに答えよ。
$$\mathbf{F}(x, y, z) = (2xy + z^2)\mathbf{i} + (x^2 + 2yz)\mathbf{j} + (2xz + y^2)\mathbf{k}$$
1. $\mathbf{F}$ が保存力場であること（$\nabla \times \mathbf{F} = \mathbf{0}$）を示せ。
2. $\mathbf{F} = \nabla \phi$ を満たすポテンシャル関数 $\phi(x, y, z)$ を求めよ。ただし、初期条件は $\phi(0, 0, 0) = 0$ とする。

### 【問題6】代数学（剰余群・同型）
加法群 $G = \mathbb{Z}_{24}$ （法24 of 合同式の加法群）と、元 6 が生成する部分群 $H = \langle 6 \rangle$ を考える。
1. 部分群 $H$ の要素と、その位数 $|H|$ を求めよ。
2. 剰余群 $G/H$ の位数 $|G/H|$ を求めよ。
3. 剰余群 $G/H$ のすべての代表元（剰余類）を列挙せよ。

### 【問題7】確率・統計（母分散の区間推定）
正規分布 $N(\mu, \sigma^2)$ （母平均 $\mu$、母分散 $\sigma^2$ はともに未知）から得られた大きさ $n=10$ のランダム標本について、標本不偏分散が $s^2 = 2.4$ であった。
母分散 $\sigma^2$ に対する信頼係数 $90\%$ の信頼区間を求めよ。
ただし、自由度 9 のカイ二乗分布の上側 $5\%$ 点を $\chi^2_{0.05}(9) = 16.92$、上側 $95\%$ 点を $\chi^2_{0.95}(9) = 3.325$ とし、端数は小数第2位まで（第3位を四捨五入）で答えよ。

---
---

## 解答・解説

### 【問題1】の解答・解説
#### 解答
$$L = 8a$$

#### 詳細な計算ステップ
1. **導関数の計算**
   媒介変数表示の各成分をパラメータ $t$ で微分します。
   * $\frac{dx}{dt} = \frac{d}{dt}(a(t - \sin t)) = a(1 - \cos t)$
   * $\frac{dy}{dt} = \frac{d}{dt}(a(1 - \cos t)) = a(0 - (-\sin t)) = a\sin t$

2. **平方根の中身（速さの2乗）の整理**
   $$\left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2 = [a(1 - \cos t)]^2 + [a\sin t]^2$$
   $$= a^2 (1 - 2\cos t + \cos^2 t) + a^2 \sin^2 t = a^2 (1 - 2\cos t + \cos^2 t + \sin^2 t)$$
   ここで、 $\cos^2 t + \sin^2 t = 1$ を適用します。
   $$= a^2 (1 - 2\cos t + 1) = a^2 (2 - 2\cos t) = 2a^2 (1 - \cos t)$$

3. **半角の公式による根号の消去**
   半角の公式 $\sin^2\left(\frac{t}{2}\right) = \frac{1 - \cos t}{2} \implies 1 - \cos t = 2\sin^2\left(\frac{t}{2}\right)$ を用いて平方完成します。
   $$2a^2(1 - \cos t) = 2a^2 \cdot 2\sin^2\left(\frac{t}{2}\right) = 4a^2\sin^2\left(\frac{t}{2}\right)$$
   これを平方根の中に入れます。
   $$\sqrt{\left(\frac{dx}{dt}\right)^2 + \left(\frac{dy}{dt}\right)^2} = \sqrt{4a^2\sin^2\left(\frac{t}{2}\right)} = 2a\left|\sin\left(\frac{t}{2}\right)\right|$$
   積分区間 $0 \le t \le 2\pi$ より、 $0 \le \frac{t}{2} \le \pi$ です。この区間では $\sin\left(\frac{t}{2}\right) \ge 0$ なので、絶対値記号をそのまま外して $2a\sin\left(\frac{t}{2}\right)$ とできます。

4. **積分の実行**
   定積分の公式 $\int \sin(kt) dt = -\frac{1}{k}\cos(kt)$ を適用します（$k=1/2$）。
   $$L = \int_0^{2\pi} 2a\sin\left(\frac{t}{2}\right) \,dt = 2a \left[ -2\cos\left(\frac{t}{2}\right) \right]_0^{2\pi} = -4a \left( \cos\pi - \cos 0 \right)$$
   $\cos\pi = -1$, $\cos 0 = 1$ を代入します。
   $$L = -4a (-1 - 1) = -4a (-2) = 8a$$

---

### 【問題2】の解答・解説
#### 解答
$$P = \frac{1}{9}\begin{pmatrix} 1 & 2 & 2 \\ 2 & 4 & 4 \\ 2 & 4 & 4 \end{pmatrix}$$

#### 詳細な計算ステップ
1. **射影行列の公式の導入**
   ベクトル $\mathbf{v}$ が生成する1次元部分空間への正射影行列 $P$ の公式は以下の通りです。
   $$P = \frac{\mathbf{v}\mathbf{v}^T}{\mathbf{v}^T\mathbf{v}}$$

2. **分母（内積）の計算**
   $$\mathbf{v}^T\mathbf{v} = \begin{pmatrix} 1 & 2 & 2 \end{pmatrix} \begin{pmatrix} 1 \\ 2 \\ 2 \end{pmatrix} = 1^2 + 2^2 + 2^2 = 1 + 4 + 4 = 9$$

3. **分子（外積行列）の計算**
   縦ベクトルと横ベクトルの積から行列を作ります。
   $$\mathbf{v}\mathbf{v}^T = \begin{pmatrix} 1 \\ 2 \\ 2 \end{pmatrix} \begin{pmatrix} 1 & 2 & 2 \end{pmatrix} = \begin{pmatrix} 1\cdot1 & 1\cdot2 & 1\cdot2 \\ 2\cdot1 & 2\cdot2 & 2\cdot2 \\ 2\cdot1 & 2\cdot2 & 2\cdot2 \end{pmatrix} = \begin{pmatrix} 1 & 2 & 2 \\ 2 & 4 & 4 \\ 2 & 4 & 4 \end{pmatrix}$$

4. **行列の決定**
   求めた値を公式に代入します。
   $$P = \frac{1}{9}\begin{pmatrix} 1 & 2 & 2 \\ 2 & 4 & 4 \\ 2 & 4 & 4 \end{pmatrix}$$

---

### 【問題3】の解答・解説
#### 解答
$$\begin{cases} x(t) = (C_1 + C_2 + C_2 t)e^{2t} \\ y(t) = (C_1 + C_2 t)e^{2t} \end{cases} \quad (C_1, C_2\text{は任意定数})$$

#### 詳細な計算ステップ
1. **変数 $x$ の消去による2階微分方程式の導出**
   与えられた連立微分方程式は：
   * $\frac{dx}{dt} = 3x - y \quad \cdots \text{(A)}$
   * $\frac{dy}{dt} = x + y \quad \cdots \text{(B)}$
   式(B) より：
   $$x = \frac{dy}{dt} - y \quad \cdots \text{(C)}$$
   式(C) の両辺を $t$ で微分します。
   $$\frac{dx}{dt} = \frac{d^2y}{dt^2} - \frac{dy}{dt} \quad \cdots \text{(D)}$$
   式(C) と (D) を 式(A) に代入して $x$ を消去します。
   $$\frac{d^2y}{dt^2} - \frac{dy}{dt} = 3\left(\frac{dy}{dt} - y\right) - y = 3\frac{dy}{dt} - 4y$$
   すべての項を左辺に移項して整理します。
   $$\frac{d^2y}{dt^2} - 4\frac{dy}{dt} + 4y = 0 \quad \cdots \text{(E)}$$

2. **2階微分方程式(E)の一般解 $y(t)$ の決定**
   特性方程式は以下の通りです。
   $$\lambda^2 - 4\lambda + 4 = 0 \implies (\lambda-2)^2 = 0 \implies \lambda = 2 \text{ (重解)}$$
   重解特性根を持つため、一般解は次の形になります。
   $$y(t) = (C_1 + C_2 t)e^{2t}$$

3. **$x(t)$ の決定**
   式(C) の $x = y' - y$ に $y(t)$ を代入するため、まず $y'(t)$ を積の微分公式で計算します。
   $$y'(t) = \frac{d}{dt}(C_1 + C_2 t)e^{2t} + (C_1 + C_2 t)\frac{d}{dt}(e^{2t}) = C_2 e^{2t} + 2(C_1 + C_2 t)e^{2t}$$
   $$y'(t) = (2C_1 + C_2 + 2C_2 t)e^{2t}$$
   式(C) に代入します。
   $$x(t) = (2C_1 + C_2 + 2C_2 t)e^{2t} - (C_1 + C_2 t)e^{2t} = (2C_1 - C_1 + C_2 + 2C_2 t - C_2 t)e^{2t}$$
   $$x(t) = (C_1 + C_2 + C_2 t)e^{2t}$$

---

### 【問題4】の解答・解説
#### 解答
1. （証明略、解説参照）
2. $v(x, y) = 2xy + 2y$

#### 詳細な計算ステップ
1. **第1問：調和関数であることの証明**
   調和関数であることを示すには、ラプラシアン $\Delta u = u_{xx} + u_{yy} = 0$ を示します。
   $u(x, y) = x^2 - y^2 + 2x$ について：
   * $u_x = \frac{\partial}{\partial x}(x^2 - y^2 + 2x) = 2x + 2 \implies u_{xx} = \frac{\partial}{\partial x}(2x + 2) = 2$
   * $u_y = \frac{\partial}{\partial y}(x^2 - y^2 + 2x) = -2y \implies u_{yy} = \frac{\partial}{\partial y}(-2y) = -2$
   これより：
   $$\Delta u = u_{xx} + u_{yy} = 2 + (-2) = 0$$
   ラプラス方程式を満たすため、 $u(x, y)$ は調和関数です。

2. **第2問：共役調和関数 $v(x, y)$ の決定**
   正則関数の必要十分条件である**コーシー・リーマンの関係式**：
   * $\frac{\partial v}{\partial y} = \frac{\partial u}{\partial x} \quad \cdots \text{(F)}$
   * $\frac{\partial v}{\partial x} = -\frac{\partial u}{\partial y} \quad \cdots \text{(G)}$
   を適用します。
   式(F) に $u_x = 2x+2$ を代入します。
   $$\frac{\partial v}{\partial y} = 2x + 2$$
   両辺を $y$ について積分します（$x$ は定数として扱います）。
   $$v(x, y) = \int (2x + 2) \,dy = 2xy + 2y + g(x) \quad \cdots \text{(H)}$$
   （$g(x)$ は積分定数に対応する $x$ のみの関数）
   式(H) を $x$ で偏微分します。
   $$\frac{\partial v}{\partial x} = 2y + g'(x)$$
   これを式(G) に代入します（$-u_y = -(-2y) = 2y$）。
   $$2y + g'(x) = 2y \implies g'(x) = 0 \implies g(x) = C \quad (C\text{は定数})$$
   したがって、共役調和関数は以下になります。
   $$v(x, y) = 2xy + 2y + C$$
   初期条件 $v(0, 0) = 0$ を代入します。
   $$v(0, 0) = 2(0)(0) + 2(0) + C = 0 \implies C = 0$$
   よって、求める関数は：
   $$v(x, y) = 2xy + 2y$$

---

### 【問題5】の解答・解説
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

### 【問題6】の解答・解説
#### 解答
1. $H = \{0, 6, 12, 18\}$ 、 $|H| = 4$
2. $|G/H| = 6$
3. $G/H = \{ 0+H, 1+H, 2+H, 3+H, 4+H, 5+H \}$

#### 詳細な計算ステップ
1. **第1問：部分群 $H$ の決定**
   群 $G = \mathbb{Z}_{24}$ の演算は加法（法24の足し算）です。元 6 が生成する部分群 $H$ は、 6 を繰り返し加えることで得られる剰余類の集合です。
   * $6 \times 1 = 6$
   * $6 \times 2 = 12$
   * $6 \times 3 = 18$
   * $6 \times 4 = 24 \equiv 0 \pmod{24}$ （単位元に戻る）
   したがって、部分群の要素は $H = \{0, 6, 12, 18\}$ です。
   要素の個数である位数 $|H|$ は **4** です。

2. **第2問：剰余群の位数**
   ラグランジュの定理により、剰余群 $G/H$ の位数（元、すなわち剰余類の個数）は：
   $$|G/H| = \frac{|G|}{|H|} = \frac{24}{4} = 6$$

3. **第3問：剰余群のすべての剰余類**
   剰余群の要素はコセット（剰余類） $a + H$ です。 $a = 0, 1, 2, 3, 4, 5$ に対して異なる剰余類が以下のように得られます。
   * $0 + H = \{0, 6, 12, 18\}$
   * $1 + H = \{1, 7, 13, 19\}$
   * $2 + H = \{2, 8, 14, 20\}$
   * $3 + H = \{3, 9, 15, 21\}$
   * $4 + H = \{4, 10, 16, 22\}$
   * $5 + H = \{5, 11, 17, 23\}$
   （これら6つで群 $G$ の全24元が重複なく分割されます。）
   したがって、剰余群 $G/H$ の元は以下の6つです。
   $$G/H = \{ 0+H, 1+H, 2+H, 3+H, 4+H, 5+H \}$$

---

### 【問題7】の解答・解説
#### 解答
$[1.28, \; 6.50]$ （または $1.28 \le \sigma^2 \le 6.50$）

#### 詳細な計算ステップ
1. **推定統計量の選択**
   母平均 $\mu$ が未知の正規分布から得られたサイズ $n$ の標本の不偏分散を $s^2$ とするとき、統計量：
   $$\chi^2 = \frac{(n-1)s^2}{\sigma^2}$$
   は自由度 $n-1$ のカイ二乗分布に従います。
   本問では $n = 10 \implies$ 自由度は $9$ です。 不偏分散は $s^2 = 2.4$ です。

2. **信頼区間の境界条件の設定**
   信頼係数 $90\%$ の信頼区間を設定するため、自由度 9 のカイ二乗分布の両側 $5\%$ 点（上側 $5\%$ 点と上側 $95\%$ 点）を用いて次のように不等式を作ります。
   $$\chi^2_{0.95}(9) \le \frac{9s^2}{\sigma^2} \le \chi^2_{0.05}(9)$$
   与えられた値 $\chi^2_{0.95}(9) = 3.325$ および $\chi^2_{0.05}(9) = 16.92$ を代入します。
   $$3.325 \le \frac{9 \times 2.4}{\sigma^2} \le 16.92$$
   分子の値を求めます： $9 \times 2.4 = 21.6$。
   $$3.325 \le \frac{21.6}{\sigma^2} \le 16.92$$

3. **不等式の変形（逆数の計算）**
   各数の逆数をとると、不等号の向きが反転します。
   $$\frac{1}{16.92} \le \frac{\sigma^2}{21.6} \le \frac{1}{3.325}$$
   各辺に $21.6$ を掛けます。
   $$\frac{21.6}{16.92} \le \sigma^2 \le \frac{21.6}{3.325}$$

4. **端数処理の計算**
   * **下限値**：
     $$\frac{21.6}{16.92} = \frac{2160}{1692} \approx 1.27659 \implies \text{四捨五入して } 1.28$$
   * **上限値**：
     $$\frac{21.6}{3.325} = \frac{21600}{3325} \approx 6.49624 \implies \text{四捨五入して } 6.50$$

したがって、求める母分散 $\sigma^2$ の $90\%$ 信頼区間は：
$$1.28 \le \sigma^2 \le 6.50$$

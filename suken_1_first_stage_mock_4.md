# 数学検定1級 一次試験（計算技能）模擬試験［第4回］

数学検定1級一次試験（計算技能）対策のための、第4回模擬試験問題（全7問）と詳細な解答解説です。今回の模擬試験では、媒介変数や球面座標の多重積分、行列の線形独立条件、高階複素微分、置換群（対称群）、および標本統計量（$t$値）の計算など、より高度かつ実践的な計算手法を扱います。

---

## 模擬試験問題（制限時間：60分）

### 【問題1】微分積分学（球面座標の3重積分）
次の3重積分の値を求めよ。
$$I = \iiint_V z \,dx\,dy\,dz$$
ただし、積分領域 $V$ は半径 $R$ の上半球体とする。
$$V = \{ (x, y, z) \in \mathbb{R}^3 \mid x^2 + y^2 + z^2 \le R^2, \; z \ge 0 \} \quad (R > 0)$$

### 【問題2】線形代数（線形独立・パラメータ決定）
次の 3つの 3次元ベクトル $\mathbf{v}_1, \mathbf{v}_2, \mathbf{v}_3$ が線形従属（一次従属）となるような、実数 $a$ の値を求めよ。
$$\mathbf{v}_1 = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}, \quad \mathbf{v}_2 = \begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix}, \quad \mathbf{v}_3 = \begin{pmatrix} 2 \\ a \\ 2 \end{pmatrix}$$

### 【問題3】微分方程式（1階同次形）
次の同次形微分方程式の一般解を求めよ。
$$\frac{dy}{dx} = \frac{x+y}{x} \quad (x > 0)$$

### 【問題4】複素解析（コーシーの積分公式・高階微分）
複素平面上の反時計回りの円 $C: |z| = 2$ において、次の周回積分の値を求めよ。
$$I = \oint_C \frac{\sin z}{(z - \pi/4)^3} \,dz$$

### 【問題5】整数論（ユークリッドの互除法とベズー等式）
1. ユークリッドの互除法を用いて、 $143$ と $104$ の最大公約数 $d = \gcd(143, 104)$ を求めよ。
2. 一次不定方程式 $143x + 104y = d$ を満たす整数の組 $(x, y)$ の1つを求めよ。

### 【問題6】代数学（対称群・置換）
5次対称群 $S_5$ の置換 $\sigma$ が以下のように与えられている。
$$\sigma = \begin{pmatrix} 1 & 2 & 3 & 4 & 5 \\ 3 & 5 & 4 & 1 & 2 \end{pmatrix}$$
1. 置換 $\sigma$ を互いに素な巡回置換の積として表せ。
2. 置換 $\sigma$ の位数（order）を求めよ。
3. 置換 $\sigma$ は偶置換か奇置換かを判定せよ。

### 【問題7】確率・統計（不偏分散と $t$ 検定統計量）
ある正規分布 $N(\mu, \sigma^2)$ から抽出された大きさ $n=5$ の標本データが、以下のように観測された。
$$\{1, \; 3, \; 4, \; 5, \; 7\}$$
1. 標本平均 $\bar{x}$ を求めよ。
2. 不偏分散 $s^2$ を求めよ。
3. 帰無仮説 $H_0: \mu = 3$ のもとでの $t$ 検定統計量 $t = \frac{\bar{x} - \mu_0}{s / \sqrt{n}}$ の値を求めよ。

---
---

## 解答・解説

### 【問題1】の解答・解説
#### 解答
$$I = \frac{\pi R^4}{4}$$

#### 詳細な計算ステップ
1. **変数変換（球面座標系）**
   積分変数 $(x, y, z)$ を球面座標系 $(\rho, \theta, \phi)$ に変換します：
   $$x = \rho \sin \phi \cos \theta, \quad y = \rho \sin \phi \sin \theta, \quad z = \rho \cos \phi$$
   このとき、積分領域 $V$ （半径 $R$ の上半球体 $x^2 + y^2 + z^2 \le R^2, \; z \ge 0$）に対応する各変数の動く範囲は次のようになります：
   * 半径： $0 \le \rho \le R$
   * 水平角（経度）： $0 \le \theta \le 2\pi$
   * 仰角（余緯度）： $0 \le \phi \le \frac{\pi}{2}$ （$z \ge 0 \implies \rho \cos \phi \ge 0 \implies \cos \phi \ge 0$ より）

2. **ヤコビアンの計算**
   球面座標変換におけるヤコビ行列 $J$ の行列式（ヤコビアン）は以下の通りです：
   $$J = \frac{\partial(x, y, z)}{\partial(\rho, \theta, \phi)} = \begin{pmatrix}
   \sin\phi\cos\theta & -\rho\sin\phi\sin\theta & \rho\cos\phi\cos\theta \\
   \sin\phi\sin\theta & \rho\sin\phi\cos\theta & \rho\cos\phi\sin\theta \\
   \cos\phi & 0 & -\rho\sin\phi
   \end{pmatrix}$$
   第3行に関して余因子展開を行うと：
   $$\det(J) = \cos\phi \begin{vmatrix} -\rho\sin\phi\sin\theta & \rho\cos\phi\cos\theta \\ \rho\sin\phi\cos\theta & \rho\cos\phi\sin\theta \end{vmatrix} - \rho\sin\phi \begin{vmatrix} \sin\phi\cos\theta & -\rho\sin\phi\sin\theta \\ \sin\phi\sin\theta & \rho\sin\phi\cos\theta \end{vmatrix}$$
   各 $2 \times 2$ 行列式を計算します：
   $$\begin{vmatrix} -\rho\sin\phi\sin\theta & \rho\cos\phi\cos\theta \\ \rho\sin\phi\cos\theta & \rho\cos\phi\sin\theta \end{vmatrix} = -\rho^2 \sin\phi\cos\phi\sin^2\theta - \rho^2 \sin\phi\cos\phi\cos^2\theta = -\rho^2 \sin\phi\cos\phi$$
   $$\begin{vmatrix} \sin\phi\cos\theta & -\rho\sin\phi\sin\theta \\ \sin\phi\sin\theta & \rho\sin\phi\cos\theta \end{vmatrix} = \rho \sin^2\phi\cos^2\theta + \rho \sin^2\phi\sin^2\theta = \rho \sin^2\phi$$
   これらを代入して整理すると：
   $$\det(J) = \cos\phi(-\rho^2 \sin\phi\cos\phi) - \rho\sin\phi(\rho \sin^2\phi) = -\rho^2 \sin\phi(\cos^2\phi + \sin^2\phi) = -\rho^2 \sin\phi$$
   積分体積要素の大きさ（ヤコビ行列式の絶対値）は、 $\phi \in [0, \pi/2]$ において $\sin\phi \ge 0$ であるため次のようになります：
   $$dx\,dy\,dz = |\det(J)| \,d\rho\,d\theta\,d\phi = \rho^2 \sin\phi \,d\rho\,d\theta\,d\phi$$

3. **累次積分への変換**
   元の3重積分に座標変換とヤコビアンを適用します：
   $$I = \int_{0}^{\frac{\pi}{2}} \int_{0}^{2\pi} \int_{0}^{R} (\rho \cos\phi) \cdot (\rho^2 \sin\phi) \,d\rho\,d\theta\,d\phi = \int_{0}^{\frac{\pi}{2}} \int_{0}^{2\pi} \int_{0}^{R} \rho^3 \sin\phi\cos\phi \,d\rho\,d\theta\,d\phi$$

4. **各積分の実行**
   被積分関数がそれぞれの変数の積に分離可能であるため、個別に積分を計算します：
   $$I = \left( \int_{0}^{R} \rho^3 \,d\rho \right) \left( \int_{0}^{2\pi} d\theta \right) \left( \int_{0}^{\frac{\pi}{2}} \sin\phi\cos\phi \,d\phi \right)$$
   * **$\rho$ の積分**：
     $$\int_{0}^{R} \rho^3 \,d\rho = \left[ \frac{\rho^4}{4} \right]_0^R = \frac{R^4}{4}$$
   * **$\theta$ の積分**：
     $$\int_{0}^{2\pi} d\theta = \left[ \theta \right]_0^{2\pi} = 2\pi$$
   * **$\phi$ の積分**：
     $\sin\phi = t$ とおくと、 $\cos\phi \,d\phi = dt$。積分範囲は $\phi: 0 \to \frac{\pi}{2}$ のとき $t: 0 \to 1$ となります：
     $$\int_{0}^{\frac{\pi}{2}} \sin\phi\cos\phi \,d\phi = \int_0^1 t \,dt = \left[ \frac{t^2}{2} \right]_0^1 = \frac{1}{2}$$

5. **最終的な計算結果**
   これら3つの積分値を掛け合わせます：
   $$I = \frac{R^4}{4} \times 2\pi \times \frac{1}{2} = \frac{\pi R^4}{4}$$

---

### 【問題2】の解答・解説
#### 解答
$$a = 0$$

#### 詳細な計算ステップ
1. **線形従属の条件式**
   3つの3次元ベクトル $\mathbf{v}_1, \mathbf{v}_2, \mathbf{v}_3$ が線形従属であるとは、一次関係式：
   $$c_1 \mathbf{v}_1 + c_2 \mathbf{v}_2 + c_3 \mathbf{v}_3 = \mathbf{0}$$
   を満たす、すべてが $0$ ではない実数の組 $(c_1, c_2, c_3)$ が存在することです。
   これは、これらのベクトルを列に持つ $3 \times 3$ 行列の行列式が $0$ になることと同値です：
   $$D = \begin{vmatrix} \mathbf{v}_1 & \mathbf{v}_2 & \mathbf{v}_3 \end{vmatrix} = \begin{vmatrix} 1 & 1 & 2 \\ 2 & 0 & a \\ 3 & 1 & 2 \end{vmatrix} = 0$$

2. **行列式の行基本変形**
   行列式の性質を用いて計算を簡単にします。第3行から第1行を引きます（第3行 $\to$ 第3行 $-$ 第1行）：
   $$D = \begin{vmatrix} 1 & 1 & 2 \\ 2 & 0 & a \\ 3-1 & 1-1 & 2-2 \end{vmatrix} = \begin{vmatrix} 1 & 1 & 2 \\ 2 & 0 & a \\ 2 & 0 & 0 \end{vmatrix}$$

3. **余因子展開による計算**
   第2列には $0$ が2つ含まれているため、第2列について余因子展開を行います：
   $$D = (-1)^{1+2} \cdot 1 \cdot \begin{vmatrix} 2 & a \\ 2 & 0 \end{vmatrix} = -1 \cdot (2 \cdot 0 - a \cdot 2) = -1 \cdot (-2a) = 2a$$
   （※別解：サラスの公式による直接計算）
   $$D = (1\cdot 0\cdot 2 + 1\cdot a\cdot 3 + 2\cdot 2\cdot 1) - (3\cdot 0\cdot 2 + 1\cdot 2\cdot 2 + 2\cdot a\cdot 1)$$
   $$D = (0 + 3a + 4) - (0 + 4 + 2a) = 2a$$

4. **パラメータの決定**
   線形従属であるための条件 $D = 0$ より：
   $$2a = 0 \implies a = 0$$

---

### 【問題3】の解答・解説
#### 解答
$$y = x(\log x + C) \quad (C\text{は任意定数})$$

#### 詳細な計算ステップ
1. **同次形微分方程式の確認**
   右辺を分解して整理します：
   $$\frac{dy}{dx} = \frac{x+y}{x} = 1 + \frac{y}{x}$$
   右辺が $\frac{y}{x}$ のみで構成されるため、この微分方程式は1階同次形です。

2. **変数変換の導入**
   $u = \frac{y}{x}$ とおきます。これは $y = ux$ と表せます。
   両辺を $x$ で微分すると、積の微分公式より：
   $$\frac{dy}{dx} = \frac{d}{dx}(ux) = u \cdot 1 + x \cdot \frac{du}{dx} = u + x\frac{du}{dx}$$

3. **微分方程式の代入と簡略化**
   これらを元の微分方程式に代入します：
   $$u + x\frac{du}{dx} = 1 + u$$
   両辺から $u$ を引くと、次のようになります：
   $$x\frac{du}{dx} = 1$$

4. **変数分離と積分**
   $x > 0$ であるため、両辺を $x$ で割ることができます：
   $$du = \frac{1}{x} \,dx$$
   両辺を積分します：
   $$\int 1 \,du = \int \frac{1}{x} \,dx$$
   $$u = \log x + C \quad (C\text{は任意定数})$$
   （※ $x > 0$ より絶対値記号は不要です）

5. **変数の復元**
   $u = \frac{y}{x}$ を元の式に戻します：
   $$\frac{y}{x} = \log x + C \implies y = x(\log x + C)$$

---

### 【問題4】の解答・解説
#### 解答
$$-\frac{\sqrt{2}}{2}\pi i$$

#### 詳細な計算ステップ
1. **コーシーの積分公式（高階微分）の定理**
   関数 $f(z)$ が単一閉曲線 $C$ およびその内部で正則であり、 $a$ が $C$ の内部の点であるとき、次の公式が成り立ちます：
   $$\oint_C \frac{f(z)}{(z-a)^{n+1}} \,dz = \frac{2\pi i}{n!} f^{(n)}(a)$$

2. **適用条件の確認**
   本問の積分式 $I = \oint_C \frac{\sin z}{(z - \pi/4)^3} \,dz$ を公式と比較します：
   * $f(z) = \sin z$ （複素平面全体で正則）
   * $a = \frac{\pi}{4}$
   * $n = 2$ （分母の指数 $n+1 = 3 \implies n = 2$）
   特異点 $a = \frac{\pi}{4}$ は、積分経路である円 $C: |z| = 2$ の内部に含まれるか確認します：
   $$\left|\frac{\pi}{4}\right| \approx \frac{3.1416}{4} \approx 0.785 < 2$$
   したがって、特異点は円の内部にあるため、公式が適用できます。

3. **2階導関数の計算**
   $f(z) = \sin z$ を 2回微分します：
   $$f'(z) = \cos z \implies f''(z) = -\sin z$$

4. **特異点における値の代入**
   $z = \frac{\pi}{4}$ を 2階導関数に代入します：
   $$f''\left(\frac{\pi}{4}\right) = -\sin\left(\frac{\pi}{4}\right) = -\frac{\sqrt{2}}{2}$$

5. **積分の計算**
   公式に代入して計算を行います：
   $$I = \frac{2\pi i}{2!} f''\left(\frac{\pi}{4}\right) = \pi i \left(-\frac{\sqrt{2}}{2}\right) = -\frac{\sqrt{2}}{2}\pi i$$

---

### 【問題5】の解答・解説
#### 解答
1. $d = 13$
2. $(x, y) = (3, -4)$ （またはその整数倍を加えた一般解）

#### 詳細な計算ステップ
1. **ユークリッドの互除法による最大公約数 $d$ の計算**
   $143$ を $104$ で順次割り、余りが $0$ になるまで繰り返します：
   * **ステップ1**： $143 = 104 \times 1 + 39$ （余り $39$）
   * **ステップ2**： $104 = 39 \times 2 + 26$ （余り $26$）
   * **ステップ3**： $39 = 26 \times 1 + 13$ （余り $13$）
   * **ステップ4**： $26 = 13 \times 2 + 0$ （余り $0$）
   最後に割り切れたときの除数（または直前の余り）が最大公約数になります：
   $$d = \gcd(143, 104) = 13$$

2. **ベズー等式 $143x + 104y = 13$ の逆算（バック・サブスティテューション）**
   上のステップ1〜3の式を、それぞれの「余り」について整理します：
   * (A) $39 = 143 - 104 \times 1$
   * (B) $26 = 104 - 39 \times 2$
   * (C) $13 = 39 - 26 \times 1$
   
   式(C)から出発し、式(B), (A)を順に代入して余りを消去します：
   * **ステップA**（式Bを代入して $26$ を消去）：
     $$13 = 39 - (104 - 39 \times 2) \times 1$$
     $$13 = 39 \times 3 - 104 \times 1$$
   * **ステップB**（式Aを代入して $39$ を消去）：
     $$13 = (143 - 104 \times 1) \times 3 - 104 \times 1$$
     $$13 = 143 \times 3 - 104 \times 3 - 104 \times 1$$
     $$13 = 143 \times 3 + 104 \times (-4)$$
   
   この式は元の不定方程式 $143x + 104y = 13$ の形になっているため、整数の組の1つとして以下が得られます：
   $$(x, y) = (3, -4)$$

---

### 【問題6】の解答・解説
#### 解答
1. $\sigma = (1 \; 3 \; 4)(2 \; 5)$
2. 6
3. 奇置換

#### 詳細な計算ステップ
1. **巡回置換への分解**
   置換 $\sigma$ の各元の写り先を順に追いかけます：
   * $1$ の写り先： $1 \to 3$
   * $3$ の写り先： $3 \to 4$
   * $4$ の写り先： $4 \to 1$ （ここで閉じたので、巡回置換 $(1 \; 3 \; 4)$ が得られます）
   * $2$ の写り先： $2 \to 5$
   * $5$ の写り先： $5 \to 2$ （ここで閉じたので、巡回置換 $(2 \; 5)$ が得られます）
   したがって、 $\sigma$ は互いに素な巡回置換の積として以下のように表されます：
   $$\sigma = (1 \; 3 \; 4)(2 \; 5)$$

2. **位数の計算**
   互いに素な巡回置換の積の位数は、それぞれの巡回置換の長さ（要素数）の最小公倍数（LCM）です：
   * 巡回置換 $(1 \; 3 \; 4)$ の長さは $3$
   * 巡回置換 $(2 \; 5)$ の長さは $2$
   したがって、位数（$\operatorname{ord}(\sigma)$）は以下の通りです：
   $$\operatorname{ord}(\sigma) = \operatorname{lcm}(3, 2) = 6$$

3. **偶置換・奇置換の判定**
   長さ $k$ の巡回置換は、$k-1$ 個の互換（長さ2の置換）の積で表すことができます：
   * $(1 \; 3 \; 4) = (1 \; 4)(1 \; 3)$ （互換2個の積）
   * $(2 \; 5)$ （互換1個の積）
   よって、置換 $\sigma$ 全体は以下の互換の積になります：
   $$\sigma = (1 \; 4)(1 \; 3)(2 \; 5)$$
   これは $3$ 個（奇数個）の互換の積であるため、 $\sigma$ は**奇置換**です。

---

### 【問題7】の解答・解説
#### 解答
1. $\bar{x} = 4$
2. $s^2 = 5$
3. $t = 1$

#### 詳細な計算ステップ
1. **標本平均 $\bar{x}$ の計算**
   標本サイズ $n = 5$ のデータ $\{1, 3, 4, 5, 7\}$ の合計値を求め、データ数で割ります：
   $$\bar{x} = \frac{1 + 3 + 4 + 5 + 7}{5} = \frac{20}{5} = 4$$

2. **不偏分散 $s^2$ の計算**
   各データの標本平均 $\bar{x} = 4$ からの偏差とその平方を求めます：
   * $x_1 = 1 \implies (1 - 4)^2 = (-3)^2 = 9$
   * $x_2 = 3 \implies (3 - 4)^2 = (-1)^2 = 1$
   * $x_3 = 4 \implies (4 - 4)^2 = 0^2 = 0$
   * $x_4 = 5 \implies (5 - 4)^2 = 1^2 = 1$
   * $x_5 = 7 \implies (7 - 4)^2 = 3^2 = 9$
   
   偏差平方和を求めます：
   $$\sum_{i=1}^5 (x_i - \bar{x})^2 = 9 + 1 + 0 + 1 + 9 = 20$$
   不偏分散の分母は自由度 $n - 1 = 5 - 1 = 4$ となります：
   $$s^2 = \frac{20}{4} = 5$$

3. **$t$ 検定統計量の計算**
   帰無仮説の基準値 $\mu_0 = 3$ のもとでの $t$ 値の公式に値を代入します。不偏分散 $s^2 = 5 \implies$ 標本標準偏差 $s = \sqrt{5}$ です：
   $$t = \frac{\bar{x} - \mu_0}{s / \sqrt{n}} = \frac{4 - 3}{\sqrt{5} / \sqrt{5}} = \frac{1}{1} = 1$$

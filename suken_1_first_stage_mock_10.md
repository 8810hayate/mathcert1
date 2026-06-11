# 数学検定1級 一次試験（計算技能）模擬試験［第10回］

数学検定1級一次試験（計算技能）対策のための、第10回模擬試験問題（全7問）と詳細な解答解説です。今回の模擬試験では、極座標における曲線の長さ（カージオイド）、平面への直交射影ベクトル、非同次オイラー・コーシーの微分方程式（定数変化法）、複素領域における零点の個数（ルーシェの定理）、ベクトルポテンシャルの構成、多項式剰余環における乗法逆元、ポアソン分布の最尤推定量など、一次試験で出題されうる難度の高い応用計算問題の総仕上げを行います。

---

## 模擬試験問題（制限時間：60分）

### 【問題1】微分積分学（極座標における曲線の長さ）
極方程式 $r = a(1 + \cos \theta) \quad (a > 0, \; 0 \le \theta \le 2\pi)$ で表される曲線（カージオイド・心臓形）の全周の長さ $L$ を求めよ。

### 【問題2】線形代数（平面への直交射影）
3次元空間のベクトル $\mathbf{v} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$ の、方程式 $x - y + 2z = 0$ で表される平面への直交射影ベクトル $\mathbf{p}$ を求めよ。

### 【問題3】微分方程式（非同次オイラー・コーシー方程式）
次の微分方程式の一般解を求めよ。
$$x^2 y'' - x y' + y = x \log x \quad (x > 0)$$

### 【問題4】複素解析（ルーシェの定理・零点の個数）
代数方程式 $z^5 + 3z^2 + 1 = 0$ は、単位円板 $|z| < 1$ の内部にいくつの根を持つか求めよ。

### 【問題5】ベクトル解析（ベクトルポテンシャルの決定）
湧き出しのない（非圧縮な）ベクトル場 $\mathbf{F}(x, y, z) = (y-z, \; z-x, \; x-y)$ に対し、 $\nabla \times \mathbf{A} = \mathbf{F}$ を満たすベクトルポテンシャル $\mathbf{A}(x, y, z)$ の1つを求めよ。

### 【問題6】代数学・整数論（多項式剰余環における逆元）
多項式環の剰余環 $\mathbb{Q}[x]/(x^2 + 2x + 3)$ において、元 $x + 1$ の乗法逆元（逆数）を求めよ。

### 【問題7】確率・統計（ポアソン分布の最尤推定量）
あるポアソン分布 $\operatorname{Po}(\lambda)$ （パラメータ $\lambda > 0$）から、大きさ $n$ のランダム標本 $\{x_1, x_2, \dots, x_n\}$ が抽出された。
このとき、対数尤度関数を最大化することにより、 $\lambda$ の最尤推定量（Maximum Likelihood Estimator） $\hat{\lambda}$ を標本平均 $\bar{x} = \frac{1}{n}\sum_{i=1}^n x_i$ を用いて表せ。

---
---

## 解答・解説

### 【問題1】の解答・解説
#### 解答
$$L = 8a$$

#### 詳細な計算ステップ
1. **極座標における曲線の長さの公式**
   極方程式 $r = f(\theta)$ で表される曲線の、区間 $[\alpha, \beta]$ における長さ $L$ は次の積分で求められます：
   $$L = \int_{\alpha}^{\beta} \sqrt{r^2 + \left(\frac{dr}{d\theta}\right)^2} \,d\theta$$

2. **微分の計算**
   $r = a(1 + \cos\theta)$ より：
   $$\frac{dr}{d\theta} = -a \sin\theta$$

3. **根号内の計算**
   $$r^2 + \left(\frac{dr}{d\theta}\right)^2 = a^2(1 + \cos\theta)^2 + a^2 \sin^2\theta = a^2(1 + 2\cos\theta + \cos^2\theta + \sin^2\theta)$$
   三角関数の基本相互関係 $\cos^2\theta + \sin^2\theta = 1$ を代入します：
   $$= a^2(2 + 2\cos\theta) = 2a^2(1 + \cos\theta)$$

4. **半角の公式を用いた変形**
   半角の公式 $\cos^2\frac{\theta}{2} = \frac{1+\cos\theta}{2} \implies 1 + \cos\theta = 2\cos^2\frac{\theta}{2}$ を適用して、根号を外せるように変形します：
   $$2a^2(1 + \cos\theta) = 2a^2 \cdot 2\cos^2\frac{\theta}{2} = 4a^2 \cos^2\frac{\theta}{2}$$
   したがって：
   $$\sqrt{r^2 + \left(\frac{dr}{d\theta}\right)^2} = \sqrt{4a^2 \cos^2\frac{\theta}{2}} = 2a \left| \cos\frac{\theta}{2} \right|$$

5. **定積分の計算**
   カージオイドの対称性から、 $\theta$ が $0 \to \pi$ の範囲で積分して 2倍します。
   この範囲では $\cos\frac{\theta}{2} \ge 0$ なので、絶対値記号をそのまま外せます：
   $$L = 2 \int_0^{\pi} 2a \cos\frac{\theta}{2} \,d\theta = 4a \left[ 2\sin\frac{\theta}{2} \right]_0^{\pi} = 8a \left( \sin\frac{\pi}{2} - \sin 0 \right) = 8a$$

---

### 【問題2】の解答・解説
#### 解答
$$\mathbf{p} = \frac{1}{6}\begin{pmatrix} 1 \\ 17 \\ 8 \end{pmatrix}$$

#### 詳細な計算ステップ
1. **平面の法線ベクトルの特定**
   平面 $x - y + 2z = 0$ の法線ベクトルは、方程式の係数から直ちに得られます：
   $$\mathbf{n} = \begin{pmatrix} 1 \\ -1 \\ 2 \end{pmatrix}$$

2. **法線方向への射影ベクトルの計算**
   ベクトル $\mathbf{v}$ の、法線ベクトル $\mathbf{n}$ への直交射影ベクトル $\mathbf{v}_{\mathbf{n}}$ を求めます。公式は次の通りです：
   $$\mathbf{v}_{\mathbf{n}} = \left( \frac{\mathbf{v} \cdot \mathbf{n}}{\|\mathbf{n}\|^2} \right) \mathbf{n}$$
   * 内積： $\mathbf{v} \cdot \mathbf{n} = 1(1) + 2(-1) + 3(2) = 1 - 2 + 6 = 5$
   * ノルムの平方： $\|\mathbf{n}\|^2 = 1^2 + (-1)^2 + 2^2 = 6$
   
   したがって：
   $$\mathbf{v}_{\mathbf{n}} = \frac{5}{6} \begin{pmatrix} 1 \\ -1 \\ 2 \end{pmatrix}$$

3. **平面への直交射影ベクトルの計算**
   平面への直交射影ベクトル $\mathbf{p}$ は、元のベクトル $\mathbf{v}$ から法線方向への射影成分を引き算したものです：
   $$\mathbf{p} = \mathbf{v} - \mathbf{v}_{\mathbf{n}} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix} - \frac{5}{6}\begin{pmatrix} 1 \\ -1 \\ 2 \end{pmatrix} = \begin{pmatrix} 1 - 5/6 \\ 2 + 5/6 \\ 3 - 10/6 \end{pmatrix} = \begin{pmatrix} 1/6 \\ 17/6 \\ 8/6 \end{pmatrix} = \frac{1}{6}\begin{pmatrix} 1 \\ 17 \\ 8 \end{pmatrix}$$

---

### 【問題3】の解答・解説
#### 解答
$$y = C_1 x + C_2 x \log x + \frac{1}{6} x (\log x)^3 \quad (C_1, C_2\text{は任意定数})$$

#### 詳細な計算ステップ
1. **同次方程式の基本解の決定**
   同次微分方程式 $x^2 y'' - x y' + y = 0$ の特性方程式を求めるため、 $y = x^r$ と仮定して代入します：
   $$r(r-1) - r + 1 = 0 \implies r^2 - 2r + 1 = 0 \implies (r-1)^2 = 0$$
   重根 $r = 1$ を得るため、同次解は次のようになります：
   $$y_h = (C_1 + C_2 \log x) x$$
   基本解は $y_1 = x$、 $y_2 = x\log x$ です。

2. **ロンスキー行列式（Wronskian）の計算**
   $$W(x) = \begin{vmatrix} y_1 & y_2 \\ y_1' & y_2' \end{vmatrix} = \begin{vmatrix} x & x\log x \\ 1 & \log x + 1 \end{vmatrix} = x(\log x + 1) - 1(x\log x) = x$$

3. **定数変化法の適用**
   微分方程式の両辺を $x^2$ で割り、標準形にします：
   $$y'' - \frac{1}{x} y' + \frac{1}{x^2} y = \frac{\log x}{x}$$
   非同次項を $f(x) = \frac{\log x}{x}$ とします。特解を $y_p = u_1(x)y_1 + u_2(x)y_2$ とおくと、定数変化法の公式より：
   * **$u_1(x)$ の計算**：
     $$u_1(x) = \int \frac{-y_2(x) f(x)}{W(x)} \,dx = \int \frac{-(x\log x) \cdot \frac{\log x}{x}}{x} \,dx = \int -\frac{(\log x)^2}{x} \,dx$$
     $\log x = t \implies \frac{1}{x} \,dx = dt$ と置換します：
     $$u_1(x) = \int -t^2 \,dt = -\frac{t^3}{3} = -\frac{(\log x)^3}{3}$$
   * **$u_2(x)$ の計算**：
     $$u_2(x) = \int \frac{y_1(x) f(x)}{W(x)} \,dx = \int \frac{x \cdot \frac{\log x}{x}}{x} \,dx = \int \frac{\log x}{x} \,dx$$
     同置換を用いて：
     $$u_2(x) = \int t \,dt = \frac{t^2}{2} = \frac{(\log x)^2}{2}$$

4. **特解 $y_p$ の構成**
   $$y_p = u_1(x)y_1 + u_2(x)y_2 = -\frac{(\log x)^3}{3} \cdot x + \frac{(\log x)^2}{2} \cdot x \log x = x(\log x)^3 \left( -\frac{1}{3} + \frac{1}{2} \right) = \frac{1}{6} x (\log x)^3$$

5. **一般解**
   $$y = y_h + y_p = C_1 x + C_2 x \log x + \frac{1}{6} x (\log x)^3$$

---

### 【問題4】の解答・解説
#### 解答
$$2\text{個}$$

#### 詳細な計算ステップ
1. **ルーシェの定理の整理**
   閉曲線 $C$ （本問では単位円 $|z|=1$ ）およびその内部で正則な関数 $f(z), g(z)$ について、 $C$ 上で $|f(z)| > |g(z)|$ が成り立つならば、 $f(z)$ と $f(z)+g(z)$ は $C$ の内部に同数の零点（根）を持ちます。

2. **関数の割り当てと絶対値の評価**
   与えられた多項式 $z^5 + 3z^2 + 1 = 0$ において、単位円 $|z|=1$ 上で最も絶対値が大きくなる支配的な項を探します：
   * $f(z) = 3z^2$ とおきます。 $|z|=1$ 上で：
     $$|f(z)| = 3|z|^2 = 3$$
   * $g(z) = z^5 + 1$ とおきます。三角不等式より、 $|z|=1$ 上で：
     $$|g(z)| = |z^5 + 1| \le |z|^5 + 1 = 1^5 + 1 = 2$$
   
   したがって、境界 $|z|=1$ 上で常に次の不等式が成り立ちます：
   $$|f(z)| = 3 > 2 \ge |g(z)| \implies |f(z)| > |g(z)|$$

3. **零点の個数の決定**
   ルーシェの定理より、求める多項式 $f(z)+g(z) = z^5 + 3z^2 + 1$ の $|z|<1$ における零点数は、 $f(z) = 3z^2$ の零点数と一致します。
   $3z^2 = 0$ は $|z|<1$ に $z=0$ （2重根）のみを零点として持つため、その個数は $2$ 個です。
   したがって、方程式 $z^5 + 3z^2 + 1 = 0$ が $|z|<1$ に持つ根の個数は **2個** です。

---

### 【問題5】の解答・解説
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

### 【問題6】の解答・解説
#### 解答
$$-\frac{1}{2}x - \frac{1}{2}$$

#### 詳細な計算ステップ
1. **剰余環と逆元の定義**
   多項式 $f(x) = x^2 + 2x + 3$ の判別式は $D = 2^2 - 4(1)(3) = -8 < 0$ であり、 $\mathbb{Q}$ 上で既約です。したがって、剰余環 $\mathbb{Q}[x]/(x^2 + 2x + 3)$ は体となります。
   $x + 1$ の逆元を $g(x) = ax + b$ （$a, b \in \mathbb{Q}$）とおき、剰余環において次の等式が成立するような $a, b$ を求めます：
   $$(x+1)(ax+b) \equiv 1 \pmod{x^2+2x+3}$$

2. **展開と次数の引き下げ**
   左辺を展開して整理します：
   $$(x+1)(ax+b) = ax^2 + (a+b)x + b$$
   法であるイデアルの関係式 $x^2 + 2x + 3 \equiv 0 \implies x^2 \equiv -2x - 3$ を代入して、次数を1次に引き下げます：
   $$ax^2 + (a+b)x + b \equiv a(-2x - 3) + (a+b)x + b \pmod{x^2+2x+3}$$
   $$= (-2a + a + b)x - 3a + b = (b-a)x + (b-3a)$$

3. **係数比較による方程式の解決**
   この式が $1$ （すなわち $0x + 1$）と合同にならなければなりません：
   $$(b-a)x + (b-3a) \equiv 0x + 1 \pmod{x^2+2x+3}$$
   係数を比較して連立方程式を立てます：
   $$\begin{cases} b - a = 0 \implies a = b \\ b - 3a = 1 \end{cases}$$
   $b = a$ を代入します：
   $$a - 3a = 1 \implies -2a = 1 \implies a = -\frac{1}{2}$$
   したがって、 $b = -\frac{1}{2}$ と決定されます。

4. **結論**
   求める逆元は次の通りです：
   $$-\frac{1}{2}x - \frac{1}{2}$$

---

### 【問題7】の解答・解説
#### 解答
$$\hat{\lambda} = \bar{x}$$

#### 詳細な計算ステップ
1. **ポアソン分布の確率質量関数と尤度関数**
   ポアソン分布 $\operatorname{Po}(\lambda)$ に従う確率変数の確率質量関数は次の通りです：
   $$P(X = x) = \frac{\lambda^x e^{-\lambda}}{x!}$$
   独立に抽出された大きさ $n$ のサンプルに対する尤度関数 $L(\lambda)$ は次のようになります：
   $$L(\lambda) = \prod_{i=1}^n P(X = x_i) = \prod_{i=1}^n \frac{\lambda^{x_i} e^{-\lambda}}{x_i!} = \frac{\lambda^{\sum x_i} e^{-n\lambda}}{\prod (x_i!)}$$

2. **対数尤度関数 $\log L(\lambda)$ の決定**
   最大化を行うため、尤度関数の自然対数をとります（積が和に変換され計算しやすくなります）：
   $$\log L(\lambda) = \log\left( \lambda^{\sum x_i} \right) + \log\left( e^{-n\lambda} \right) - \log\left( \prod (x_i!) \right)$$
   $$\log L(\lambda) = \left( \sum_{i=1}^n x_i \right) \log \lambda - n\lambda - \sum_{i=1}^n \log(x_i!)$$

3. **最尤方程式の立式と解法**
   パラメータ $\lambda$ について偏微分し、 $0$ とおきます：
   $$\frac{\partial}{\partial \lambda} \log L(\lambda) = \left( \sum_{i=1}^n x_i \right) \frac{1}{\lambda} - n = 0$$
   この式を最尤推定量 $\hat{\lambda}$ について解きます：
   $$\frac{1}{\hat{\lambda}} \sum_{i=1}^n x_i = n \implies \hat{\lambda} = \frac{1}{n} \sum_{i=1}^n x_i$$
   ここで標本平均 $\bar{x} = \frac{1}{n} \sum_{i=1}^n x_i$ を用いて表すと、次のようになります：
   $$\hat{\lambda} = \bar{x}$$
   （※2階微分は $\frac{\partial^2}{\partial \lambda^2} \log L(\lambda) = -\frac{1}{\lambda^2}\sum x_i < 0$ となり、極大かつ最大値であることを保証します。）

# 数学検定1級 一次試験 模擬問題：微分方程式 (Differential Equations)

数検1級一次試験対策のための、**微分方程式 (Differential Equations)**分野の模擬・演習問題（全16問）と詳細な解答解説です。

[分野別問題集トップに戻る](README.md)

---

## 【問題 1】微分方程式（境界値問題） （第1回 模擬試験・問題3）

### 問題
次の常微分方程式の境界値問題を解け。
$$y'' + 4y = 0, \quad y(0) = 1, \quad y\left(\frac{\pi}{4}\right) = 2$$

### 解答・解説
#### 解答
$$y = \cos 2x + 2\sin 2x$$

#### 詳細な計算ステップ
1. **一般解の決定**
   線形同次微分方程式 $y'' + 4y = 0$ を解くために、特性方程式を設定します。
   $$\lambda^2 + 4 = 0 \implies \lambda = \pm 2i$$
   特性根が純虚数 $\pm 2i$ なので、同次方程式の一般解は実数の形で以下のように書けます。
   $$y(x) = C_1 \cos 2x + C_2 \sin 2x \quad (C_1, C_2\text{は任意定数})$$

2. **初期条件1の適用**
   $y(0) = 1$ を代入します。
   $$y(0) = C_1 \cos 0 + C_2 \sin 0 = C_1 \cdot 1 + C_2 \cdot 0 = 1 \implies C_1 = 1$$
   これにより、解の形は $y(x) = \cos 2x + C_2 \sin 2x$ となります。

3. **初期条件2の適用**
   $y\left(\frac{\pi}{4}\right) = 2$ を代入します。
   $$y\left(\frac{\pi}{4}\right) = \cos\left(2 \cdot \frac{\pi}{4}\right) + C_2 \sin\left(2 \cdot \frac{\pi}{4}\right) = 2$$
   $$\cos\left(\frac{\pi}{2}\right) + C_2 \sin\left(\frac{\pi}{2}\right) = 2$$
   ここで、 $\cos\left(\frac{\pi}{2}\right) = 0$、 $\sin\left(\frac{\pi}{2}\right) = 1$ なので：
   $$0 + C_2 \cdot 1 = 2 \implies C_2 = 2$$

4. **特解の決定**
   定数を代入すると、求める境界値問題の解が得られます。
   $$y = \cos 2x + 2\sin 2x$$

---

## 【問題 2】微分方程式（1階線形） （第2回 模擬試験・問題4）

### 問題
次の微分方程式の初期値問題を解け。
$$\frac{dy}{dx} + y \tan x = \sin 2x, \quad y(0) = 1 \quad \left( -\frac{\pi}{2} < x < \frac{\pi}{2} \right)$$

### 解答・解説
#### 解答
$$y = 3\cos x - 2\cos^2 x$$

#### 詳細な計算ステップ
1. **標準形と積分因子の決定**
   微分方程式は $\frac{dy}{dx} + P(x)y = Q(x)$ の線形標準形をしています。ここで $P(x) = \tan x$, $Q(x) = \sin 2x$ です。
   積分因子 $I(x)$ を求めます。
   $$I(x) = e^{\int \tan x \,dx} = e^{-\log|\cos x|} = e^{\log\left(\frac{1}{|\cos x|}\right)} = \frac{1}{|\cos x|}$$
   定義された区間 $-\frac{\pi}{2} < x < \frac{\pi}{2}$ では、 $\cos x > 0$ であるため、絶対値記号を外して $I(x) = \frac{1}{\cos x}$ とできます。

2. **方程式への積分因子の乗算**
   方程式の両辺に $\frac{1}{\cos x}$ を掛けます。
   $$\frac{1}{\cos x} \frac{dy}{dx} + y \frac{\sin x}{\cos^2 x} = \frac{\sin 2x}{\cos x}$$
   左辺は積の微分公式 $\frac{d}{dx}\left( y \cdot \frac{1}{\cos x} \right)$ そのものです。
   右辺は倍角公式 $\sin 2x = 2\sin x \cos x$ を代入して整理します。
   $$\frac{\sin 2x}{\cos x} = \frac{2\sin x \cos x}{\cos x} = 2\sin x$$
   これより、方程式は以下のように整理されます。
   $$\frac{d}{dx} \left( \frac{y}{\cos x} \right) = 2\sin x$$

3. **積分と一般解の導出**
   両辺を $x$ について積分します。
   $$\frac{y}{\cos x} = \int 2\sin x \,dx = -2\cos x + C \quad (C\text{は任意定数})$$
   両辺に $\cos x$ を掛けます。
   $$y = -2\cos^2 x + C\cos x$$

4. **初期条件による定数の決定**
   $y(0) = 1$ を代入します。 $\cos 0 = 1$ です。
   $$1 = -2(1)^2 + C(1) \implies 1 = -2 + C \implies C = 3$$
   したがって、求める初期値問題の解は：
   $$y = 3\cos x - 2\cos^2 x$$

---

## 【問題 3】微分方程式（連立常微分方程式） （第3回 模擬試験・問題3）

### 問題
次の連立微分方程式の一般解を求めよ。
$$\begin{cases} \frac{dx}{dt} = 3x - y \\ \frac{dy}{dt} = x + y \end{cases}$$

### 解答・解説
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

## 【問題 4】微分方程式（1階同次形） （第4回 模擬試験・問題3）

### 問題
次の同次形微分方程式の一般解を求めよ。
$$\frac{dy}{dx} = \frac{x+y}{x} \quad (x > 0)$$

### 解答・解説
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

## 【問題 5】微分方程式（定数変化法） （第5回 模擬試験・問題3）

### 問題
微分演算子や未定係数法ではなく、**定数変化法（variation of parameters）**を用いて、次の2階非同次線形微分方程式の特解（および一般解）を求めよ。
$$y'' + y = \tan x \quad \left( -\frac{\pi}{2} < x < \frac{\pi}{2} \right)$$

### 解答・解説
#### 解答
* **特解**： $y_p = -\cos x \log|\sec x + \tan x|$
* **一般解**： $y = C_1 \cos x + C_2 \sin x - \cos x \log|\sec x + \tan x| \quad (C_1, C_2\text{は任意定数})$

#### 詳細な計算ステップ
1. **同次方程式の基本解の決定**
   同次方程式 $y'' + y = 0$ の特性方程式は $\lambda^2 + 1 = 0 \implies \lambda = \pm i$ です。
   したがって、基本解は次の2つです：
   $$y_1(x) = \cos x, \quad y_2(x) = \sin x$$

2. **ロンスキー行列式（Wronskian）の計算**
   基本解のロンスキー行列式 $W(x)$ を求めます：
   $$W(x) = \begin{vmatrix} y_1 & y_2 \\ y_1' & y_2' \end{vmatrix} = \begin{vmatrix} \cos x & \sin x \\ -\sin x & \cos x \end{vmatrix} = \cos^2 x - (-\sin^2 x) = \cos^2 x + \sin^2 x = 1$$

3. **定数変化法の定式化**
   特解を $y_p(x) = u_1(x)y_1(x) + u_2(x)y_2(x)$ と仮定します。
   非同次項を $f(x) = \tan x$ とすると、定数変化法の公式より $u_1(x), u_2(x)$ は次のようになります：
   $$u_1(x) = \int \frac{-y_2(x)f(x)}{W(x)} \,dx = \int -\sin x \tan x \,dx$$
   $$u_2(x) = \int \frac{y_1(x)f(x)}{W(x)} \,dx = \int \cos x \tan x \,dx$$

4. **$u_1(x)$ の積分計算**
   $$u_1(x) = \int -\frac{\sin^2 x}{\cos x} \,dx = \int \frac{\cos^2 x - 1}{\cos x} \,dx = \int \left( \cos x - \frac{1}{\cos x} \right) \,dx$$
   ここで、 $\int \cos x \,dx = \sin x$ です。
   次に、 $\int \frac{1}{\cos x} \,dx$ を計算するために分子分母に $\cos x$ を掛けます：
   $$\int \frac{1}{\cos x} \,dx = \int \frac{\cos x}{1 - \sin^2 x} \,dx$$
   $\sin x = t \implies \cos x \,dx = dt$ と置換します：
   $$\int \frac{1}{1-t^2} \,dt = \frac{1}{2} \int \left( \frac{1}{1+t} + \frac{1}{1-t} \right) \,dt = \frac{1}{2} \log\left| \frac{1+t}{1-t} \right| = \frac{1}{2} \log\left| \frac{1+\sin x}{1-\sin x} \right|$$
   この対数部分は次のように変形できます：
   $$\frac{1}{2} \log\left| \frac{(1+\sin x)^2}{1-\sin^2 x} \right| = \frac{1}{2} \log\left| \frac{(1+\sin x)^2}{\cos^2 x} \right| = \log\left| \frac{1+\sin x}{\cos x} \right| = \log|\sec x + \tan x|$$
   したがって、 $u_1(x)$ は次のようになります：
   $$u_1(x) = \sin x - \log|\sec x + \tan x|$$

5. **$u_2(x)$ の積分計算**
   $$\int \cos x \tan x \,dx = \int \cos x \cdot \frac{\sin x}{\cos x} \,dx = \int \sin x \,dx = -\cos x$$

6. **特解 $y_p$ の組み立て**
   求めた $u_1(x), u_2(x)$ を $y_p(x)$ の式に代入します：
   $$y_p = (\sin x - \log|\sec x + \tan x|)\cos x + (-\cos x)\sin x$$
   $$y_p = \sin x \cos x - \cos x \log|\sec x + \tan x| - \sin x \cos x = - \cos x \log|\sec x + \tan x|$$

7. **一般解**
   同次方程式の一般解に特解を加えます：
   $$y = C_1 \cos x + C_2 \sin x - \cos x \log|\sec x + \tan x|$$

---

## 【問題 6】微分方程式（クレローの微分方程式） （第6回 模擬試験・問題3）

### 問題
次の微分方程式の一般解および特異解（包絡線）を求めよ。
$$y = x \frac{dy}{dx} + \left(\frac{dy}{dx}\right)^2$$

### 解答・解説
#### 解答
* **一般解**： $y = C x + C^2 \quad (C\text{は任意定数})$
* **特異解**： $y = -\frac{x^2}{4}$

#### 詳細な計算ステップ
1. **微分方程式の分類**
   本方程式 $y = x \frac{dy}{dx} + \left(\frac{dy}{dx}\right)^2$ は、一般に $y = x y' + f(y')$ の形をしたクレローの微分方程式です。ここでは $f(p) = p^2$ （ただし $p = y' = \frac{dy}{dx}$）となります。

2. **両辺の微分と整理**
   $p = \frac{dy}{dx}$ とおいて方程式を書き直します：
   $$y = xp + p^2 \quad \cdots \text{(1)}$$
   両辺を $x$ で微分します：
   $$\frac{dy}{dx} = \frac{d}{dx}(xp + p^2) \implies p = p + x\frac{dp}{dx} + 2p\frac{dp}{dx}$$
   両辺から $p$ を引き、共通因数をまとめます：
   $$(x + 2p)\frac{dp}{dx} = 0$$

3. **一般解の決定**
   $\frac{dp}{dx} = 0$ のとき、これを積分して $p = C$ （定数）となります。
   これを元の式 (1) に代入すると一般解が得られます：
   $$y = Cx + C^2$$

4. **特異解の決定**
   $x + 2p = 0$ のとき、これを $p$ について解きます：
   $$p = -\frac{x}{2}$$
   これを元の式 (1) に代入して特異解（一般解の包絡線）を得ます：
   $$y = x \left( -\frac{x}{2} \right) + \left( -\frac{x}{2} \right)^2 = -\frac{x^2}{2} + \frac{x^2}{4} = -\frac{x^2}{4}$$

---

## 【問題 7】微分方程式（オイラー・コーシーの微分方程式） （第7回 模擬試験・問題3）

### 問題
次の可変係数微分方程式の一般解を求めよ。
$$x^2 y'' - 2x y' + 2y = 0 \quad (x > 0)$$

### 解答・解説
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

## 【問題 8】微分方程式（完全微分方程式） （第8回 模擬試験・問題3）

### 問題
次の微分方程式の一般解を求めよ。
$$(3x^2 + 2y^2) \,dx + (4xy + 6y^2) \,dy = 0$$

### 解答・解説
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

## 【問題 9】微分方程式（連立線形微分方程式） （第9回 模擬試験・問題3）

### 問題
次の連立微分方程式の初期値問題を解け。
$$\begin{cases} 
\frac{dx}{dt} = 3x - 2y \\ 
\frac{dy}{dt} = 2x - 2y 
\end{cases} \quad \left( x(0) = 3, \; y(0) = 2 \right)$$

### 解答・解説
#### 解答
$$x(t) = \frac{8}{3}e^{2t} + \frac{1}{3}e^{-t}, \quad y(t) = \frac{4}{3}e^{2t} + \frac{2}{3}e^{-t}$$

#### 詳細な計算ステップ
1. **行列形式での定式化と固有値の算出**
   連立微分方程式を $\frac{d\mathbf{x}}{dt} = M \mathbf{x}$ の形で表します：
   $$\frac{d}{dt}\begin{pmatrix} x \\ y \end{pmatrix} = \begin{pmatrix} 3 & -2 \\ 2 & -2 \end{pmatrix} \begin{pmatrix} x \\ y \end{pmatrix}$$
   係数行列 $M = \begin{pmatrix} 3 & -2 \\ 2 & -2 \end{pmatrix}$ の固有値 $\lambda$ を求めます：
   $$\det(M - \lambda I) = \begin{vmatrix} 3-\lambda & -2 \\ 2 & -2-\lambda \end{vmatrix} = (3-\lambda)(-2-\lambda) - (-4) = \lambda^2 - \lambda - 2 = 0$$
   因数分解して固有値を求めます：
   $$(\lambda - 2)(\lambda + 1) = 0 \implies \lambda = 2, \; -1$$

2. **固有ベクトルの算出**
   * **$\lambda_1 = 2$ に対する固有ベクトル $\mathbf{v}_1$**：
     $$(M - 2I)\mathbf{v}_1 = \mathbf{0} \implies \begin{pmatrix} 1 & -2 \\ 2 & -4 \end{pmatrix} \begin{pmatrix} v_{11} \\ v_{12} \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \implies v_{11} - 2v_{12} = 0$$
     固有ベクトルとして以下を選びます：
     $$\mathbf{v}_1 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$$
   * **$\lambda_2 = -1$ に対する固有ベクトル $\mathbf{v}_2$**：
     $$(M + I)\mathbf{v}_2 = \mathbf{0} \implies \begin{pmatrix} 4 & -2 \\ 2 & -1 \end{pmatrix} \begin{pmatrix} v_{21} \\ v_{22} \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \implies 2v_{21} - v_{22} = 0$$
     固有ベクトルとして以下を選びます：
     $$\mathbf{v}_2 = \begin{pmatrix} 1 \\ 2 \end{pmatrix}$$

3. **一般解の構成**
   一般解は固有値と固有ベクトルを用いて次のように表されます：
   $$\begin{pmatrix} x(t) \\ y(t) \end{pmatrix} = C_1 e^{2t} \begin{pmatrix} 2 \\ 1 \end{pmatrix} + C_2 e^{-t} \begin{pmatrix} 1 \\ 2 \end{pmatrix}$$
   成分ごとに書くと：
   $$x(t) = 2C_1 e^{2t} + C_2 e^{-t} \quad \cdots \text{(1)}$$
   $$y(t) = C_1 e^{2t} + 2C_2 e^{-t} \quad \cdots \text{(2)}$$

4. **初期条件による定数の決定**
   $t = 0$ における初期値 $x(0) = 3$, $y(0) = 2$ を代入します：
   * 式 (1) より： $2C_1 + C_2 = 3 \quad \cdots \text{(3)}$
   * 式 (2) より： $C_1 + 2C_2 = 2 \quad \cdots \text{(4)}$
   
   この連立一次方程式を解きます。
   式 (4) より $C_1 = 2 - 2C_2$ とし、これを式 (3) に代入します：
   $$2(2 - 2C_2) + C_2 = 3 \implies 4 - 3C_2 = 3 \implies 3C_2 = 1 \implies C_2 = \frac{1}{3}$$
   これより：
   $$C_1 = 2 - 2\left(\frac{1}{3}\right) = \frac{4}{3}$$

5. **特解の決定**
   定数の値を代入して一般解を決定します：
   $$x(t) = 2\left(\frac{4}{3}\right)e^{2t} + \frac{1}{3}e^{-t} = \frac{8}{3}e^{2t} + \frac{1}{3}e^{-t}$$
   $$y(t) = \frac{4}{3}e^{2t} + 2\left(\frac{1}{3}\right)e^{-t} = \frac{4}{3}e^{2t} + \frac{2}{3}e^{-t}$$

---

## 【問題 10】微分方程式（非同次オイラー・コーシー方程式） （第10回 模擬試験・問題3）

### 問題
次の微分方程式の一般解を求めよ。
$$x^2 y'' - x y' + y = x \log x \quad (x > 0)$$

### 解答・解説
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

## 【問題 11】微分方程式 （模擬問題集・問題3）

### 問題
次の微分方程式の初期値問題を解け。
$$x \frac{dy}{dx} - y = x^2 \cos x \quad (x > 0), \quad y(\pi) = 0$$

### 解答・解説
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

## 【問題 12】微分方程式（2階線形） （総合問題セット・問題6）

### 問題
次の微分方程式の一般解を求めよ。
$$y'' - 4y' + 4y = e^{2x} + \sin x$$

### 解答・解説
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

## 【問題 13】微分方程式（ラプラス変換） （新規追加問題）

### 問題
ラプラス変換を用いて、次の常微分方程式の初期値問題を解け。
$$y'' + 4y = \sin t, \quad y(0) = 0, \quad y'(0) = 1$$

### 解答・解説
#### 解答
$$y(t) = \frac{1}{3}\sin t + \frac{1}{3}\sin 2t$$

#### 解説
1. **初期値問題の両辺のラプラス変換**
   求める解 $y(t)$ のラプラス変換を $Y(s) = \mathcal{L}\{y(t)\}$ とします。
   微分に関するラプラス変換の公式：
   $$\mathcal{L}\{y''\} = s^2 Y(s) - s y(0) - y'(0)$$
   および $\mathcal{L}\{\sin t\} = \frac{1}{s^2+1}$ を用いて、微分方程式の両辺をラプラス変換します。
   $$s^2 Y(s) - s y(0) - y'(0) + 4 Y(s) = \frac{1}{s^2+1}$$
   初期条件 $y(0) = 0, y'(0) = 1$ を代入して整理します。
   $$s^2 Y(s) - 1 + 4 Y(s) = \frac{1}{s^2+1}$$
   $$(s^2 + 4) Y(s) = 1 + \frac{1}{s^2+1} = \frac{s^2 + 2}{s^2 + 1}$$
   これより、 $Y(s)$ は次のようになります。
   $$Y(s) = \frac{s^2 + 2}{(s^2 + 1)(s^2 + 4)}$$

2. **部分分数分解**
   $Y(s)$ をラプラス逆変換しやすいように、次のように部分分数分解します。
   $$\frac{s^2 + 2}{(s^2 + 1)(s^2 + 4)} = \frac{A}{s^2 + 1} + \frac{B}{s^2 + 4}$$
   両辺に通分した分母 $(s^2+1)(s^2+4)$ を掛けて分子を比較します。
   $$s^2 + 2 = A(s^2 + 4) + B(s^2 + 1) = (A + B)s^2 + (4A + B)$$
   $s^2$ の係数と定数項を比較します。
   $$\begin{cases} A + B = 1 \\ 4A + B = 2 \end{cases}$$
   第2式から第1式を引くと：
   $$3A = 1 \implies A = \frac{1}{3}$$
   これを第1式に代入して：
   $$B = 1 - \frac{1}{3} = \frac{2}{3}$$
   したがって、 $Y(s)$ は次のように分解されます。
   $$Y(s) = \frac{1}{3} \cdot \frac{1}{s^2+1} + \frac{2}{3} \cdot \frac{1}{s^2+4} = \frac{1}{3} \cdot \frac{1}{s^2+1} + \frac{1}{3} \cdot \frac{2}{s^2+2^2}$$

3. **ラプラス逆変換**
   各項に対してラプラス逆変換公式 $\mathcal{L}^{-1}\left\{\frac{1}{s^2+1}\right\} = \sin t$、および $\mathcal{L}^{-1}\left\{\frac{a}{s^2+a^2}\right\} = \sin at$ （ここでは $a=2$）を適用します。
   $$y(t) = \mathcal{L}^{-1}\{Y(s)\} = \frac{1}{3}\sin t + \frac{1}{3}\sin 2t$$

---

## 【問題 14】微分方程式（オイラー・コーシーの微分方程式） （新規追加問題）

### 問題
次の常微分方程式の一般解を求めよ。
$$x^2 y'' - 2xy' + 2y = x^3 \quad (x > 0)$$

### 解答・解説
#### 解答
$$y(x) = C_1 x + C_2 x^2 + \frac{1}{2}x^3 \quad (C_1, C_2 \text{ は任意定数})$$

#### 解説
1. **同次方程式の解法（オイラー・コーシー形）**
   まず、対応する同次方程式 $x^2 y'' - 2xy' + 2y = 0$ を解きます。
   この形の微分方程式はオイラー・コーシー（Euler-Cauchy）の微分方程式と呼ばれ、 $y = x^r$ と仮定して解くことができます。
   $y' = r x^{r-1}$、 $y'' = r(r-1) x^{r-2}$ を同次式に代入します：
   $$x^2 \cdot r(r-1)x^{r-2} - 2x \cdot r x^{r-1} + 2 x^r = 0$$
   $$x^r [ r(r-1) - 2r + 2 ] = 0 \implies r^2 - 3r + 2 = 0$$
   特性方程式を解くと：
   $$(r-1)(r-2) = 0 \implies r = 1, 2$$
   したがって、同次基本解は $y_1 = x, y_2 = x^2$ となり、同次方程式の一般解 $y_h$ は以下のようになります：
   $$y_h = C_1 x + C_2 x^2$$

2. **非同次方程式の特解 $y_p$ の決定**
   右辺の非同次項 $f(x) = x^3$ は、基本解 $x, x^2$ とは独立であるため、特解 $y_p$ を以下のように仮定できます（未定係数法）：
   $$y_p = A x^3$$
   この導関数を求めます：
   $$y_p' = 3A x^2, \quad y_p'' = 6A x$$
   これらを元の微分方程式に代入して定数 $A$ を決定します：
   $$x^2(6A x) - 2x(3A x^2) + 2(A x^3) = x^3$$
   $$6A x^3 - 6A x^3 + 2A x^3 = x^3 \implies 2A x^3 = x^3$$
   両辺の係数を比較して、 $2A = 1 \implies A = \frac{1}{2}$ が得られます。
   したがって、特解は $y_p = \frac{1}{2}x^3$ です。

3. **一般解の合成**
   微分方程式の一般解 $y(x)$ は、同次解 $y_h$ と特解 $y_p$ の和になります：
   $$y(x) = y_h + y_p = C_1 x + C_2 x^2 + \frac{1}{2}x^3$$

---

## 【問題 15】微分方程式（積分因子を用いた完全微分方程式の解法） （新規追加問題）

### 問題
次の微分方程式の積分因子 $\mu(x)$ を求め、一般解を求めよ。
$$(3x^2 y + 2xy + y^3)dx + (x^2 + y^2)dy = 0$$

### 解答・解説
#### 解答
積分因子： $\mu(x) = e^{3x}$
一般解： $$e^{3x} \left( x^2 y + \frac{1}{3}y^3 \right) = C \quad （C \text{ は任意定数}）$$

#### 解説
1. **完全性の判定**
   $M(x, y) = 3x^2 y + 2xy + y^3$, $N(x, y) = x^2 + y^2$ とおきます。
   偏導関数を計算して完全性（全微分形式）を確認します：
   $$M_y = \frac{\partial M}{\partial y} = 3x^2 + 2x + 3y^2$$
   $$N_x = \frac{\partial N}{\partial x} = 2x$$
   $M_y \neq N_x$ であるため、この方程式は完全微分方程式ではありません。

2. **積分因子 $\mu(x)$ の決定**
   積分因子 $\mu$ が $x$ のみの関数である（$\mu = \mu(x)$）と仮定します。このとき、次の関係式を満たす必要があります：
   $$\frac{1}{\mu} \frac{d\mu}{dx} = \frac{M_y - N_x}{N}$$
   右辺に計算結果を代入します：
   $$\frac{M_y - N_x}{N} = \frac{(3x^2 + 2x + 3y^2) - 2x}{x^2 + y^2} = \frac{3x^2 + 3y^2}{x^2 + y^2} = \frac{3(x^2 + y^2)}{x^2 + y^2} = 3$$
   これより、次の変数分離形の微分方程式が得られます：
   $$\frac{d\mu}{dx} = 3\mu \implies \log |\mu| = 3x + C_0 \implies \mu(x) = e^{3x}$$

3. **完全微分方程式としての解法**
   元の微分方程式に積分因子 $\mu(x) = e^{3x}$ を掛けます：
   $$e^{3x}(3x^2 y + 2xy + y^3)dx + e^{3x}(x^2 + y^2)dy = 0$$
   これは完全微分方程式です。求めるポテンシャル関数 $U(x, y)$ は以下を満たします：
   $$\frac{\partial U}{\partial y} = e^{3x}(x^2 + y^2)$$
   この式を $y$ で積分します：
   $$U(x, y) = \int e^{3x}(x^2 + y^2) \,dy = e^{3x} \left( x^2 y + \frac{1}{3}y^3 \right) + g(x) \quad \cdots \text{(i)}$$
   ここで $g(x)$ は $x$ のみの関数です。式 (i) を $x$ で偏微分します：
   $$rac{partial U}{partial x} = 3e^{3x} left( x^2 y + rac{1}{3}y^3 ight) + e^{3x}(2xy) + g'(x) = e^{3x}(3x^2 y + y^3 + 2xy) + g'(x)$$
   これが $e^{3x}(3x^2 y + 2xy + y^3)$ と等しくなければならないため：
   $$g'(x) = 0 implies g(x) = C_0 quad 	ext{（定数）}$$
   したがって、微分方程式の一般解は次のようになります：
   $$e^{3x} left( x^2 y + rac{1}{3}y^3 ight) = C$$

---

## 【問題 16】微分方程式（3階定数係数線形微分方程式の一般解） （新規追加問題）

### 問題
次の3階常微分方程式の一般解を求めよ。
$$y''' - 3y'' + 3y' - y = e^x$$

### 解答・解説
#### 解答
$$y(x) = (C_1 + C_2 x + C_3 x^2)e^x + rac{1}{6}x^3 e^x quad (C_1, C_2, C_3 	ext{ は任意定数})$$

#### 解説
1. **同次方程式の基本解の決定**
   対応する同次微分方程式 $y''' - 3y'' + 3y' - y = 0$ の特性方程式を解きます：
   $$lambda^3 - 3lambda^2 + 3lambda - 1 = 0 \implies (lambda - 1)^3 = 0$$
   特性方程式は3重根 $lambda = 1$ を持ちます。したがって、同次基本解は以下のようになります：
   $$y_1(x) = e^x, quad y_2(x) = xe^x, quad y_3(x) = x^2 e^x$$
   よって、同次一般解 $y_h(x)$ は次の通りです：
   $$y_h(x) = (C_1 + C_2 x + C_3 x^2)e^x$$

2. **非同次方程式の特解の決定**
   右辺の非同次項 $f(x) = e^x$ は、同次基本解の3重根に対応する関数そのものであるため、特解 $y_p(x)$ の形を以下のように仮定します（未定係数法）：
   $$y_p(x) = A x^3 e^x$$
   この導関数を求め、微分方程式に代入して定数 $A$ を決定します。微分演算子 $D = rac{d}{dx}$ を用いた指数シフト公式を用いて計算します：
   $$(D-1)^3 (A x^3 e^x) = e^x D^3 (A x^3) = e^x (6A)$$
   これが与えられた右辺 $e^x$ に等しいため：
   $$6A e^x = e^x implies 6A = 1 implies A = rac{1}{6}$$
   したがって、特解は $y_p(x) = rac{1}{6}x^3 e^x$ と決定されます。

3. **一般解の合成**
   微分方程式の一般解は、同次解と特解の和で表されます：
   $$y(x) = y_h(x) + y_p(x) = (C_1 + C_2 x + C_3 x^2)e^x + rac{1}{6}x^3 e^x$$

---


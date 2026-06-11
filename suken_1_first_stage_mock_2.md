# 数学検定1級 一次試験（計算技能）模擬試験［第2回］

数学検定1級一次試験（計算技能）対策のための、第2回模擬試験問題（全7問）と詳細な解答解説です。第1回の模擬試験とは異なる数学的領域やアプローチをカバーするように設計されています。

---

## 模擬試験問題（制限時間：60分）

### 【問題1】極限・無限級数
次の無限級数の和を求めよ。
$$S = \sum_{n=1}^{\infty} \frac{n^2}{2^n}$$

### 【問題2】線形代数（行列の累乗）
次の行列 $A$ に対し、 $A^n$ （$n$ は正の整数）を求めよ。
$$A = \begin{pmatrix} 4 & -2 \\ 1 & 1 \end{pmatrix}$$

### 【問題3】微分積分学（多変数関数の極値）
次の2変数関数 $f(x, y)$ の極値を判定し、極大値または極小値とそのときの $(x, y)$ を求めよ。
$$f(x, y) = x^3 + y^3 - 3xy$$

### 【問題4】微分方程式（1階線形）
次の微分方程式の初期値問題を解け。
$$\frac{dy}{dx} + y \tan x = \sin 2x, \quad y(0) = 1 \quad \left( -\frac{\pi}{2} < x < \frac{\pi}{2} \right)$$

### 【問題5】複素解析（有理関数の実無限積分）
留数定理を用いて、次の広義積分の値を求めよ。
$$I = \int_0^{\infty} \frac{1}{x^4+1} \,dx$$

### 【問題6】代数学・整数論（フェルマーの小定理）
$2^{1000}$ を $13$ で割ったときの余りを求めよ。

### 【問題7】確率・統計（ポアソン分布）
ある窓口で1分間に受ける電話の件数 $X$ が、平均（期待値） $\lambda = 3$ のポアソン分布に従っている。
1. 任意の1分間に受ける電話の件数がちょうど 2件である確率 $P(X=2)$ を求めよ。
2. 5分間に受ける電話の件数 $Y$ の分散 $V[Y]$ を求めよ。

---
---

## 解答・解説

### 【問題1】の解答・解説
#### 解答
$$S = 6$$

#### 詳細な計算ステップ
1. **等比級数とその落とし込み**
   収束半径が $|x| < 1$ である無限等比級数の基本公式から始めます。
   $$f(x) = \sum_{n=0}^{\infty} x^n = \frac{1}{1-x}$$

2. **1回目の微分と $n x^n$ の構成**
   両辺を $x$ について微分します。左辺は項別微分を行い、右辺は $\frac{d}{dx}(1-x)^{-1} = -(1-x)^{-2}(-1) = (1-x)^{-2}$ を用います。
   $$f'(x) = \sum_{n=1}^{\infty} n x^{n-1} = \frac{1}{(1-x)^2}$$
   両辺に $x$ を掛けて、指数を $n$ に合わせます。
   $$\sum_{n=1}^{\infty} n x^n = \frac{x}{(1-x)^2} \quad \cdots \text{(i)}$$

3. **2回目の微分と $n^2 x^n$ の構成**
   式(i) の両辺を再度 $x$ について微分します。右辺は商の微分公式 $\left(\frac{u}{v}\right)' = \frac{u'v - uv'}{v^2}$ を適用します。ここで $u = x, v = (1-x)^2$ です。
   * $u' = 1$
   * $v' = 2(1-x)(-1) = -2(1-x)$
   したがって：
   $$\frac{d}{dx} \left( \frac{x}{(1-x)^2} \right) = \frac{1 \cdot (1-x)^2 - x \cdot (-2(1-x))}{(1-x)^4}$$
   分子の共通因数 $(1-x)$ で約分します。
   $$= \frac{(1-x) \left[ (1-x) + 2x \right]}{(1-x)^4} = \frac{1+x}{(1-x)^3}$$
   左辺の項別微分結果と合わせると：
   $$\sum_{n=1}^{\infty} n^2 x^{n-1} = \frac{1+x}{(1-x)^3}$$
   両辺に $x$ を掛けます。
   $$\sum_{n=1}^{\infty} n^2 x^n = \frac{x(1+x)}{(1-x)^3} \quad \cdots \text{(ii)}$$

4. **$x = 1/2$ の代入**
   式(ii) は収束域 $|x| < 1$ で成立します。 $x = \frac{1}{2}$ を代入すると、求める級数 $S$ になります。
   $$S = \sum_{n=1}^{\infty} \frac{n^2}{2^n} = \frac{\frac{1}{2}\left(1 + \frac{1}{2}\right)}{\left(1 - \frac{1}{2}\right)^3} = \frac{\frac{1}{2} \cdot \frac{3}{2}}{\left(\frac{1}{2}\right)^3} = \frac{\frac{3}{4}}{\frac{1}{8}} = \frac{3}{4} \times 8 = 6$$

---

### 【問題2】の解答・解説
#### 解答
$$A^n = \begin{pmatrix} -2^n + 2 \cdot 3^n & 2 \cdot 2^n - 2 \cdot 3^n \\ -2^n + 3^n & 2 \cdot 2^n - 3^n \end{pmatrix}$$

#### 詳細な計算ステップ
1. **固有値の計算**
   行列 $A = \begin{pmatrix} 4 & -2 \\ 1 & 1 \end{pmatrix}$ の特性方程式を解きます。
   $$\det(A - \lambda I) = \begin{vmatrix} 4-\lambda & -2 \\ 1 & 1-\lambda \end{vmatrix} = 0$$
   $$(4-\lambda)(1-\lambda) - (-2)(1) = \lambda^2 - 5\lambda + 4 + 2 = \lambda^2 - 5\lambda + 6 = 0$$
   因数分解して：
   $$(\lambda-2)(\lambda-3) = 0 \implies \lambda = 2, \; 3$$

2. **固有ベクトルの計算**
   * **$\lambda = 2$ に対する固有ベクトル $\mathbf{p}_1$**
     $$(A - 2I)\mathbf{x} = \mathbf{0} \implies \begin{pmatrix} 2 & -2 \\ 1 & -1 \end{pmatrix} \begin{pmatrix} x_1 \\ x_2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \implies x_1 - x_2 = 0$$
     固有ベクトルの1つとして $\mathbf{p}_1 = \begin{pmatrix} 1 \\ 1 \end{pmatrix}$ を選びます。
   * **$\lambda = 3$ に対する固有ベクトル $\mathbf{p}_2$**
     $$(A - 3I)\mathbf{x} = \mathbf{0} \implies \begin{pmatrix} 1 & -2 \\ 1 & -2 \end{pmatrix} \begin{pmatrix} x_1 \\ x_2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix} \implies x_1 - 2x_2 = 0$$
     固有ベクトルの1つとして $\mathbf{p}_2 = \begin{pmatrix} 2 \\ 1 \end{pmatrix}$ を選びます。

3. **正則行列 $P$ とその逆行列の構成**
   固有ベクトルを並べて行列 $P$ を作ります。
   $$P = (\mathbf{p}_1, \mathbf{p}_2) = \begin{pmatrix} 1 & 2 \\ 1 & 1 \end{pmatrix}$$
   逆行列 $P^{-1}$ を公式 $\begin{pmatrix} a & b \\ c & d \end{pmatrix}^{-1} = \frac{1}{ad-bc}\begin{pmatrix} d & -b \\ -c & a \end{pmatrix}$ により求めます。行列式は $1\cdot 1 - 2\cdot 1 = -1$ です。
   $$P^{-1} = \frac{1}{-1} \begin{pmatrix} 1 & -2 \\ -1 & 1 \end{pmatrix} = \begin{pmatrix} -1 & 2 \\ 1 & -1 \end{pmatrix}$$

4. **行列の累乗の計算**
   $A = P D P^{-1}$ より $A^n = P D^n P^{-1}$ です。ここで $D = \begin{pmatrix} 2 & 0 \\ 0 & 3 \end{pmatrix}$ です。
   $$A^n = \begin{pmatrix} 1 & 2 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} 2^n & 0 \\ 0 & 3^n \end{pmatrix} \begin{pmatrix} -1 & 2 \\ 1 & -1 \end{pmatrix}$$
   右側2枚の積を計算します。
   $$\begin{pmatrix} 2^n & 0 \\ 0 & 3^n \end{pmatrix} \begin{pmatrix} -1 & 2 \\ 1 & -1 \end{pmatrix} = \begin{pmatrix} -2^n & 2 \cdot 2^n \\ 3^n & -3^n \end{pmatrix}$$
   左から $P$ を掛けます。
   $$A^n = \begin{pmatrix} 1 & 2 \\ 1 & 1 \end{pmatrix} \begin{pmatrix} -2^n & 2 \cdot 2^n \\ 3^n & -3^n \end{pmatrix} = \begin{pmatrix} 1(-2^n) + 2(3^n) & 1(2 \cdot 2^n) + 2(-3^n) \\ 1(-2^n) + 1(3^n) & 1(2 \cdot 2^n) + 1(-3^n) \end{pmatrix}$$
   $$A^n = \begin{pmatrix} -2^n + 2 \cdot 3^n & 2 \cdot 2^n - 2 \cdot 3^n \\ -2^n + 3^n & 2 \cdot 2^n - 3^n \end{pmatrix}$$

---

### 【問題3】の解答・解説
#### 解答
$(x, y) = (1, 1)$ のとき、極小値 $-1$ をとる。（$(0, 0)$ は極値をとらない鞍点）

#### 詳細な計算ステップ
1. **1階偏導関数の計算と停留点**
   停留点（極値の候補）を求めるため、偏導関数を $0$ とおきます。
   * $f_x = \frac{\partial}{\partial x}(x^3 + y^3 - 3xy) = 3x^2 - 3y = 0 \implies y = x^2 \quad \cdots \text{(A)}$
   * $f_y = \frac{\partial}{\partial y}(x^3 + y^3 - 3xy) = 3y^2 - 3x = 0 \implies x = y^2 \quad \cdots \text{(B)}$
   式(A)を式(B)に代入します。
   $$x = (x^2)^2 = x^4 \implies x^4 - x = 0 \implies x(x^3 - 1) = 0 \implies x(x-1)(x^2+x+1) = 0$$
   実数解は $x = 0$ または $x = 1$ です。
   * $x = 0$ のとき： 式(A)より $y = 0^2 = 0 \implies$ 停留点 $(0, 0)$
   * $x = 1$ のとき： 式(A)より $y = 1^2 = 1 \implies$ 停留点 $(1, 1)$

2. **2階偏導関数の計算と極値判定式**
   極値判定のために2階偏導関数を計算します。
   * $f_{xx} = \frac{\partial}{\partial x}(3x^2 - 3y) = 6x$
   * $f_{yy} = \frac{\partial}{\partial y}(3y^2 - 3x) = 6y$
   * $f_{xy} = \frac{\partial}{\partial y}(3x^2 - 3y) = -3$
   極値判定用のヘシアン（判別式） $D(x, y)$ を設定します。
   $$D(x, y) = f_{xx}f_{yy} - (f_{xy})^2 = (6x)(6y) - (-3)^2 = 36xy - 9$$

3. **各停留点における判定**
   * **点 $(0, 0)$ の場合**
     $$D(0, 0) = 36(0)(0) - 9 = -9 < 0$$
     $D < 0$ であるため、この点は**極値をとらない鞍点（サドルポイント）**です。
   * **点 $(1, 1)$ の場合**
     $$D(1, 1) = 36(1)(1) - 9 = 27 > 0$$
     $D > 0$ なのでこの点では極値を持ちます。さらに：
     $$f_{xx}(1, 1) = 6(1) = 6 > 0$$
     2階微分係数が正なので、この点で**極小値**をとります。
     極小値の値は：
     $$f(1, 1) = 1^3 + 1^3 - 3(1)(1) = 2 - 3 = -1$$

---

### 【問題4】の解答・解説
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

### 【問題5】の解答・解説
#### 解答
$$I = \frac{\sqrt{2}}{4}\pi$$

#### 詳細な計算ステップ
1. **積分範囲の拡張と複素関数の設定**
   被積分関数 $\frac{1}{x^4+1}$ は偶関数（$f(-x) = f(x)$）なので、実数全体での積分に変換します。
   $$I = \frac{1}{2} \int_{-\infty}^{\infty} \frac{1}{x^4+1} \,dx$$
   複素関数 $f(z) = \frac{1}{z^4+1}$ を考え、上半平面に半円の積分経路 $C$ （実軸 $[-R, R]$ および大半円 $C_R$）を設定します。

2. **極の決定**
   分母 $z^4+1 = 0 \implies z^4 = -1 = e^{i\pi}$ の根を求めます。オイラーの公式より、極は以下の 4点です。
   $$z_k = e^{i\frac{\pi + 2k\pi}{4}} \quad (k=0, 1, 2, 3)$$
   このうち、上半平面 ($\operatorname{Im}(z) > 0$) に含まれるのは以下の 2点（いずれも1位の極）です。
   * $z_0 = e^{i\pi/4} = \cos\frac{\pi}{4} + i\sin\frac{\pi}{4} = \frac{1+i}{\sqrt{2}}$
   * $z_1 = e^{i3\pi/4} = \cos\frac{3\pi}{4} + i\sin\frac{3\pi}{4} = \frac{-1+i}{\sqrt{2}}$

3. **留数の計算**
   $f(z) = \frac{g(z)}{h(z)}$ 型で $z=a$ が1位の極のとき、留数は $\frac{g(a)}{h'(a)}$ で計算できます。
   本問では $g(z)=1$, $h'(z)=4z^3$ なので、留数は $\frac{1}{4z^3}$ となります。
   分母・分子に $z$ を掛けると、 $z^4 = -1$ より：
   $$\frac{1}{4z^3} = \frac{z}{4z^4} = -\frac{z}{4}$$
   これより留数は簡単に計算できます。
   * $\operatorname{Res}(f, z_0) = -\frac{z_0}{4} = -\frac{1+i}{4\sqrt{2}}$
   * $\operatorname{Res}(f, z_1) = -\frac{z_1}{4} = -\frac{-1+i}{4\sqrt{2}}$
   留数の合計を計算します。
   $$\sum \operatorname{Res} = -\frac{1}{4\sqrt{2}} \left( (1+i) + (-1+i) \right) = -\frac{2i}{4\sqrt{2}} = -\frac{i}{2\sqrt{2}}$$

4. **留数定理の適用と積分値**
   大半円上の積分は $R \to \infty$ で $0$ に収束するため、
   $$\int_{-\infty}^{\infty} \frac{1}{x^4+1} \,dx = 2\pi i \left( -\frac{i}{2\sqrt{2}} \right) = \frac{2\pi}{2\sqrt{2}} = \frac{\pi}{\sqrt{2}} = \frac{\sqrt{2}}{2}\pi$$
   求める積分値 $I$ はその半分なので：
   $$I = \frac{1}{2} \cdot \left(\frac{\sqrt{2}}{2}\pi\right) = \frac{\sqrt{2}}{4}\pi$$

---

### 【問題6】の解答・解説
#### 解答
$$3$$

#### 詳細な計算ステップ
1. **フェルマーの小定理の適用条件**
   求めるものは $2^{1000} \pmod{13}$ です。
   法である $p = 13$ は素数であり、 $2$ と $13$ は互いに素です。フェルマーの小定理 $a^{p-1} \equiv 1 \pmod p$ を適用します。
   $$2^{13-1} \equiv 2^{12} \equiv 1 \pmod{13}$$

2. **指数の次数下げ**
   指数の $1000$ を $12$ で割ります。
   $$1000 = 12 \times 83 + 4$$
   指数法則を用いて $2^{1000}$ を分解します。
   $$2^{1000} = (2^{12})^{83} \times 2^4$$

3. **合同式の計算**
   両辺について法 $13$ で合同式をとります。 $2^{12} \equiv 1$ より：
   $$2^{1000} \equiv (1)^{83} \times 2^4 \equiv 1 \times 16 \equiv 16 \pmod{13}$$
   $16$ を $13$ で割った余りは $3$ なので：
   $$16 \equiv 3 \pmod{13}$$
   したがって、余りは **3** になります。

---

### 【問題7】の解答・解説
#### 解答
1. $P(X=2) = \frac{9}{2} e^{-3} \quad (\approx 0.224)$
2. $V[Y] = 15$

#### 詳細な計算ステップ
1. **第1問：ちょうど2件である確率**
   ポアソン分布の確率質量関数は以下の通りです。
   $$P(X=k) = \frac{e^{-\lambda} \lambda^k}{k!}$$
   問題より平均（期待値） $\lambda = 3$ なので：
   $$P(X=k) = \frac{e^{-3} 3^k}{k!}$$
   ちょうど 2件となる確率を求めるため、 $k=2$ を代入します。
   $$P(X=2) = \frac{e^{-3} 3^2}{2!} = \frac{9}{2}e^{-3}$$
   （※数値としては $e^{-3} \approx 0.0498$ より、 $\frac{9}{2} \times 0.0498 \approx 0.224$ となります。）

2. **第2問：5分間の件数 $Y$ の分散**
   窓口への着信は時間に関して定常かつ独立（ポアソン過程）です。
   1分間の平均が $\lambda = 3$ であるとき、 5分間（5つの独立な 1分間の区間の合計）での着信件数 $Y$ の期待値 $\lambda_Y$ は加法性より以下のようになります。
   $$\lambda_Y = 5 \times 3 = 15$$
   したがって、 $Y$ は平均（期待値）パラメータ $\lambda_Y = 15$ のポアソン分布に従います。
   ポアソン分布の重要な代数的性質として「**期待値と分散は等しい**（$E[Y] = V[Y] = \lambda_Y$）」があります。
   よって、求める分散は：
   $$V[Y] = 15$$

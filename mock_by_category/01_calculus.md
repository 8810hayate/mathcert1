# 数学検定1級 一次試験 模擬問題：微分積分学 (Calculus)

数検1級一次試験対策のための、**微分積分学 (Calculus)**分野の模擬・演習問題（全21問）と詳細な解答解説です。

[分野別問題集トップに戻る](README.md)

---

## 【問題 1】微分積分学（広義積分と特殊関数） （第1回 模擬試験・問題1）

### 問題
次の広義積分の値を求めよ。
$$I = \int_{0}^{\infty} \frac{x}{(1+x^3)^2} \,dx$$

### 解答・解説
#### 解答
$$I = \frac{2\sqrt{3}}{27}\pi$$

#### 詳細な計算ステップ
1. **変数変換の導入**
   積分変数 $x$ を、分母の項 $x^3$ を単純化するために $x^3 = t$ とおきます。
   両辺を $x$ について微分すると：
   $$\frac{dt}{dx} = 3x^2 \implies dx = \frac{1}{3x^2} \,dt$$
   ここで、 $x = t^{1/3}$ より：
   $$dx = \frac{1}{3(t^{1/3})^2} \,dt = \frac{1}{3} t^{-2/3} \,dt$$
   積分範囲について、 $x$ が $0$ から $\infty$ に変化するとき、 $t$ も $0$ から $\infty$ に変化します。

2. **置換積分の実行**
   これらを元の積分式に代入して整理します。
   $$I = \int_0^{\infty} \frac{t^{1/3}}{(1+t)^2} \left( \frac{1}{3} t^{-2/3} \,dt \right) = \frac{1}{3} \int_0^{\infty} \frac{t^{1/3 - 2/3}}{(1+t)^2} \,dt = \frac{1}{3} \int_0^{\infty} \frac{t^{-1/3}}{(1+t)^2} \,dt$$

3. **ベータ関数との対応**
   ベータ関数の広義積分表示公式：
   $$\int_0^{\infty} \frac{t^{p-1}}{(1+t)^{p+q}} \,dt = B(p, q)$$
   と比較します。
   分子の指数について：
   $$p - 1 = -\frac{1}{3} \implies p = \frac{2}{3}$$
   分母の指数について：
   $$p + q = 2 \implies \frac{2}{3} + q = 2 \implies q = \frac{4}{3}$$
   したがって、積分はベータ関数を用いて以下のように表されます。
   $$I = \frac{1}{3} B\left(\frac{2}{3}, \frac{4}{3}\right)$$

4. **ガンマ関数への変換と相反公式の適用**
   ベータ関数とガンマ関数の関係式 $B(p, q) = \frac{\Gamma(p)\Gamma(q)}{\Gamma(p+q)}$ より：
   $$B\left(\frac{2}{3}, \frac{4}{3}\right) = \frac{\Gamma\left(\frac{2}{3}\right)\Gamma\left(\frac{4}{3}\right)}{\Gamma\left(\frac{2}{3} + \frac{4}{3}\right)} = \frac{\Gamma\left(\frac{2}{3}\right)\Gamma\left(\frac{4}{3}\right)}{\Gamma(2)}$$
   ここで、 $\Gamma(2) = 1! = 1$ です。また、ガンマ関数の漸化式 $\Gamma(z+1) = z\Gamma(z)$ より：
   $$\Gamma\left(\frac{4}{3}\right) = \Gamma\left(\frac{1}{3} + 1\right) = \frac{1}{3}\Gamma\left(\frac{1}{3}\right)$$
   これを分子に代入すると：
   $$\Gamma\left(\frac{2}{3}\right)\Gamma\left(\frac{4}{3}\right) = \frac{1}{3}\Gamma\left(\frac{1}{3}\right)\Gamma\left(\frac{2}{3}\right)$$
   さらに、ガンマ関数の相反公式 $\Gamma(z)\Gamma(1-z) = \frac{\pi}{\sin(\pi z)}$ に $z = \frac{1}{3}$ を代入すると、 $\Gamma\left(\frac{2}{3}\right) = \Gamma\left(1 - \frac{1}{3}\right)$ なので：
   $$\Gamma\left(\frac{1}{3}\right)\Gamma\left(\frac{2}{3}\right) = \frac{\pi}{\sin(\pi/3)} = \frac{\pi}{\sqrt{3}/2} = \frac{2\pi}{\sqrt{3}} = \frac{2\sqrt{3}}{3}\pi$$
   これをベータ関数の式に戻します。
   $$B\left(\frac{2}{3}, \frac{4}{3}\right) = \frac{1}{3} \cdot \frac{2\sqrt{3}}{3}\pi = \frac{2\sqrt{3}}{9}\pi$$

5. **最終的な積分値**
   $$I = \frac{1}{3} B\left(\frac{2}{3}, \frac{4}{3}\right) = \frac{1}{3} \cdot \frac{2\sqrt{3}}{9}\pi = \frac{2\sqrt{3}}{27}\pi$$

---

## 【問題 2】極限・無限級数 （第2回 模擬試験・問題1）

### 問題
次の無限級数の和を求めよ。
$$S = \sum_{n=1}^{\infty} \frac{n^2}{2^n}$$

### 解答・解説
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

## 【問題 3】微分積分学（多変数関数の極値） （第2回 模擬試験・問題3）

### 問題
次の2変数関数 $f(x, y)$ の極値を判定し、極大値または極小値とそのときの $(x, y)$ を求めよ。
$$f(x, y) = x^3 + y^3 - 3xy$$

### 解答・解説
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

## 【問題 4】微分積分学（曲線の長さ） （第3回 模擬試験・問題1）

### 問題
次の媒介変数表示で表される平面曲線（サイクロイド）の長さ $L$ を求めよ。
$$x(t) = a(t - \sin t), \quad y(t) = a(1 - \cos t) \quad (0 \le t \le 2\pi, \; a > 0)$$

### 解答・解説
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

## 【問題 5】微分積分学（球面座標の3重積分） （第4回 模擬試験・問題1）

### 問題
次の3重積分の値を求めよ。
$$I = \iiint_V z \,dx\,dy\,dz$$
ただし、積分領域 $V$ は半径 $R$ の上半球体とする。
$$V = \{ (x, y, z) \in \mathbb{R}^3 \mid x^2 + y^2 + z^2 \le R^2, \; z \ge 0 \} \quad (R > 0)$$

### 解答・解説
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

## 【問題 6】微分積分学（リーマン和の極限・区分求積法） （第5回 模擬試験・問題1）

### 問題
次の極限値を求めよ。
$$L = \lim_{n \to \infty} \sum_{k=1}^n \frac{n}{n^2 + k^2}$$

### 解答・解説
#### 解答
$$L = \frac{\pi}{4}$$

#### 詳細な計算ステップ
1. **区分求積法（定積分と和の極限）の公式の導入**
   ある連続関数 $f(x)$ について、区間 $[0, 1]$ における定積分とリーマン和の極限の関係は次の通りです：
   $$\lim_{n \to \infty} \frac{1}{n} \sum_{k=1}^n f\left(\frac{k}{n}\right) = \int_0^1 f(x) \,dx$$

2. **極限式の変形**
   与えられた和の数式において、 $\frac{1}{n}$ と変数 $\frac{k}{n}$ の形を作り出すために、分子と分母を $n^2$ で割ります：
   $$\sum_{k=1}^n \frac{n}{n^2 + k^2} = \sum_{k=1}^n \frac{\frac{n}{n^2}}{\frac{n^2 + k^2}{n^2}} = \sum_{k=1}^n \frac{\frac{1}{n}}{1 + \left(\frac{k}{n}\right)^2} = \frac{1}{n} \sum_{k=1}^n \frac{1}{1 + \left(\frac{k}{n}\right)^2}$$
   したがって、極限 $L$ は次のように書き換えられます：
   $$L = \lim_{n \to \infty} \frac{1}{n} \sum_{k=1}^n \frac{1}{1 + \left(\frac{k}{n}\right)^2}$$

3. **定積分への変換**
   この極限式は $f(x) = \frac{1}{1+x^2}$ としたときの区間 $[0, 1]$ での定積分に等しくなります：
   $$L = \int_0^1 \frac{1}{1+x^2} \,dx$$

4. **置換積分による計算**
   $x = \tan\theta$ とおきます。このとき：
   * 微分関係： $\frac{dx}{d\theta} = \frac{1}{\cos^2\theta} \implies dx = \frac{1}{\cos^2\theta} \,d\theta$
   * 被積分関数の変形： $1 + x^2 = 1 + \tan^2\theta = \frac{1}{\cos^2\theta} \implies \frac{1}{1+x^2} = \cos^2\theta$
   * 積分範囲の変換： $x$ が $0 \to 1$ に変化するとき、 $\tan\theta = 0 \implies \theta = 0$， $\tan\theta = 1 \implies \theta = \frac{\pi}{4}$ となります。
   
   これらを積分式に代入して計算します：
   $$L = \int_0^{\frac{\pi}{4}} \cos^2\theta \cdot \left( \frac{1}{\cos^2\theta} \,d\theta \right) = \int_0^{\frac{\pi}{4}} 1 \,d\theta = \Big[ \theta \Big]_0^{\frac{\pi}{4}} = \frac{\pi}{4}$$
   （※公式として $\int \frac{1}{1+x^2} \,dx = \arctan x$ を適用して $\Big[ \arctan x \Big]_0^1 = \arctan 1 - \arctan 0 = \frac{\pi}{4}$ と求めても同様です。）

---

## 【問題 7】微分積分学（累次積分の積分順序の変更） （第6回 模擬試験・問題1）

### 問題
次の2重積分の積分順序を変更し、その値を計算せよ。
$$I = \int_{0}^{1} \int_{y}^{1} e^{-x^2} \,dx\,dy$$

### 解答・解説
#### 解答
$$I = \frac{e-1}{2e}$$

#### 詳細な計算ステップ
1. **積分順序変更の必要性の検討**
   被積分関数 $e^{-x^2}$ は、 $x$ についての原始関数が初等関数で表せません（誤差関数を用いる必要があります）。したがって、 $x$ で先に積分することは困難です。そこで、積分の順序を変更して $y$ について先に積分することにより、被積分関数 $e^{-x^2}$ を定数とみなして積分を実行します。

2. **積分領域 $D$ の把握と図示**
   与えられた累次積分から、積分領域 $D$ は次のように定義されます：
   $$D = \{ (x, y) \in \mathbb{R}^2 \mid 0 \le y \le 1, \; y \le x \le 1 \}$$
   これを $xy$ 平面上に描くと、 $y = 0$, $x = 1$, $y = x$ で囲まれた、頂点を $(0,0), (1,0), (1,1)$ とする三角形領域であることがわかります。

3. **積分の順序変更（$y$ を先に積分する表現への変換）**
   同一の領域 $D$ を、 $x$ を外側の積分変数、 $y$ を内側の積分変数とするように書き換えます：
   * $x$ の動く全体範囲： $0 \le x \le 1$
   * $x$ を固定したときの $y$ の範囲： 下限は $y = 0$、上限は境界線である $y = x$ となるため、 $0 \le y \le x$ です。
   
   したがって、積分領域 $D$ は次のようになります：
   $$D = \{ (x, y) \in \mathbb{R}^2 \mid 0 \le x \le 1, \; 0 \le y \le x \}$$
   これを用いて累次積分を書き換えます：
   $$I = \int_{0}^{1} \left( \int_{0}^{x} e^{-x^2} \,dy \right) \,dx$$

4. **内側の積分（$y$ についての積分）の実行**
   被積分関数 $e^{-x^2}$ は $y$ については定数扱いとなります：
   $$\int_{0}^{x} e^{-x^2} \,dy = e^{-x^2} \int_{0}^{x} 1 \,dy = e^{-x^2} \Big[ y \Big]_0^x = x e^{-x^2}$$

5. **外側の積分（$x$ についての積分）の実行**
   これをもとの積分の式に戻します：
   $$I = \int_{0}^{1} x e^{-x^2} \,dx$$
   ここで、 $u = x^2$ とおきます：
   * 微分関係： $du = 2x \,dx \implies x \,dx = \frac{1}{2} \,du$
   * 範囲の変換： $x$ が $0 \to 1$ に変化するとき、 $u$ も $0 \to 1$ に変化します。
   
   置換積分を実行します：
   $$I = \int_{0}^{1} e^{-u} \left( \frac{1}{2} \,du \right) = \frac{1}{2} \Big[ -e^{-u} \Big]_0^1 = \frac{1}{2} \left( -e^{-1} - (-e^0) \right) = \frac{1}{2} \left( 1 - \frac{1}{e} \right) = \frac{e-1}{2e}$$

---

## 【問題 8】微分積分学（テイラー展開と不定形の極限） （第8回 模擬試験・問題1）

### 問題
次の極限値を求めよ。
$$L = \lim_{x \to 0} \frac{\cos x - e^{-x^2/2}}{x^4}$$

### 解答・解説
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

## 【問題 9】微分積分学（回転体の体積・バウムクーヘン分割） （第9回 模擬試験・問題1）

### 問題
$xy$ 平面上の曲線 $y = \sin x$ と $x$ 軸で囲まれた領域のうち、 $0 \le x \le \pi$ の部分を $y$ 軸の周りに1回転させてできる回転体の体積 $V$ を求めよ。

### 解答・解説
#### 解答
$$V = 2\pi^2$$

#### 詳細な計算ステップ
1. **バウムクーヘン分割（円筒殻法）の公式の導入**
   $y = f(x) \ge 0$ と $x$ 軸、および $x=a, x=b$ ($0 \le a < b$) で囲まれた領域を $y$ 軸の周りに1回転させてできる回転体の体積 $V$ は、次の公式（バウムクーヘン分割）で計算されます：
   $$V = 2\pi \int_a^b x f(x) \,dx$$
   本問では $f(x) = \sin x$ 、 $a = 0$ 、 $b = \pi$ です：
   $$V = 2\pi \int_0^{\pi} x \sin x \,dx$$

2. **部分積分の実行**
   積分部分 $I = \int_0^{\pi} x \sin x \,dx$ を部分積分法を用いて計算します。 $\sin x = (-\cos x)'$ であることを利用します：
   $$I = \int_0^{\pi} x (-\cos x)' \,dx = \Big[ x (-\cos x) \Big]_0^{\pi} - \int_0^{\pi} 1 \cdot (-\cos x) \,dx$$
   $$I = \Big[ -x \cos x \Big]_0^{\pi} + \int_0^{\pi} \cos x \,dx$$

3. **各項の計算**
   * 第1項：
     $$\Big[ -x \cos x \Big]_0^{\pi} = (-\pi \cos \pi) - (0) = -\pi(-1) = \pi$$
   * 第2項：
     $$\int_0^{\pi} \cos x \,dx = \Big[ \sin x \Big]_0^{\pi} = \sin \pi - \sin 0 = 0 - 0 = 0$$
   したがって：
   $$I = \pi + 0 = \pi$$

4. **最終計算**
   公式に代入して体積 $V$ を求めます：
   $$V = 2\pi I = 2\pi^2$$

---

## 【問題 10】微分積分学（極座標における曲線の長さ） （第10回 模擬試験・問題1）

### 問題
極方程式 $r = a(1 + \cos \theta) \quad (a > 0, \; 0 \le \theta \le 2\pi)$ で表される曲線（カージオイド・心臓形）の全周の長さ $L$ を求めよ。

### 解答・解説
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

## 【問題 11】微積分学（重積分） （模擬問題集・問題1）

### 問題
次の2重積分を計算せよ。
$$J = \iint_{\mathbb{R}^2} e^{-(x^2 + xy + y^2)} \,dx\,dy$$

### 解答・解説
#### 解答
$$J = \frac{2\sqrt{3}}{3}\pi$$

#### 解説
被積分関数の指数部分にある 2次形式 $x^2 + xy + y^2$ を、変数変換によって対角化（直交変換）します。

2次形式を次のように行列で表します。
$$x^2 + xy + y^2 = \begin{pmatrix} x & y \end{pmatrix} A \begin{pmatrix} x \\ y \end{pmatrix}, \quad A = \begin{pmatrix} 1 & 1/2 \\ 1/2 & 1 \end{pmatrix}$$

対称行列 $A$ の固有値を求めます。固有多項式は、
$$\det(A - \lambda I) = (1-\lambda)^2 - \frac{1}{4} = 0$$
$$\lambda^2 - 2\lambda + \frac{3}{4} = 0 \implies \left(\lambda - \frac{3}{2}\right)\left(\lambda - \frac{1}{2}\right) = 0$$
よって、固有値は $\lambda_1 = \frac{3}{2}, \lambda_2 = \frac{1}{2}$ です。

対称行列は直交行列 $P$ を用いて対角化できます。
$$\begin{pmatrix} x \\ y \end{pmatrix} = P \begin{pmatrix} u \\ v \end{pmatrix}$$
直交変換において、ヤコビアン（Jacobian）の絶対値は $1$ になります（$|J| = |\det P| = 1$）。また、積分領域 $\mathbb{R}^2$ は $uv$ 平面でも全平面 $\mathbb{R}^2$ のままです。

したがって、積分 $J$ は以下のように変換されます。
$$J = \iint_{\mathbb{R}^2} e^{-\left(\frac{3}{2}u^2 + \frac{1}{2}v^2\right)} \,du\,dv$$

これは $u$ と $v$ に関して独立な積分の積に分解できます。
$$J = \left( \int_{-\infty}^{\infty} e^{-\frac{3}{2}u^2} \,du \right) \left( \int_{-\infty}^{\infty} e^{-\frac{1}{2}v^2} \,dv \right)$$

ここで、ガウス積分公式 $\int_{-\infty}^{\infty} e^{-a t^2} \,dt = \sqrt{\frac{\pi}{a}}$ を適用します。
* $u$ の積分: $\sqrt{\frac{\pi}{3/2}} = \sqrt{\frac{2\pi}{3}}$
* $v$ の積分: $\sqrt{\frac{\pi}{1/2}} = \sqrt{2\pi}$

よって、求める積分値は以下の通りです。
$$J = \sqrt{\frac{2\pi}{3}} \cdot \sqrt{2\pi} = \frac{2\pi}{\sqrt{3}} = \frac{2\sqrt{3}}{3}\pi$$

---

## 【問題 12】微分積分（ラグランジュの未定乗数法） （総合問題セット・問題3）

### 問題
制約条件 $x^2 + y^2 + z^2 = 1$ および $x + y + z = 0$ のもとで、3変数関数 $f(x, y, z) = xyz$ の最大値と最小値を求めよ。

### 解答・解説
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

## 【問題 13】微分積分（特殊関数） （総合問題セット・問題4）

### 問題
次の定積分を計算せよ。
$$I = \int_0^1 x^3 (1-x^2)^{3/2} \,dx$$

### 解答・解説
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

## 【問題 14】微分積分学（逆三角関数） （新規追加問題）

### 問題
次の値を求めよ。
$$\theta = \arctan \frac{1}{2} + \arctan \frac{1}{3}$$

### 解答・解説
#### 解答
$$\frac{\pi}{4}$$

#### 解説
1. **加法定理の適用**
   $\alpha = \arctan \frac{1}{2}$、 $\beta = \arctan \frac{1}{3}$ とおきます。
   逆三角関数の定義より、 $\tan \alpha = \frac{1}{2}$， $\tan \beta = \frac{1}{3}$ です。
   ここで、正接（tangent）の加法定理を用いて、 $\tan(\alpha + \beta)$ を計算します。
   $$\tan(\alpha + \beta) = \frac{\tan \alpha + \tan \beta}{1 - \tan \alpha \tan \beta} = \frac{\frac{1}{2} + \frac{1}{3}}{1 - \frac{1}{2} \cdot \frac{1}{3}} = \frac{\frac{5}{6}}{1 - \frac{1}{6}} = \frac{\frac{5}{6}}{\frac{5}{6}} = 1$$

2. **角度の範囲の評価**
   $\tan x$ は区間 $\left(-\frac{\pi}{2}, \frac{\pi}{2}\right)$ で単調増加であり、 $\tan 0 = 0$， $\tan \frac{\pi}{4} = 1$ です。
   $0 < \frac{1}{3} < \frac{1}{2} < 1$ より、次の範囲が成り立ちます：
   $$0 < \alpha < \frac{\pi}{4}$$
   $$0 < \beta < \frac{\pi}{4}$$
   したがって、両者の和は次の範囲に入ります：
   $$0 < \alpha + \beta < \frac{\pi}{2}$$

3. **値の決定**
   区間 $\left(0, \frac{\pi}{2}\right)$ において $\tan(\alpha + \beta) = 1$ を満たす唯一の角度は次の通りです：
   $$\alpha + \beta = \frac{\pi}{4}$$
   したがって、
   $$\arctan \frac{1}{2} + \arctan \frac{1}{3} = \frac{\pi}{4}$$

---

## 【問題 15】微分積分学（漸化式と極限） （新規追加問題）

### 問題
次の漸化式で定義される数列 ${a_n}$ の極限値 $\lim_{n \to \infty} a_n$ を求めよ。
$$a_1 = \sqrt{2}, \quad a_{n+1} = \sqrt{2 + a_n} \quad (n \ge 1)$$

### 解答・解説
#### 解答
$$2$$

#### 解説
1. **極限値の候補の決定**
   数列 ${a_n}$ がある値 $\alpha$ に収束すると仮定します。
   漸化式 $a_{n+1} = \sqrt{2 + a_n}$ において $n \to \infty$ の極限をとると、次の関係式が得られます：
   $$\alpha = \sqrt{2 + \alpha}$$
   両辺を2乗して整理します：
   $$\alpha^2 - \alpha - 2 = 0 \implies (\alpha - 2)(\alpha + 1) = 0$$
   数列の初項 $a_1 = \sqrt{2} > 0$ であり、すべての項が正であるため、極限値も非負（$\alpha \ge 0$）でなければなりません。したがって、極限の候補は $\alpha = 2$ に絞られます。

2. **有界性の証明（数学的帰納法）**
   すべての自然数 $n$ に対して $a_n < 2$ であることを示します。
   * $n=1$ のとき： $a_1 = \sqrt{2} < 2$ より成立。
   * $n=k$ のとき： $a_k < 2$ と仮定すると：
     $$a_{k+1} = \sqrt{2 + a_k} < \sqrt{2 + 2} = \sqrt{4} = 2$$
     よって $n=k+1$ でも成立。
   したがって、任意の自然数 $n$ に対して $a_n < 2$ が成り立ちます。

3. **単調増加性の証明**
   差 $a_{n+1} - a_n$ を計算します：
   $$a_{n+1} - a_n = \sqrt{2 + a_n} - a_n = \frac{2 + a_n - a_n^2}{\sqrt{2 + a_n} + a_n} = \frac{(2 - a_n)(1 + a_n)}{\sqrt{2 + a_n} + a_n}$$
   $0 < a_n < 2$ より、分子は $(2 - a_n)(1 + a_n) > 0$ であり、分母も明らかに正です。
   したがって、 $a_{n+1} - a_n > 0$ となり、数列 ${a_n}$ は単調増加数列です。

4. **極限の決定**
   数列 ${a_n}$ は上に有界（恒に 2 未満）であり、かつ単調増加であるため、実数の完備性（有界単調数列の収束定理）より収束します。その極限値はステップ1で求めた唯一の候補である 2 です。
   よって、
   $$\lim_{n \to \infty} a_n = 2$$

---

## 【問題 16】微分積分学（ニュートン法） （新規追加問題）

### 問題
方程式 $x^3 - 2 = 0$ の正の実数根（すなわち $\sqrt[3]{2}$）をニュートン法を用いて求める。
初期値を $x_0 = 1.5$ とするとき、1回目の反復値 $x_1$ を求めよ（分数で表せ）。

### 解答・解説
#### 解答
$$\frac{35}{27}$$

#### 解説
1. **ニュートン法（Newton's method）の公式**
   方程式 $f(x) = 0$ に対するニュートン法の反復式は次の通りです：
   $$x_{n+1} = x_n - \frac{f(x_n)}{f'(x_n)}$$
   本問では $f(x) = x^3 - 2$ であり、その導関数は $f'(x) = 3x^2$ です。反復式に代入して整理します：
   $$x_{n+1} = x_n - \frac{x_n^3 - 2}{3x_n^2} = \frac{3x_n^3 - (x_n^3 - 2)}{3x_n^2} = \frac{2x_n^3 + 2}{3x_n^2}$$

2. **1回目の反復計算**
   初期値 $x_0 = 1.5 = \frac{3}{2}$ を代入して、 $x_1$ の値を求めます：
   $$x_1 = \frac{2 \left( \left(\frac{3}{2}\right)^3 + 1 \right)}{3 \left(\frac{3}{2}\right)^2} = \frac{2 \left( \frac{27}{8} + 1 \right)}{3 \cdot \frac{9}{4}} = \frac{2 \cdot \frac{35}{8}}{\frac{27}{4}} = \frac{\frac{35}{4}}{\frac{27}{4}} = \frac{35}{27}$$
   （※参考： $x_1 = \frac{35}{27} \approx 1.2963$ であり、真の値 $\sqrt[3]{2} \approx 1.2599$ に速やかに近似していることがわかります。）

---

## 【問題 17】微分積分学（多変数関数の極値とヘッセ行列） （新規追加問題）

### 問題
次の2変数関数 $f(x, y)$ の極値を求めよ。
$$f(x, y) = x^3 + y^3 - 3xy$$

### 解答・解説
#### 解答
$(x, y) = (1, 1)$ のとき極小値 $-1$ をとる。 $(0, 0)$ は極値ではない（鞍点）。

#### 解説
1. **1階偏導関数の計算と停留点の決定**
   極値の候補（停留点）を求めるため、 $f(x, y)$ を $x$ および $y$ で偏微分し、それぞれ $0$ とおきます。
   $$f_x(x, y) = 3x^2 - 3y = 0 \implies y = x^2 \quad \cdots \text{(i)}$$
   $$f_y(x, y) = 3y^2 - 3x = 0 \implies x = y^2 \quad \cdots \text{(ii)}$$
   式 (i) を式 (ii) に代入します：
   $$x = (x^2)^2 = x^4 \implies x^4 - x = 0 \implies x(x^3 - 1) = 0$$
   実数解を求めると、 $x = 0$ または $x = 1$ です。
   * $x = 0$ のとき： $y = 0^2 = 0$
   * $x = 1$ のとき： $y = 1^2 = 1$
   したがって、停留点は $(0, 0)$ および $(1, 1)$ の2点となります。

2. **2階偏導関数とヘッセ行列式（Hessian）の計算**
   停留点での極値の判定を行うために、2階偏導関数を計算します。
   $$f_{xx}(x, y) = 6x, \quad f_{yy}(x, y) = 6y, quad f_{xy}(x, y) = -3$$
   ヘッセ行列式 $H(x, y)$ は以下のように定義されます：
   $$H(x, y) = f_{xx}f_{yy} - (f_{xy})^2 = (6x)(6y) - (-3)^2 = 36xy - 9$$

3. **各停留点における極値の判定**
   * **停留点 $(0, 0)$ において**
     $$H(0, 0) = 36(0)(0) - 9 = -9 < 0$$
     ヘッセ行列式が負であるため、点 $(0, 0)$ は極値ではなく**鞍点（サドルポイント）**となります。
   * **停留点 $(1, 1)$ において**
     $$H(1, 1) = 36(1)(1) - 9 = 27 > 0$$
     ヘッセ行列式が正であるため極値を持ちます。さらに、
     $$f_{xx}(1, 1) = 6(1) = 6 > 0$$
     であるため、この点において関数は**極小値**をとります。
     極小値の値は次の通りです：
     $$f(1, 1) = 1^3 + 1^3 - 3(1)(1) = 1 + 1 - 3 = -1$$

---

## 【問題 18】微分積分学（曲線の曲率半径の計算） （新規追加問題）

### 問題
曲線 $y = log(cos x)$ の $x = 0$ における曲率半径 $R$ を求めよ。

### 解答・解説
#### 解答
$$1$$

#### 解説
1. **曲率半径の公式**
   平面曲線 $y = f(x)$ の曲率半径 $R$ の定義公式は以下の通りです：
   $$R = rac{left( 1 + y'^2 ight)^{3/2}}{|y''|}$$

2. **導関数の計算**
   与えられた関数 $y = log(cos x)$ を $x$ で順に微分します。
   $$y' = rac{d}{dx} left[ log(cos x) ight] = rac{1}{cos x} cdot (-sin x) = -	an x$$
   $$y'' = rac{d}{dx} left[ -	an x ight] = -sec^2 x = -rac{1}{cos^2 x}$$

3. **$x = 0$ における値の計算**
   $x = 0$ を代入して、各微分係数を求めます：
   $$y'(0) = -	an 0 = 0$$
   $$y''(0) = -rac{1}{cos^2 0} = -1$$

4. **曲率半径 $R$ の決定**
   得られた値を公式に代入します：
   $$R = rac{left( 1 + 0^2 ight)^{3/2}}{|-1|} = rac{1^{3/2}}{1} = 1$$
   したがって、 $x = 0$ における曲率半径は **1** となります。

---

## 【問題 19】微分積分学（マクローリン展開と高階微分係数の計算） （新規追加問題）

### 問題
関数 $f(x) = rac{1}{x^2 - 3x + 2}$ について、 $x=0$ における $n$ 階微分係数 $f^{(n)}(0)$ を求めよ。

### 解答・解説
#### 解答
$$f^{(n)}(0) = left( 1 - rac{1}{2^{n+1}} ight) n!$$

#### 解説
1. **部分分数分解**
   与えられた関数 $f(x)$ の分母を因数分解し、部分分数に分解します。
   $$f(x) = rac{1}{(x-1)(x-2)} = rac{1}{x-2} - rac{1}{x-1}$$
   これをマクローリン展開しやすい形式に変形します：
   $$f(x) = rac{1}{1-x} - rac{1}{2} cdot rac{1}{1 - x/2}$$

2. **等比級数展開の適用**
   マクローリン展開の基本公式である次の等比級数の和の公式（$|t| < 1$ で収束）を利用します：
   $$rac{1}{1-t} = sum_{k=0}^{infty} t^k$$
   各項に適用します：
   * 第1項： $$rac{1}{1-x} = sum_{k=0}^{infty} x^k$$
   * 第2項： $$rac{1}{1 - x/2} = sum_{k=0}^{infty} left(rac{x}{2}ight)^k = sum_{k=0}^{infty} rac{1}{2^k} x^k$$
   
   これらを $f(x)$ に代入してまとめると次のようになります：
   $$f(x) = sum_{k=0}^{infty} x^k - rac{1}{2} sum_{k=0}^{infty} rac{1}{2^k} x^k = sum_{k=0}^{infty} left( 1 - rac{1}{2^{k+1}} ight) x^k$$

3. **高階微分係数の決定**
   一般に、関数 $f(x)$ のマクローリン展開は次の式で与えられます：
   $$f(x) = sum_{k=0}^{infty} rac{f^{(k)}(0)}{k!} x^k$$
   展開式の $x^n$ の係数を比較することで、以下が得られます：
   $$rac{f^{(n)}(0)}{n!} = 1 - rac{1}{2^{n+1}}$$
   両辺に $n!$ を掛けることで、 $x=0$ における $n$ 階微分係数の一般項が求まります：
   $$f^{(n)}(0) = left( 1 - rac{1}{2^{n+1}} ight) n!$$

---

## 【問題 20】微分積分学（フーリエ級数展開と無限級数の和） （新規追加問題）

### 問題
区間 $[-pi, pi]$ において定義される関数 $f(x) = x^2$ のフーリエ級数展開を求めよ。
また、それを利用して次の級数の和（バーゼル問題）を求めよ。
$$sum_{n=1}^{infty} rac{1}{n^2}$$

### 解答・解説
#### 解答
フーリエ級数展開： $$x^2 = rac{pi^2}{3} + sum_{n=1}^{infty} rac{4(-1)^n}{n^2} cos(nx)$$
無限級数の和： $$sum_{n=1}^{infty} rac{1}{n^2} = rac{pi^2}{6}$$

#### 解説
1. **フーリエ展開の算出**
   $f(x) = x^2$ は偶関数（$f(-x) = f(x)$）であるため、フーリエ正弦係数 $b_n$ はすべて $0$ となります。したがって、余弦展開のみを求めます：
   $$f(x) sim rac{a_0}{2} + sum_{n=1}^{infty} a_n cos(nx)$$
   
   * **定数項 $a_0$ の計算**：
     $$a_0 = rac{1}{pi} int_{-pi}^{pi} x^2 ,dx = rac{2}{pi} int_0^{pi} x^2 ,dx = rac{2}{pi} left[ rac{x^3}{3} ight]_0^{pi} = rac{2pi^2}{3}$$
     これより、 $rac{a_0}{2} = rac{pi^2}{3}$ です。
     
   * **係数 $a_n$ （$n ge 1$）の計算**：
     部分積分を2回実行します：
     $$a_n = rac{1}{pi} int_{-pi}^{pi} x^2 cos(nx) ,dx = rac{2}{pi} int_0^{pi} x^2 cos(nx) ,dx$$
     $$int_0^{pi} x^2 cos(nx) ,dx = left[ x^2 rac{sin(nx)}{n} ight]_0^{pi} - int_0^{pi} 2x rac{sin(nx)}{n} ,dx = 0 - rac{2}{n} int_0^{pi} x sin(nx) ,dx$$
     $$int_0^{pi} x sin(nx) ,dx = left[ x rac{-cos(nx)}{n} ight]_0^{pi} - int_0^{pi} rac{-cos(nx)}{n} ,dx = -rac{pi cos(npi)}{n} + left[ rac{sin(nx)}{n^2} ight]_0^{pi}$$
     $cos(npi) = (-1)^n$ なので：
     $$int_0^{pi} x sin(nx) ,dx = -rac{pi (-1)^n}{n}$$
     これを代入して $a_n$ を求めます：
     $$a_n = rac{2}{pi} left( -rac{2}{n} left( -rac{pi (-1)^n}{n} ight) ight) = rac{4(-1)^n}{n^2}$$
     したがって、フーリエ展開は以下のようになります：
     $$x^2 = rac{pi^2}{3} + sum_{n=1}^{infty} rac{4(-1)^n}{n^2} cos(nx)$$

2. **無限級数の和の計算**
   得られた展開式に $x = pi$ を代入します。 $f(x)$ は $x=pi$ で連続であるため、ディリクレの収束定理より級数は元の値 $f(pi) = pi^2$ に収束します：
   $$pi^2 = rac{pi^2}{3} + sum_{n=1}^{infty} rac{4(-1)^n}{n^2} cos(npi)$$
   $cos(npi) = (-1)^n$ なので、 $(-1)^n cos(npi) = (-1)^{2n} = 1$ です：
   $$pi^2 = rac{pi^2}{3} + 4 sum_{n=1}^{infty} rac{1}{n^2}$$
   両辺から $rac{pi^2}{3}$ を引きます：
   $$rac{2pi^2}{3} = 4 sum_{n=1}^{infty} rac{1}{n^2}$$
   両辺を $4$ で割ることで、求める和が求まります：
   $$sum_{n=1}^{infty} rac{1}{n^2} = rac{pi^2}{6}$$

---

## 【問題 21】微分積分学（積分記号下の微分） （新規追加問題）

### 問題
次の広義積分（パラメータ $a \in \mathbb{R}$）の値を求めよ。
$$I(a) = \int_0^{\infty} \frac{e^{-x} \sin(ax)}{x} \,dx$$

### 解答・解説
#### 解答
$$I(a) = \arctan a$$

#### 解説
1. **積分記号下の微分の適用**
   被積分関数 $f(x, a) = \frac{e^{-x} \sin(ax)}{x}$ は、 $x > 0$ において $a$ に関して連続かつ偏微分可能です。偏導関数は次のようになります：
   $$\frac{\partial f}{\partial a} = \frac{e^{-x} \cdot x \cos(ax)}{x} = e^{-x} \cos(ax)$$
   $x=0$ における極限 $\lim_{x \to 0} \frac{\sin(ax)}{x} = a$ より、被積分関数は $x=0$ でも連続に拡張されます。
   Leibnizの積分規則（積分記号下の微分）により、 $I(a)$ を $a$ で微分します：
   $$I'(a) = \frac{d}{da} \int_0^{\infty} \frac{e^{-x} \sin(ax)}{x} \,dx = \int_0^{\infty} e^{-x} \cos(ax) \,dx$$

2. **微分値の計算**
   この積分は、部分積分を2回繰り返すか、ラプラス変換の公式 $\mathcal{L}\{\cos(at)\} = \frac{s}{s^2+a^2}$ （ここでは $s=1$）を用いることで容易に計算できます：
   $$\int_0^{\infty} e^{-x} \cos(ax) \,dx = \left[ \frac{e^{-x} (a\sin(ax) - \cos(ax))}{a^2 + 1} \right]_0^{\infty} = 0 - \frac{-1}{a^2 + 1} = \frac{1}{a^2 + 1}$$
   したがって、次の微分方程式が得られます：
   $$I'(a) = \frac{1}{a^2 + 1}$$

3. **積分による一般解と定数の決定**
   両辺を $a$ で積分します：
   $$I(a) = \int \frac{1}{a^2 + 1} \,da = \arctan a + C \quad （C \text{ は積分定数}）$$
   元の定義式に $a = 0$ を代入すると：
   $$I(0) = \int_0^{\infty} 0 \,dx = 0$$
   また、得られた一般解に $a = 0$ を代入すると $I(0) = \arctan 0 + C = C$ です。
   これより $C = 0$ と決定されます。
   したがって、求める積分の値は次のようになります：
   $$I(a) = \arctan a$$

---


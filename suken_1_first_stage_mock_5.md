# 数学検定1級 一次試験（計算技能）模擬試験［第5回］

数学検定1級一次試験（計算技能）対策のための、第5回模擬試験問題（全7問）と詳細な解答解説です。今回の模擬試験では、区分求積法（リーマン和の極限）、行列のトレース・デト値と固有値の関係、微分方程式における定数変化法、べき級数の収束半径、曲面の表面積、巡回群の生成元、および2つの正規母集団の分散比に対するF検定など、幅広いトピックをカバーします。

---

## 模擬試験問題（制限時間：60分）

### 【問題1】微分積分学（リーマン和の極限・区分求積法）
次の極限値を求めよ。
$$L = \lim_{n \to \infty} \sum_{k=1}^n \frac{n}{n^2 + k^2}$$

### 【問題2】線形代数（固有値と対角和・行列式の関係）
$A$ を固有値 $\lambda_1, \lambda_2, \lambda_3$ を持つ $3 \times 3$ の実正方行列とする。
いま、 $A$ に関して以下の条件が成り立っているとき、固有値 $\lambda_1, \lambda_2, \lambda_3$ の値を求めよ。
$$\operatorname{tr}(A) = 6, \quad \operatorname{tr}(A^2) = 14, \quad \det(A) = 6$$

### 【問題3】微分方程式（定数変化法）
微分演算子や未定係数法ではなく、**定数変化法（variation of parameters）**を用いて、次の2階非同次線形微分方程式の特解（および一般解）を求めよ。
$$y'' + y = \tan x \quad \left( -\frac{\pi}{2} < x < \frac{\pi}{2} \right)$$

### 【問題4】複素解析（べき級数の収束半径）
次の複素べき級数の収束半径 $R$ を求めよ。
$$\sum_{n=1}^{\infty} \frac{n!}{n^n} z^n$$

### 【問題5】ベクトル解析・幾何（曲面の面積）
放物面 $z = x^2 + y^2$ のうち、平面 $z = 1$ より下にある部分の曲面積 $A$ を求めよ。

### 【問題6】代数学（巡回群の生成元）
加法群 $G = \mathbb{Z}_{30}$ （法30の合同式の加法群）について、以下の問いに答えよ。
1. $G$ の生成元の個数を求めよ。
2. $G$ のすべての生成元を求めよ。

### 【問題7】確率・統計（等分散のF検定）
ある2つの独立な正規母集団から得られた標本データについて、以下の統計量が算出された。
* 標本1： 大きさ $n_1 = 6$, 不偏分散 $s_1^2 = 12.5$
* 標本2： 大きさ $n_2 = 11$, 不偏分散 $s_2^2 = 3.2$

2つの母集団の母分散が等しいという帰無仮説 $H_0: \sigma_1^2 = \sigma_2^2$ に対し、対立仮説を $H_1: \sigma_1^2 \neq \sigma_2^2$ として、有意水準 $5\%$ で両側検定を行え。
ただし、自由度 $(5, 10)$ のF分布の上側 $2.5\%$ 点を $F_{0.025}(5, 10) = 4.24$ とし、検定統計量の数値を明記して結論を述べよ。

---
---

## 解答・解説

### 【問題1】の解答・解説
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

### 【問題2】の解答・解説
#### 解答
$\lambda = 1, \; 2, \; 3$ （順不同）

#### 詳細な計算ステップ
1. **固有値とトレース・行列式の基本定理の整理**
   行列 $A$ の固有値を $\lambda_1, \lambda_2, \lambda_3$ とすると、線形代数学の基本性質から以下の関係式が成立します：
   * **固有値の和（トレース）**：
     $$\lambda_1 + \lambda_2 + \lambda_3 = \operatorname{tr}(A) = 6$$
   * **固有値の平方和（$A^2$ のトレース）**：
     $A$ の固有値が $\lambda_i$ のとき $A^2$ の固有値は $\lambda_i^2$ であるため、
     $$\lambda_1^2 + \lambda_2^2 + \lambda_3^2 = \operatorname{tr}(A^2) = 14$$
   * **固有値の積（行列式）**：
     $$\lambda_1 \lambda_2 \lambda_3 = \det(A) = 6$$

2. **2変数の積の和の導出**
   3変数の対称式に関する展開公式：
   $$(\lambda_1 + \lambda_2 + \lambda_3)^2 = \lambda_1^2 + \lambda_2^2 + \lambda_3^2 + 2(\lambda_1\lambda_2 + \lambda_2\lambda_3 + \lambda_3\lambda_1)$$
   に既知の数値を代入します：
   $$6^2 = 14 + 2(\lambda_1\lambda_2 + \lambda_2\lambda_3 + \lambda_3\lambda_1)$$
   $$36 = 14 + 2(\lambda_1\lambda_2 + \lambda_2\lambda_3 + \lambda_3\lambda_1)$$
   $$22 = 2(\lambda_1\lambda_2 + \lambda_2\lambda_3 + \lambda_3\lambda_1) \implies \lambda_1\lambda_2 + \lambda_2\lambda_3 + \lambda_3\lambda_1 = 11$$

3. **固有多項式（3次方程式）の構成**
   3つの数 $\lambda_1, \lambda_2, \lambda_3$ を解とする 3次方程式は、解と係数の関係より次のようになります：
   $$t^3 - (\lambda_1 + \lambda_2 + \lambda_3)t^2 + (\lambda_1\lambda_2 + \lambda_2\lambda_3 + \lambda_3\lambda_1)t - \lambda_1\lambda_2\lambda_3 = 0$$
   得られた値を代入します：
   $$t^3 - 6t^2 + 11t - 6 = 0$$

4. **3次方程式の因数分解**
   左辺 $P(t) = t^3 - 6t^2 + 11t - 6$ において、 $t=1$ を代入します：
   $$P(1) = 1^3 - 6(1)^2 + 11(1) - 6 = 1 - 6 + 11 - 6 = 0$$
   因数定理より $P(t)$ は $(t-1)$ を因数に持ちます。多項式の割り算（または組立除法）を実行します：
   $$t^3 - 6t^2 + 11t - 6 = (t-1)(t^2 - 5t + 6) = 0$$
   2次式部分をさらに因数分解します：
   $$(t-1)(t-2)(t-3) = 0$$
   よって、方程式の解は $t = 1, 2, 3$ です。

5. **結論**
   固有値の集合は $\{1, 2, 3\}$ となります。

---

### 【問題3】の解答・解説
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

### 【問題4】の解答・解説
#### 解答
$$R = e$$

#### 詳細な計算ステップ
1. **べき級数の収束半径の公式（ダランベールの判定法）**
   べき級数 $\sum_{n=0}^{\infty} a_n z^n$ の収束半径 $R$ は次の比の極限で求められます：
   $$R = \lim_{n \to \infty} \left| \frac{a_n}{a_{n+1}} \right|$$

2. **係数の比の計算**
   本級数の係数は $a_n = \frac{n!}{n^n}$ です。
   隣り合う項の比を計算します：
   $$\left| \frac{a_n}{a_{n+1}} \right| = \frac{\frac{n!}{n^n}}{\frac{(n+1)!}{(n+1)^{n+1}}} = \frac{n!}{n^n} \cdot \frac{(n+1)^{n+1}}{(n+1)!}$$
   ここで、階乗の性質 $(n+1)! = (n+1)n!$ を適用して簡約化します：
   $$\left| \frac{a_n}{a_{n+1}} \right| = \frac{n!}{n^n} \cdot \frac{(n+1)^{n+1}}{(n+1)n!} = \frac{(n+1)^{n+1}}{n^n(n+1)}$$
   分子の $(n+1)^{n+1}$ を分母の $(n+1)$ で 1個分約分します：
   $$\left| \frac{a_n}{a_{n+1}} \right| = \frac{(n+1)^n}{n^n} = \left( \frac{n+1}{n} \right)^n = \left( 1 + \frac{1}{n} \right)^n$$

3. **極限値の算出**
   $n \to \infty$ の極限をとります。オイラー数 $e$ の定義極限：
   $$\lim_{n \to \infty} \left( 1 + \frac{1}{n} \right)^n = e$$
   を適用すると：
   $$R = \lim_{n \to \infty} \left( 1 + \frac{1}{n} \right)^n = e$$
   したがって、収束半径は $e$ です。

---

### 【問題5】の解答・解説
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

### 【問題6】の解答・解説
#### 解答
1. 8個
2. $\{1, \; 7, \; 11, \; 13, \; 17, \; 19, \; 23, \; 29\} \pmod{30}$

#### 詳細な計算ステップ
1. **生成元の個数の決定**
   有限巡回加法群 $\mathbb{Z}_m$ の生成元の個数は、オイラーの $\phi$ 関数を用いて $\phi(m)$ 個となります。
   本問では $m = 30$ です。 $30$ を素因数分解すると：
   $$30 = 2 \times 3 \times 5$$
   オイラーの $\phi$ 関数の公式を適用します：
   $$\phi(30) = 30 \left(1 - \frac{1}{2}\right)\left(1 - \frac{1}{3}\right)\left(1 - \frac{1}{5}\right) = 30 \times \frac{1}{2} \times \frac{2}{3} \times \frac{4}{5} = 8$$
   よって、生成元の個数は **8個** です。

2. **すべての生成元のリストアップ**
   加法群 $\mathbb{Z}_{30}$ の剰余類のうち、代表元 $a \in \{0, 1, \dots, 29\}$ が生成元となる条件は、 $\gcd(a, 30) = 1$ （互いに素）であることです。
   $30 = 2 \times 3 \times 5$ より、 $2$ の倍数、 $3$ の倍数、 $5$ の倍数をすべて除外します：
   * 除外される数：偶数すべて、 $3$ の倍数すべて、 $5$ の倍数すべて。
   * 残る数：
     * $1$
     * $7$
     * $11$
     * $13$
     * $17$
     * $19$
     * $23$
     * $29$
   これら 8個の元が群 $G$ の生成元となります。

---

### 【問題7】の解答・解説
#### 解答
* **検定統計量（実現値）**： $F = 3.91$
* **判定**： 帰無仮説 $H_0$ は棄却されない。
* **結論**： 有意水準 $5\%$ において、2つの母分散に有意な差があるとは言えない（等分散の仮説は否定されない）。

#### 詳細な計算ステップ
1. **仮説の設定**
   2つの正規母集団の分散 $\sigma_1^2, \sigma_2^2$ について以下の通り仮説を設定します：
   * 帰無仮説 $H_0: \sigma_1^2 = \sigma_2^2$ （2つの母分散は等しい）
   * 対立仮説 $H_1: \sigma_1^2 \neq \sigma_2^2$ （2つの母分散は等しくない、両側検定）

2. **検定統計量 $F$ の計算**
   等分散の検定統計量 $F$ は、不偏分散の比をとります。通常、判定を簡略化するため大きい不偏分散を分子、小さい不偏分散を分母に配置します：
   $$F = \frac{s_1^2}{s_2^2}$$
   与えられた不偏分散の値を代入します（$s_1^2 = 12.5, \; s_2^2 = 3.2$）：
   $$F = \frac{12.5}{3.2} = 3.90625 \approx 3.91$$
   ここで、標本1の自由度は $\nu_1 = n_1 - 1 = 6 - 1 = 5$、標本2の自由度は $\nu_2 = n_2 - 1 = 11 - 1 = 10$ です。

3. **棄却域の決定**
   帰無仮説 $H_0$ のもとで、統計量 $F$ は自由度 $(\nu_1, \nu_2) = (5, 10)$ のF分布に従います。
   有意水準 $5\%$ （両側検定）のため、上側確率が $2.5\%$ となる点（$F_{0.025}(5, 10)$）を棄却限界値とします。
   問題文より、上側限界値は以下の通りです：
   $$F_{0.025}(5, 10) = 4.24$$
   よって、棄却域は $F \ge 4.24$ となります。

4. **判定と結論**
   計算した統計量の値 $F \approx 3.91$ を限界値と比較します：
   $$F = 3.91 < 4.24$$
   統計量は棄却域に入りません。したがって、帰無仮説 $H_0$ は棄却されず、有意水準 $5\%$ において「2つの母集団の分散に有意な差があるとは言えない」と判定されます。

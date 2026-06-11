# 数学検定1級 一次試験（計算技能）模擬試験

数学検定1級の一次試験（計算技能）は、**制限時間60分で全7問**の計算問題が出題され、解答（数値や式）のみを記述する形式です。本模擬試験では、分野の重複がないように厳選された7つの問題と、その詳細な解答解説を提供します。

---

## 模擬試験問題（制限時間：60分）

### 【問題1】微分積分学（広義積分と特殊関数）
次の広義積分の値を求めよ。
$$I = \int_{0}^{\infty} \frac{x}{(1+x^3)^2} \,dx$$

### 【問題2】線形代数（行列式）
次の $4 \times 4$ 行列の行列式を求めよ。
$$D = \begin{vmatrix}
x & a & a & a \\
a & x & a & a \\
a & a & x & a \\
a & a & a & x
\end{vmatrix}$$

### 【問題3】微分方程式（境界値問題）
次の常微分方程式の境界値問題を解け。
$$y'' + 4y = 0, \quad y(0) = 1, \quad y\left(\frac{\pi}{4}\right) = 2$$

### 【問題4】複素解析（複素積分）
留数定理または複素積分の手法を用いて、次の実積分の値を求めよ。
$$I = \int_{0}^{2\pi} \frac{1}{5 - 4\cos \theta} \,d\theta$$

### 【問題5】ベクトル解析（線積分・グリーンの定理）
$xy$ 平面上の円 $C: (x-1)^2 + y^2 = 4$ を反時計回りに1周するとき、次の線積分の値を求めよ。
$$\oint_C \left( (y + \sin(x^2)) \,dx + (3x - e^{y^3}) \,dy \right)$$

### 【問題6】整数論（合同式とオイラーの $\phi$ 関数）
$3^{402}$ の下2桁（100で割った余り）を求めよ。

### 【問題7】確率・統計（正規分布のモーメント）
確率変数 $X$ が標準正規分布 $N(0, 1)$ に従うとき、4次モーメントの期待値 $E[X^4]$ を求めよ。

---
---

## 解答・解説

### 【問題1】の解答・解説
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

### 【問題2】の解答・解説
#### 解答
$$(x+3a)(x-a)^3$$

#### 詳細な計算ステップ
1. **行基本変形（第1列の和）**
   行列のすべての行を第1行に加える基本変形を行います。
   $$\text{第1行} \to \text{第1行} + \text{第2行} + \text{第3行} + \text{第4行}$$
   これにより、第1行の各成分はすべて $x + a + a + a = x + 3a$ になります。
   $$D = \begin{vmatrix}
   x+3a & x+3a & x+3a & x+3a \\
   a & x & a & a \\
   a & a & x & a \\
   a & a & a & x
   \end{vmatrix}$$

2. **共通因数の括り出し**
   第1行の共通因数 $(x+3a)$ を行列式の外にくくり出します。
   $$D = (x+3a) \begin{vmatrix}
   1 & 1 & 1 & 1 \\
   a & x & a & a \\
   a & a & x & a \\
   a & a & a & x
   \end{vmatrix}$$

3. **第1列を用いた掃き出し**
   第1列の 1 を利用して、第2行以下を掃き出します。
   * $\text{第2行} \to \text{第2行} - a \times \text{第1行}$
   * $\text{第3行} \to \text{第3行} - a \times \text{第1行}$
   * $\text{第4行} \to \text{第4行} - a \times \text{第1行}$
   この変形により、第1列の第2行から第4行まではすべて $a - a\cdot 1 = 0$ となり、対角成分は $x - a\cdot 1 = x - a$ になります。他の非対角成分は $a - a\cdot 1 = 0$ になります。
   $$D = (x+3a) \begin{vmatrix}
   1 & 1 & 1 & 1 \\
   0 & x-a & 0 & 0 \\
   0 & 0 & x-a & 0 \\
   0 & 0 & 0 & x-a
   \end{vmatrix}$$

4. **上三角行列の行列式計算**
   この行列は、対角成分より左下がすべて $0$ の上三角行列であるため、行列式の値は対角成分の積になります。
   $$D = (x+3a) \cdot 1 \cdot (x-a) \cdot (x-a) \cdot (x-a) = (x+3a)(x-a)^3$$

---

### 【問題3】の解答・解説
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

### 【問題4】の解答・解説
#### 解答
$$\frac{2}{3}\pi$$

#### 詳細な計算ステップ
1. **複素平面への変換**
   複素平面上の単位円 $C: |z| = 1$ を反時計回りに1周する積分に変換するため、 $z = e^{i\theta}$ とおきます。
   * $dz = i e^{i\theta} \,d\theta = i z \,d\theta \implies d\theta = \frac{dz}{iz}$
   * $\cos \theta = \frac{e^{i\theta} + e^{-i\theta}}{2} = \frac{z + z^{-1}}{2} = \frac{z^2 + 1}{2z}$
   積分範囲について、 $\theta: 0 \to 2\pi$ は複素平面上の単位円 $C$ を反時計回りに1周することに対応します。

2. **被積分関数の変形**
   これらを変数代入して式を整理します。
   $$I = \oint_C \frac{1}{5 - 4\left(\frac{z + z^{-1}}{2}\right)} \left(\frac{dz}{iz}\right) = \oint_C \frac{1}{5 - 2(z + z^{-1})} \frac{dz}{iz}$$
   $$I = \oint_C \frac{1}{z(5 - 2z - 2z^{-1})} \frac{dz}{i} = \frac{1}{i} \oint_C \frac{1}{5z - 2z^2 - 2} \,dz = -\frac{1}{i} \oint_C \frac{1}{2z^2 - 5z + 2} \,dz$$

3. **極（Singularities）の決定**
   被積分関数の分母 $2z^2 - 5z + 2 = 0$ の解を求めます。たすき掛け因数分解を行うと：
   $$(2z - 1)(z - 2) = 0 \implies z = \frac{1}{2}, \; 2$$
   したがって、極は $z = \frac{1}{2}$ と $z = 2$ の 2点（いずれも1位の極）です。
   積分経路 $C$ は単位円 $|z|=1$ なので、その**内部に含まれる極は $z = \frac{1}{2}$ のみ**です。（$z=2$ は円の外側なので無視します）

4. **留数（Residue）の計算**
   $z = \frac{1}{2}$ における留数 $\operatorname{Res}\left(g, \frac{1}{2}\right)$ を求めます。ここで $g(z) = \frac{1}{2z^2-5z+2}$ です。
   $$\operatorname{Res}\left(g, \frac{1}{2}\right) = \lim_{z \to \frac{1}{2}} \left(z - \frac{1}{2}\right) \frac{1}{2\left(z - \frac{1}{2}\right)(z - 2)} = \lim_{z \to \frac{1}{2}} \frac{1}{2(z-2)} = \frac{1}{2\left(\frac{1}{2} - 2\right)} = \frac{1}{-3} = -\frac{1}{3}$$

5. **留数定理の適用**
   留数定理により：
   $$I = -\frac{1}{i} \cdot 2\pi i \operatorname{Res}\left(g, \frac{1}{2}\right) = -2\pi \left(-\frac{1}{3}\right) = \frac{2}{3}\pi$$

---

### 【問題5】の解答・解説
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

### 【問題6】の解答・解説
#### 解答
$$09$$

#### 詳細な計算ステップ
1. **合同式の定式化**
   下2桁を求めることは、法 $100$ における合同式 $3^{402} \pmod{100}$ を求めることと同じです。
   $3$ と $100$ は互いに素（$\gcd(3, 100) = 1$）であるため、オイラーの定理を適用できます。

2. **オイラーの $\phi$ 関数の計算**
   法 $m = 100$ を素因数分解します。
   $$100 = 2^2 \times 5^2$$
   オイラーの $\phi$ 関数の公式より：
   $$\phi(100) = 100 \left(1 - \frac{1}{2}\right)\left(1 - \frac{1}{5}\right) = 100 \times \frac{1}{2} \times \frac{4}{5} = 40$$
   これは、 $1$ から $100$ までの整数のうち、 $100$ と互いに素なものが 40個あることを意味します。

3. **オイラーの定理の適用**
   オイラーの定理 $a^{\phi(m)} \equiv 1 \pmod m$ より：
   $$3^{40} \equiv 1 \pmod{100}$$

4. **指数の簡単化と計算**
   指数の $402$ を $40$ で割ります。
   $$402 = 40 \times 10 + 2$$
   これを利用してべき乗を分解します。
   $$3^{402} = (3^{40})^{10} \times 3^2$$
   両辺で $\pmod{100}$ をとると、 $3^{40} \equiv 1$ より：
   $$3^{402} \equiv (1)^{10} \times 9 \equiv 9 \pmod{100}$$
   余りが $9$ となるため、下2桁は **09** です。（十の位が 0、一の位が 9）

---

### 【問題7】の解答・解説
#### 解答
$$3$$

#### 詳細な計算ステップ
1. **期待値の積分の立式**
   標準正規分布の確率密度関数は $f(x) = \frac{1}{\sqrt{2\pi}} e^{-x^2/2}$ なので、期待値 $E[X^4]$ は：
   $$E[X^4] = \int_{-\infty}^{\infty} x^4 \cdot \frac{1}{\sqrt{2\pi}} e^{-x^2/2} \,dx$$
   被積分関数は偶関数（$(-x)^4 e^{-(-x)^2/2} = x^4 e^{-x^2/2}$）なので、積分範囲を $[0, \infty)$ に変更して2倍します。
   $$E[X^4] = \frac{2}{\sqrt{2\pi}} \int_0^{\infty} x^4 e^{-x^2/2} \,dx = \sqrt{\frac{2}{\pi}} \int_0^{\infty} x^4 e^{-x^2/2} \,dx$$

2. **部分積分の適用（1回目）**
   被積分関数を $x^3 \cdot (x e^{-x^2/2})$ と分解して部分積分を行います。ここで $\frac{d}{dx}(-e^{-x^2/2}) = x e^{-x^2/2}$ であることを利用します。
   $$\int_0^{\infty} x^4 e^{-x^2/2} \,dx = \int_0^{\infty} x^3 \left( x e^{-x^2/2} \right) \,dx$$
   $$= \left[ x^3 \left( -e^{-x^2/2} \right) \right]_0^{\infty} - \int_0^{\infty} 3x^2 \left( -e^{-x^2/2} \right) \,dx$$
   無限遠点での極限に関して、指数関数の減衰の方が代数関数 $x^3$ よりも速いため、 $\lim_{x \to \infty} -x^3 e^{-x^2/2} = 0$ です。また $x=0$ を代入しても $0$ になります。
   したがって、第1項は $0$ になり、式は以下のように簡単化されます。
   $$= 3 \int_0^{\infty} x^2 e^{-x^2/2} \,dx$$

3. **部分積分の適用（2回目）**
   同様に $x \cdot (x e^{-x^2/2})$ と分解して部分積分を行います。
   $$\int_0^{\infty} x^2 e^{-x^2/2} \,dx = \int_0^{\infty} x \left( x e^{-x^2/2} \right) \,dx$$
   $$= \left[ x \left( -e^{-x^2/2} \right) \right]_0^{\infty} - \int_0^{\infty} 1 \cdot \left( -e^{-x^2/2} \right) \,dx$$
   第1項は再び $0$ になります。
   $$= \int_0^{\infty} e^{-x^2/2} \,dx$$

4. **ガウス積分の適用**
   標準正規分布の全確率が 1 であること（$\frac{1}{\sqrt{2\pi}}\int_{-\infty}^{\infty} e^{-x^2/2} dx = 1 \implies \int_0^{\infty} e^{-x^2/2} dx = \frac{\sqrt{2\pi}}{2} = \sqrt{\frac{\pi}{2}}$）を利用します。
   これらをまとめると：
   $$\int_0^{\infty} x^4 e^{-x^2/2} \,dx = 3 \times \int_0^{\infty} x^2 e^{-x^2/2} \,dx = 3 \sqrt{\frac{\pi}{2}}$$
   これを $E[X^4]$ の式に代入します。
   $$E[X^4] = \sqrt{\frac{2}{\pi}} \left( 3 \sqrt{\frac{\pi}{2}} \right) = 3 \left( \sqrt{\frac{2}{\pi}} \sqrt{\frac{\pi}{2}} \right) = 3 \cdot 1 = 3$$

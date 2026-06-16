# 数学検定1級 一次試験 模擬問題：線形代数 (Linear Algebra)

数検1級一次試験対策のための、**線形代数 (Linear Algebra)**分野の模擬・演習問題（全17問）と詳細な解答解説です。

[分野別問題集トップに戻る](README.md)

---

## 【問題 1】線形代数（行列式） （第1回 模擬試験・問題2）

### 問題
次の $4 \times 4$ 行列の行列式を求めよ。
$$D = \begin{vmatrix}
x & a & a & a \\
a & x & a & a \\
a & a & x & a \\
a & a & a & x
\end{vmatrix}$$

### 解答・解説
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

## 【問題 2】線形代数（行列の累乗） （第2回 模擬試験・問題2）

### 問題
次の行列 $A$ に対し、 $A^n$ （$n$ は正の整数）を求めよ。
$$A = \begin{pmatrix} 4 & -2 \\ 1 & 1 \end{pmatrix}$$

### 解答・解説
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

## 【問題 3】線形代数（正射影行列） （第3回 模擬試験・問題2）

### 問題
3次元数ベクトル空間 $\mathbb{R}^3$ において、ベクトル $\mathbf{v} = \begin{pmatrix} 1 \\ 2 \\ 2 \end{pmatrix}$ が生成する部分空間を $W$ とする。このとき、 $W$ への直交射影（正射影）を表す行列 $P$ を求めよ。

### 解答・解説
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

## 【問題 4】線形代数（線形独立・パラメータ決定） （第4回 模擬試験・問題2）

### 問題
次の 3つの 3次元ベクトル $\mathbf{v}_1, \mathbf{v}_2, \mathbf{v}_3$ が線形従属（一次従属）となるような、実数 $a$ の値を求めよ。
$$\mathbf{v}_1 = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}, \quad \mathbf{v}_2 = \begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix}, \quad \mathbf{v}_3 = \begin{pmatrix} 2 \\ a \\ 2 \end{pmatrix}$$

### 解答・解説
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

## 【問題 5】線形代数（固有値と対角和・行列式の関係） （第5回 模擬試験・問題2）

### 問題
$A$ を固有値 $\lambda_1, \lambda_2, \lambda_3$ を持つ $3 \times 3$ の実正方行列とする。
いま、 $A$ に関して以下の条件が成り立っているとき、固有値 $\lambda_1, \lambda_2, \lambda_3$ の値を求めよ。
$$\operatorname{tr}(A) = 6, \quad \operatorname{tr}(A^2) = 14, \quad \det(A) = 6$$

### 解答・解説
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

## 【問題 6】線形代数（階数とパラメータによる場合分け） （第6回 模擬試験・問題2）

### 問題
実数パラメータ $a$ に対して、次の行列 $A$ の階数（rank）を求めよ。
$$A = \begin{pmatrix} 1 & a & 1 \\ a & 1 & 1 \\ 1 & 1 & a \end{pmatrix}$$

### 解答・解説
#### 解答
* $a \neq 1$ かつ $a \neq -2$ のとき： $\operatorname{rank}(A) = 3$
* $a = -2$ のとき： $\operatorname{rank}(A) = 2$
* $a = 1$ のとき： $\operatorname{rank}(A) = 1$

#### 詳細な計算ステップ
1. **行列式の計算**
   $3 \times 3$ 行列 $A$ の行列式 $\det(A)$ を計算し、正則となる条件を調べます：
   $$\det(A) = \begin{vmatrix} 1 & a & 1 \\ a & 1 & 1 \\ 1 & 1 & a \end{vmatrix}$$
   第1行および第2行から、それぞれ第3行を引き算します（第1行 $\to$ 第1行 $-$ 第3行、第2行 $\to$ 第2行 $-$ 第3行）：
   $$\det(A) = \begin{vmatrix} 1-1 & a-1 & 1-a \\ a-1 & 1-1 & 1-a \\ 1 & 1 & a \end{vmatrix} = \begin{vmatrix} 0 & a-1 & -(a-1) \\ a-1 & 0 & -(a-1) \\ 1 & 1 & a \end{vmatrix}$$
   第1行から因数 $(a-1)$、第2行から因数 $(a-1)$ をそれぞれくくり出します：
   $$\det(A) = (a-1)^2 \begin{vmatrix} 0 & 1 & -1 \\ 1 & 0 & -1 \\ 1 & 1 & a \end{vmatrix}$$
   残った $3 \times 3$ 行列式を第1行に関して展開します：
   $$\begin{vmatrix} 0 & 1 & -1 \\ 1 & 0 & -1 \\ 1 & 1 & a \end{vmatrix} = -1 \begin{vmatrix} 1 & -1 \\ 1 & a \end{vmatrix} + (-1) \begin{vmatrix} 1 & 0 \\ 1 & 1 \end{vmatrix} = -1(a + 1) - 1(1) = -a - 2 = -(a+2)$$
   したがって、行列式は以下の通りです：
   $$\det(A) = -(a-1)^2(a+2)$$

2. **場合分けによる階数（rank）の決定**
   * **ケース1： $\det(A) \neq 0$ （$a \neq 1$ かつ $a \neq -2$）**
     行列式が $0$ でないため、行列 $A$ は正則であり、最大階数をとります：
     $$\operatorname{rank}(A) = 3$$
   
   * **ケース2： $a = 1$ のとき**
     行列 $A$ はすべての成分が $1$ の行列になります：
     $$A = \begin{pmatrix} 1 & 1 & 1 \\ 1 & 1 & 1 \\ 1 & 1 & 1 \end{pmatrix}$$
     すべての行ベクトルが同一 $\begin{pmatrix} 1 & 1 & 1 \end{pmatrix}$ なので、線形独立な行の最大数は 1 です：
     $$\operatorname{rank}(A) = 1$$
   
   * **ケース3： $a = -2$ のとき**
     行列 $A$ に $a = -2$ を代入し、行基本変形を行います：
     $$A = \begin{pmatrix} 1 & -2 & 1 \\ -2 & 1 & 1 \\ 1 & 1 & -2 \end{pmatrix}$$
     * 第2行に第1行の2倍を加算（第2行 $\to$ 第2行 $+ 2 \times$ 第1行）：
       $$\to \begin{pmatrix} 1 & -2 & 1 \\ 0 & -3 & 3 \\ 1 & 1 & -2 \end{pmatrix}$$
     * 第3行から第1行を減算（第3行 $\to$ 第3行 $-$ 第1行）：
       $$\to \begin{pmatrix} 1 & -2 & 1 \\ 0 & -3 & 3 \\ 0 & 3 & -3 \end{pmatrix}$$
     * 第2行を $-3$ で除算し、その3倍を第3行から減算します：
       $$\to \begin{pmatrix} 1 & -2 & 1 \\ 0 & 1 & -1 \\ 0 & 0 & 0 \end{pmatrix}$$
     この階段行列において、非ゼロ行数は 2 です。したがって：
     $$\operatorname{rank}(A) = 2$$

---

## 【問題 7】線形代数（ケーリー・ハミルトンの定理と多項式） （第7回 模擬試験・問題2）

### 問題
行列 $A = \begin{pmatrix} 3 & 1 \\ 1 & 2 \end{pmatrix}$ に対し、ケーリー・ハミルトンの定理および多項式の除法を用いて、次の行列多項式の値を求めよ。
$$P(A) = A^4 - 5A^3 + 7A^2 - 3I$$

### 解答・解説
#### 解答
$$\begin{pmatrix} 17 & 10 \\ 10 & 7 \end{pmatrix}$$

#### 詳細な計算ステップ
1. **ケーリー・ハミルトンの定理の適用**
   $2 \times 2$ 行列 $A = \begin{pmatrix} 3 & 1 \\ 1 & 2 \end{pmatrix}$ について、ケーリー・ハミルトンの定理 $A^2 - \operatorname{tr}(A)A + \det(A)I = O$ を用います：
   * トレース： $\operatorname{tr}(A) = 3 + 2 = 5$
   * 行列式： $\det(A) = 3(2) - 1(1) = 5$
   したがって、次の行列等式が成り立ちます：
   $$A^2 - 5A + 5I = O \quad \cdots \text{(3)}$$

2. **多項式の除法（次数下げ）**
   求めたい次数 $4$ の行列多項式 $P(x) = x^4 - 5x^3 + 7x^2 - 3$ を、特性多項式 $Q(x) = x^2 - 5x + 5$ で割る多項式の割り算を行います：
   $$x^4 - 5x^3 + 7x^2 - 3 = (x^2 - 5x + 5)x^2 + 2x^2 - 3$$
   さらに、余り $2x^2 - 3$ から $x^2$ を消去するため $2(x^2 - 5x + 5)$ で割ると、次のようになります：
   $$x^4 - 5x^3 + 7x^2 - 3 = (x^2 - 5x + 5)(x^2 + 2) + 10x - 13$$

3. **行列の代入と簡略化**
   この多項式等式に行列 $A$ を代入します。定数項は単位行列 $I$ に置き換わります：
   $$P(A) = (A^2 - 5A + 5I)(A^2 + 2I) + 10A - 13I$$
   式 (3) より $A^2 - 5A + 5I = O$ なので、第1項は零行列 $O$ となり消去されます：
   $$P(A) = O \cdot (A^2 + 2I) + 10A - 13I = 10A - 13I$$

4. **行列値の計算**
   具体的な行列の成分を代入して計算します：
   $$P(A) = 10 \begin{pmatrix} 3 & 1 \\ 1 & 2 \end{pmatrix} - 13 \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 30 & 10 \\ 10 & 20 \end{pmatrix} - \begin{pmatrix} 13 & 0 \\ 0 & 13 \end{pmatrix} = \begin{pmatrix} 17 & 10 \\ 10 & 7 \end{pmatrix}$$

---

## 【問題 8】線形代数（グラム・シュミットの直交化法） （第8回 模擬試験・問題2）

### 問題
$\mathbb{R}^3$ の次の 3つの一次独立なベクトル $\mathbf{u}_1, \mathbf{u}_2, \mathbf{u}_3$ を、グラム・シュミットの直交化法を用いて正規直交化し、正規直交基底 $\{\mathbf{e}_1, \mathbf{e}_2, \mathbf{e}_3\}$ を求めよ。
$$\mathbf{u}_1 = \begin{pmatrix} 1 \\ 1 \\ 0 \end{pmatrix}, \quad \mathbf{u}_2 = \begin{pmatrix} 0 \\ 1 \\ 1 \end{pmatrix}, \quad \mathbf{u}_3 = \begin{pmatrix} 1 \\ 0 \\ 1 \end{pmatrix}$$

### 解答・解説
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

## 【問題 9】線形代数（対角化可能性と最小多項式） （第9回 模擬試験・問題2）

### 問題
次の $3 \times 3$ 行列 $A$ について、以下の問いに答えよ。
$$A = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \\ 0 & 0 & 2 \end{pmatrix}$$
1. 行列 $A$ が対角化可能であるか判定せよ。
2. 行列 $A$ の最小多項式 $m(x)$ を求めよ。

### 解答・解説
#### 解答
1. 対角化可能ではない。
2. $m(x) = (x-1)^2(x-2)$ （または $m(A) = (A-I)^2(A-2I) = O$）

#### 詳細な計算ステップ
1. **固有値と固有多項式の計算**
   行列 $A = \begin{pmatrix} 1 & 1 & 0 \\ 0 & 1 & 1 \\ 0 & 0 & 2 \end{pmatrix}$ は上三角行列であるため、対角成分がそのまま固有値となります。
   特性多項式 $p(\lambda)$ は次の通りです：
   $$p(\lambda) = \det(A - \lambda I) = (1-\lambda)^2(2-\lambda) = -(\lambda-1)^2(\lambda-2)$$
   したがって、固有値は以下の通りです：
   * $\lambda = 1$ （重複度 2）
   * $\lambda = 2$ （重複度 1）

2. **対角化可能性の判定**
   固有値 $\lambda = 1$ に対する固有空間の次元（幾何学的重複度） $d_1$ を調べます：
   $$A - I = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 1 \end{pmatrix}$$
   この行列の階数（rank）は、明らかに $2$ です（第2行と第3行は実質的に同一であり、第1行と第2行が一次独立なため）。
   次元定理（Rank-Nullity Theorem）より：
   $$d_1 = \dim \operatorname{Ker}(A - I) = 3 - \operatorname{rank}(A - I) = 3 - 2 = 1$$
   固有値 $\lambda = 1$ の代数的重複度（特性多項式における重根の数）は $2$ であるのに対し、幾何学的重複度（一次独立な固有ベクトルの数）は $1$ です。
   代数的重複度と幾何学的重複度が一致しないため、行列 $A$ は**対角化可能ではありません**。

3. **最小多項式 $m(x)$ の決定**
   最小多項式 $m(x)$ は、特性多項式と同じ固有値を根に持ち、かつ $m(A) = O$ を満たす最小次数の単項式です。
   特性多項式の因数から、最小多項式の候補は次の2つに絞られます：
   * 候補1： $g_1(x) = (x-1)(x-2)$
   * 候補2： $g_2(x) = (x-1)^2(x-2)$
   
   実際に $g_1(A)$ を計算してみます：
   $$(A-I)(A-2I) = \begin{pmatrix} 0 & 1 & 0 \\ 0 & 0 & 1 \\ 0 & 0 & 1 \end{pmatrix} \begin{pmatrix} -1 & 1 & 0 \\ 0 & -1 & 1 \\ 0 & 0 & 0 \end{pmatrix} = \begin{pmatrix} 0 & -1 & 1 \\ 0 & 0 & 0 \\ 0 & 0 & 0 \end{pmatrix} \neq O$$
   $g_1(A) \neq O$ であるため、最小多項式は $g_1(x)$ ではありません。
   ハミルトン・ケーリーの定理より特性多項式では必ず $p(A) = O$ となるため、残った $g_2(x)$ が最小多項式となります：
   $$m(x) = (x-1)^2(x-2)$$

---

## 【問題 10】線形代数（平面への直交射影） （第10回 模擬試験・問題2）

### 問題
3次元空間のベクトル $\mathbf{v} = \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}$ の、方程式 $x - y + 2z = 0$ で表される平面への直交射影ベクトル $\mathbf{p}$ を求めよ。

### 解答・解説
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

## 【問題 11】線形代数（行列式） （模擬問題集・問題2）

### 問題
次の $n$ 次正方行列の行列式 $D_n$ を $n$ を用いて表せ。
$$D_n = \begin{vmatrix}
3 & 2 & 0 & 0 & \dots & 0 & 0 \\
1 & 3 & 2 & 0 & \dots & 0 & 0 \\
0 & 1 & 3 & 2 & \dots & 0 & 0 \\
\vdots & \vdots & \vdots & \vdots & \ddots & \vdots & \vdots \\
0 & 0 & 0 & 0 & \dots & 3 & 2 \\
0 & 0 & 0 & 0 & \dots & 1 & 3
\end{vmatrix}$$

### 解答・解説
#### 解答
$$D_n = 2^{n+1} - 1$$

#### 解説
第1行に関して余因子展開を行い、隣接3項間の漸化式を導きます。

第1行で展開すると、
$$D_n = 3 D_{n-1} - 2 \begin{vmatrix}
1 & 2 & 0 & \dots & 0 \\
0 & 3 & 2 & \dots & 0 \\
\vdots & \vdots & \vdots & \ddots & \vdots \\
0 & 0 & 0 & \dots & 3
\end{vmatrix}_{(n-1)\text{次}}$$

右辺第2項の行列式の第1列に関してさらに展開すると、値は $1 \cdot D_{n-2}$ となります。したがって、次の漸化式が得られます。
$$D_n = 3 D_{n-1} - 2 D_{n-2} \quad (n \ge 3)$$

初期条件（$n=1, 2$）を求めます。
* $D_1 = |3| = 3$
* $D_2 = \begin{vmatrix} 3 & 2 \\ 1 & 3 \end{vmatrix} = 9 - 2 = 7$

この漸化式 $D_n - 3 D_{n-1} + 2 D_{n-2} = 0$ の特性方程式は、
$$t^2 - 3t + 2 = 0 \implies (t-1)(t-2) = 0$$
よって、特性根は $t = 1, 2$ です。
一般解は次のように置くことができます。
$$D_n = C_1 \cdot 1^n + C_2 \cdot 2^n = C_1 + C_2 2^n$$

初期条件を代入して定数 $C_1, C_2$ を決定します。
1. $n=1$ のとき： $C_1 + 2C_2 = 3$
2. $n=2$ のとき： $C_1 + 4C_2 = 7$

下式から上式を引くと、
$$2C_2 = 4 \implies C_2 = 2$$
これを代入して、
$$C_1 + 4 = 3 \implies C_1 = -1$$

したがって、求める行列式は次のようになります。
$$D_n = -1 + 2 \cdot 2^n = 2^{n+1} - 1$$

---

## 【問題 12】線形代数（ジョルダン標準形） （総合問題セット・問題1）

### 問題
次の行列 $A$ のジョルダン標準形 $J$、および $P^{-1}AP = J$ を満たす正則行列 $P$ を求めよ。
$$A = \begin{pmatrix} 3 & 1 & 0 \\ -1 & 1 & 0 \\ 0 & 0 & 2 \end{pmatrix}$$

### 解答・解説
#### 解答
$$J = \begin{pmatrix} 2 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix}, \quad P = \begin{pmatrix} 1 & 1 & 0 \\ -1 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}$$
※ $P$ の取り方は一意ではありませんが、積 $AP = PJ$ を満たす必要があります。

#### 解説
1. **固有値の算出**
   行列 $A$ の固有多項式を計算します。
   $$\det(A - \lambda I) = \begin{vmatrix} 3-\lambda & 1 & 0 \\ -1 & 1-\lambda & 0 \\ 0 & 0 & 2-\lambda \end{vmatrix} = (2-\lambda) \begin{vmatrix} 3-\lambda & 1 \\ -1 & 1-\lambda \end{vmatrix}$$
   $$= (2-\lambda)((3-\lambda)(1-\lambda) + 1) = (2-\lambda)(\lambda^2 - 4\lambda + 4) = (2-\lambda)(\lambda-2)^2 = -(\lambda-2)^3$$
   したがって、固有値は $\lambda = 2$ （重複度 3）となります。

2. **固有空間の次元（幾何学的重複度）の確認**
   $$\operatorname{rank}(A - 2I) = \operatorname{rank} \begin{pmatrix} 1 & 1 & 0 \\ -1 & -1 & 0 \\ 0 & 0 & 0 \end{pmatrix} = 1$$
   次元定理より、固有空間の次元（固有ベクトルの自由度）は $3 - 1 = 2$ となり、ジョルダン細胞の個数は 2 個（サイズ 2 が 1 つ、サイズ 1 が 1 つ）になります。
   したがって、ジョルダン標準形は次の通りです。
   $$J = \begin{pmatrix} 2 & 1 & 0 \\ 0 & 2 & 0 \\ 0 & 0 & 2 \end{pmatrix}$$

3. **変換行列 $P = (\mathbf{p}_1, \mathbf{p}_2, \mathbf{p}_3)$ の決定**
   $AP = PJ$ より、各列ベクトルに関して以下の関係式が成り立ちます。
   * $A\mathbf{p}_1 = 2\mathbf{p}_1 \implies (A-2I)\mathbf{p}_1 = \mathbf{0}$
   * $A\mathbf{p}_2 = \mathbf{p}_1 + 2\mathbf{p}_2 \implies (A-2I)\mathbf{p}_2 = \mathbf{p}_1$
   * $A\mathbf{p}_3 = 2\mathbf{p}_3 \implies (A-2I)\mathbf{p}_3 = \mathbf{0}$

   $(A-2I)\mathbf{p}_2 = \mathbf{p}_1$ を満たすためには、$\mathbf{p}_1$ が $A-2I$ の値域に含まれている必要があります。
   $$A-2I = \begin{pmatrix} 1 & 1 & 0 \\ -1 & -1 & 0 \\ 0 & 0 & 0 \end{pmatrix} \implies \text{値域の基底は} \begin{pmatrix} 1 \\ -1 \\ 0 \end{pmatrix}$$
   よって、固有ベクトル $\mathbf{p}_1$ として $\mathbf{p}_1 = \begin{pmatrix} 1 \\ -1 \\ 0 \end{pmatrix}$ を選択します。
   このとき、$(A-2I)\mathbf{p}_2 = \mathbf{p}_1$ は以下の通りです。
   $$\begin{pmatrix} 1 & 1 & 0 \\ -1 & -1 & 0 \\ 0 & 0 & 0 \end{pmatrix} \begin{pmatrix} y_1 \\ y_2 \\ y_3 \end{pmatrix} = \begin{pmatrix} 1 \\ -1 \\ 0 \end{pmatrix} \implies y_1 + y_2 = 1$$
   ここで $y_1 = 1, y_2 = 0, y_3 = 0$ とすれば、広義固有ベクトル $\mathbf{p}_2 = \begin{pmatrix} 1 \\ 0 \\ 0 \end{pmatrix}$ が得られます。
   また、$\mathbf{p}_3$ は $\mathbf{p}_1$ と線形独立な固有ベクトル（$A-2I$ の核の元）として、$\mathbf{p}_3 = \begin{pmatrix} 0 \\ 0 \\ 1 \end{pmatrix}$ を選べます。
   以上より、正則行列 $P$ は以下になります。
   $$P = \begin{pmatrix} 1 & 1 & 0 \\ -1 & 0 & 0 \\ 0 & 0 & 1 \end{pmatrix}$$

---

## 【問題 13】線形代数（線形写像の核と像） （総合問題セット・問題2）

### 問題
線形写像 $f: \mathbb{R}^3 \to \mathbb{R}^3$ を以下のように定義する。
$$f\begin{pmatrix} x \\ y \\ z \end{pmatrix} = \begin{pmatrix} x + 2y - z \\ 2x + 3y + z \\ 3x + 5y \end{pmatrix}$$
このとき、以下を求めよ。
1. $f$ の階数（rank）
2. $f$ の像 $\operatorname{Im}(f)$ の基底の1組
3. $f$ の核 $\operatorname{Ker}(f)$ の基底の1組

### 解答・解説
#### 解答
1. $\operatorname{rank}(f) = 2$
2. $\operatorname{Im}(f)$ の基底： $\left\{ \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}, \begin{pmatrix} 2 \\ 3 \\ 5 \end{pmatrix} \right\}$
3. $\operatorname{Ker}(f)$ の基底： $\left\{ \begin{pmatrix} -5 \\ 3 \\ 1 \end{pmatrix} \right\}$

#### 解説
標準基底に対する表現行列 $A = \begin{pmatrix} 1 & 2 & -1 \\ 2 & 3 & 1 \\ 3 & 5 & 0 \end{pmatrix}$ を行基本変形します。

第1列の掃き出し：
$$\begin{pmatrix} 1 & 2 & -1 \\ 2 & 3 & 1 \\ 3 & 5 & 0 \end{pmatrix} \xrightarrow{\text{第2行}-2\times\text{第1行}, \text{第3行}-3\times\text{第1行}} \begin{pmatrix} 1 & 2 & -1 \\ 0 & -1 & 3 \\ 0 & -1 & 3 \end{pmatrix}$$

第2列の掃き出し：
$$\xrightarrow{\text{第2行}\times(-1)} \begin{pmatrix} 1 & 2 & -1 \\ 0 & 1 & -3 \\ 0 & -1 & 3 \end{pmatrix} \xrightarrow{\text{第1行}-2\times\text{第2行}, \text{第3行}+\text{第2行}} \begin{pmatrix} 1 & 0 & 5 \\ 0 & 1 & -3 \\ 0 & 0 & 0 \end{pmatrix}$$

1. **階数の決定**
   行基本変形結果の非ゼロ行数が 2 であるため、$\operatorname{rank}(f) = 2$ です。
2. **$\operatorname{Im}(f)$ の基底**
   元の行列 $A$ の第1列と第2列（ピボットがある列）が線形独立なベクトルとなり、像の基底を構成します。
   $$\operatorname{Im}(f) \text{の基底} = \left\{ \begin{pmatrix} 1 \\ 2 \\ 3 \end{pmatrix}, \begin{pmatrix} 2 \\ 3 \\ 5 \end{pmatrix} \right\}$$
3. **$\operatorname{Ker}(f)$ の基底**
   $A\mathbf{x} = \mathbf{0}$ を解きます。変形後の階段行列より、
   $$x + 5z = 0 \implies x = -5z$$
   $$y - 3z = 0 \implies y = 3z$$
   $z = t$ とおくと、$\mathbf{x} = t \begin{pmatrix} -5 \\ 3 \\ 1 \end{pmatrix}$ となるため、核の基底は以下となります。
   $$\operatorname{Ker}(f) \text{の基底} = \left\{ \begin{pmatrix} -5 \\ 3 \\ 1 \end{pmatrix} \right\}$$

---

## 【問題 14】線形代数（空間におけるねじれの位置の2直線間の最短距離） （新規追加問題）

### 問題
3次元空間内の次の 2つの直線 $L_1, L_2$ の間の最短距離 $d$ を求めよ。
$$L_1: \frac{x-1}{2} = \frac{y-2}{1} = \frac{z-3}{2}$$
$$L_2: \frac{x-2}{1} = \frac{y-3}{2} = \frac{z-5}{1}$$

### 解答・解説
#### 解答
$$\frac{\sqrt{2}}{2}$$

#### 解説
1. **方向ベクトルと通過点**
   直線 $L_1, L_2$ の方向ベクトルをそれぞれ $\mathbf{v}_1, \mathbf{v}_2$、および通過点を $A, B$ とします：
   * 直線 $L_1$：方向ベクトル $\mathbf{v}_1 = \begin{pmatrix} 2 \\ 1 \\ 2 \end{pmatrix}$、通過点 $A(1, 2, 3)$
   * 直線 $L_2$：方向ベクトル $\mathbf{v}_2 = \begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix}$、通過点 $B(2, 3, 5)$

2. **共通法線ベクトル（外積）の計算**
   2つの直線に共に直交する共通法線ベクトル $\mathbf{n} = \mathbf{v}_1 \times \mathbf{v}_2$ を求めます：
   $$\mathbf{n} = \begin{pmatrix} 2 \\ 1 \\ 2 \end{pmatrix} \times \begin{pmatrix} 1 \\ 2 \\ 1 \end{pmatrix} = \begin{pmatrix} 1\cdot 1 - 2\cdot 2 \\ 2\cdot 1 - 2\cdot 1 \\ 2\cdot 2 - 1\cdot 1 \end{pmatrix} = \begin{pmatrix} -3 \\ 0 \\ 3 \end{pmatrix}$$
   計算を単純化するため、これを $-3$ で割ったベクトル $\mathbf{n}_0 = \begin{pmatrix} 1 \\ 0 \\ -1 \end{pmatrix}$ を法線ベクトルとします。
   長さを 1 に正規化した単位共通法線ベクトル $\mathbf{e}_n$ は次のようになります：
   $$\mathbf{e}_n = \frac{\mathbf{n}_0}{\|\mathbf{n}_0\|} = \frac{1}{\sqrt{1^2 + 0^2 + (-1)^2}} \begin{pmatrix} 1 \\ 0 \\ -1 \end{pmatrix} = \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 0 \\ -1 \end{pmatrix}$$

3. **距離 $d$ の計算（射影）**
   ねじれの位置にある2直線間の最短距離 $d$ は、直線 $L_1$ 上の点 $A$ と直線 $L_2$ 上の点 $B$ を結ぶ線分ベクトル $\vec{AB}$ を、共通法線方向 $\mathbf{e}_n$ に射影した長さの絶対値に一致します。
   $$\vec{AB} = \mathbf{b} - \mathbf{a} = \begin{pmatrix} 2-1 \\ 3-2 \\ 5-3 \end{pmatrix} = \begin{pmatrix} 1 \\ 1 \\ 2 \end{pmatrix}$$
   内積を計算して距離 $d$ を求めます：
   $$d = |\vec{AB} \cdot \mathbf{e}_n| = \left| \begin{pmatrix} 1 \\ 1 \\ 2 \end{pmatrix} \cdot \frac{1}{\sqrt{2}} \begin{pmatrix} 1 \\ 0 \\ -1 \end{pmatrix} \right| = \frac{|1\cdot 1 + 1\cdot 0 + 2\cdot(-1)|}{\sqrt{2}} = \frac{|-1|}{\sqrt{2}} = \frac{1}{\sqrt{2}} = \frac{\sqrt{2}}{2}$$
   したがって、最短距離は $\frac{\sqrt{2}}{2}$ です。

---

## 【問題 15】線形代数（ケーリー・ハミルトンの定理を用いた行列の累乗計算） （新規追加問題）

### 問題
次の行列 $A$ に対し、 $A^{10}$ を求めよ。
$$A = \begin{pmatrix} 3 & 1 \\ -2 & 0 \end{pmatrix}$$

### 解答・解説
#### 解答
$$\begin{pmatrix} 2047 & 1023 \\ -2046 & -1022 \end{pmatrix}$$

#### 解説
1. **ケーリー・ハミルトンの定理の適用**
   行列 $A$ のトレース（対角和）および行列式（デターミナント）は以下の通りです：
   $$\operatorname{tr}(A) = 3 + 0 = 3$$
   $$\det(A) = 3\cdot 0 - 1\cdot(-2) = 2$$
   ケーリー・ハミルトンの定理より、 $A$ は自身の固有多項式を満たします：
   $$A^2 - 3A + 2I = O \quad \text{（ただし } I \text{ は単位行列、} O \text{ は零行列）}$$
   これより、 $A^2 = 3A - 2I$ が成り立ちます。

2. **多項式の剰余算による次数下げ**
   $A^{10}$ を計算するために、多項式 $x^{10}$ を $x^2 - 3x + 2 = (x-1)(x-2)$ で割った余りを求めます。
   余りは高々1次式なので $ax + b$ とおくことができます：
   $$x^{10} = Q(x)(x-1)(x-2) + ax + b \quad \cdots \text{(i)}$$
   式 (i) に $x = 1$ および $x = 2$ を代入して連立方程式を作成します：
   * $x = 1$ を代入： $1^{10} = a(1) + b \implies a + b = 1 \quad \cdots \text{(ii)}$
   * $x = 2$ を代入： $2^{10} = a(2) + b \implies 2a + b = 1024 \quad \cdots \text{(iii)}$
   
   式 (iii) から 式 (ii) を引くと：
   $$a = 1023$$
   これを 式 (ii) に代入すると：
   $$b = 1 - 1023 = -1022$$
   したがって、 $x^{10} \equiv 1023x - 1022 \pmod{x^2-3x+2}$ が得られます。

3. **行列の代入と最終計算**
   多項式の関係式に行列 $A$ を代入します。 $A^2 - 3A + 2I = O$ なので、次のようになります：
   $$A^{10} = 1023A - 1022I$$
   各成分を計算します：
   $$A^{10} = 1023 \begin{pmatrix} 3 & 1 \\ -2 & 0 \end{pmatrix} - 1022 \begin{pmatrix} 1 & 0 \\ 0 & 1 \end{pmatrix} = \begin{pmatrix} 3069 - 1022 & 1023 \\ -2046 & 0 - 1022 \end{pmatrix} = \begin{pmatrix} 2047 & 1023 \\ -2046 & -1022 \end{pmatrix}$$

---

## 【問題 16】線形代数（実対称行列の直交対角化） （新規追加問題）

### 問題
次の実対称行列 $A$ に対し、 $A$ を直交対角化する直交行列 $P$ と、対角化された対角行列 $D = P^T A P$ を一組求めよ。
$$A = egin{pmatrix} 2 & 1 & 1 \ 1 & 2 & 1 \ 1 & 1 & 2 end{pmatrix}$$

### 解答・解説
#### 解答
$$P = egin{pmatrix} 1/sqrt{3} & 1/sqrt{2} & 1/sqrt{6} \ 1/sqrt{3} & -1/sqrt{2} & 1/sqrt{6} \ 1/sqrt{3} & 0 & -2/sqrt{6} end{pmatrix}, quad D = egin{pmatrix} 4 & 0 & 0 \ 0 & 1 & 0 \ 0 & 0 & 1 end{pmatrix}$$

#### 解説
1. **固有値の算出**
   固有多項式 $det(A - lambda I) = 0$ を解いて固有値を求めます。
   $$det(A - lambda I) = egin{vmatrix} 2-lambda & 1 & 1 \ 1 & 2-lambda & 1 \ 1 & 1 & 2-lambda end{vmatrix} = 0$$
   第1行に第2行、第3行を加えると、共通因数 $(4-lambda)$ が現れます：
   $$egin{vmatrix} 4-lambda & 4-lambda & 4-lambda \ 1 & 2-lambda & 1 \ 1 & 1 & 2-lambda end{vmatrix} = (4-lambda) egin{vmatrix} 1 & 1 & 1 \ 1 & 2-lambda & 1 \ 1 & 1 & 2-lambda end{vmatrix} = 0$$
   第1行の 1倍を第2行および第3行から引きます：
   $$(4-lambda) egin{vmatrix} 1 & 1 & 1 \ 0 & 1-lambda & 0 \ 0 & 0 & 1-lambda end{vmatrix} = (4-lambda)(1-lambda)^2 = 0$$
   これより、固有値は $lambda = 4$ （重複度1）および $lambda = 1$ （重複度2）です。

2. **固有ベクトルの決定と正規直交化**
   * **固有値 $lambda = 4$ に対して：**
     $$(A - 4I)mathbf{x} = mathbf{0} implies egin{pmatrix} -2 & 1 & 1 \ 1 & -2 & 1 \ 1 & 1 & -2 end{pmatrix} egin{pmatrix} x \ y \ z end{pmatrix} = egin{pmatrix} 0 \ 0 \ 0 end{pmatrix}$$
     これより固有ベクトル $mathbf{u}_1 = egin{pmatrix} 1 \ 1 \ 1 end{pmatrix}$ を得ます。長さを 1 に正規化して：
     $$mathbf{p}_1 = rac{1}{sqrt{3}} egin{pmatrix} 1 \ 1 \ 1 end{pmatrix}$$
   * **固有値 $lambda = 1$ に対して：**
     $$(A - I)mathbf{x} = mathbf{0} implies egin{pmatrix} 1 & 1 & 1 \ 1 & 1 & 1 \ 1 & 1 & 1 end{pmatrix} egin{pmatrix} x \ y \ z end{pmatrix} = egin{pmatrix} 0 \ 0 \ 0 end{pmatrix}$$
     これは平面 $x + y + z = 0$ を表します。この平面上で互いに直交する2つの単位ベクトルを求めます。
     まず1次独立な解の1つとして $mathbf{u}_2 = egin{pmatrix} 1 \ -1 \ 0 end{pmatrix}$ を選び、正規化して：
     $$mathbf{p}_2 = rac{1}{sqrt{2}} egin{pmatrix} 1 \ -1 \ 0 end{pmatrix}$$
     次に、 $mathbf{p}_1$ と $mathbf{p}_2$ の両方に直交する単位ベクトル $mathbf{p}_3$ を外積または直交条件から求めます。 $mathbf{p}_3 = mathbf{p}_1 	imes mathbf{p}_2$ より：
     $$mathbf{p}_3 = rac{1}{sqrt{6}} egin{pmatrix} 1 \ 1 \ -2 end{pmatrix}$$

3. **直交行列 $P$ と対角行列 $D$ の構成**
   これら $mathbf{p}_1, mathbf{p}_2, mathbf{p}_3$ を列ベクトルとする行列 $P$ は直交行列になり、 $P^T A P = D$ が成立します。
   $$P = egin{pmatrix} 1/sqrt{3} & 1/sqrt{2} & 1/sqrt{6} \ 1/sqrt{3} & -1/sqrt{2} & 1/sqrt{6} \ 1/sqrt{3} & 0 & -2/sqrt{6} end{pmatrix}, quad D = egin{pmatrix} 4 & 0 & 0 \ 0 & 1 & 0 \ 0 & 0 & 1 end{pmatrix}$$

---

## 【問題 17】線形代数（エルミート行列の対角化） （新規追加問題）

### 問題
次の複素エルミート行列 $A$ に対し、 $A$ を対角化するユニタリ行列 $U$ と、対角化された対角行列 $D = U^{\dagger} A U$ を一組求めよ。
$$A = \begin{pmatrix} 3 & 2i \\ -2i & 0 \end{pmatrix}$$

### 解答・解説
#### 解答
$$U = \frac{1}{\sqrt{5}} \begin{pmatrix} 2i & 1 \\ 1 & 2i \end{pmatrix}, \quad D = \begin{pmatrix} 4 & 0 \\ 0 & -1 \end{pmatrix}$$

#### 解説
1. **固有値の算出**
   固有多項式 $\det(A - \lambda I) = 0$ を解いて固有値を求めます。
   $$\det(A - \lambda I) = \begin{vmatrix} 3-\lambda & 2i \\ -2i & -\lambda \end{vmatrix} = (3-\lambda)(-\lambda) - (2i)(-2i) = \lambda^2 - 3\lambda - 4 = 0$$
   $$(\lambda - 4)(\lambda + 1) = 0 \implies \lambda = 4, -1$$
   よって、エルミート行列 $A$ の固有値は実数 $\lambda_1 = 4$ および $\lambda_2 = -1$ です。（エルミート行列の固有値は常に実数になります。）

2. **固有ベクトルの決定と正規化**
   * **固有値 $\lambda_1 = 4$ に対する固有ベクトル $\mathbf{u}_1$：**
     $$(A - 4I)\mathbf{x} = \mathbf{0} \implies \begin{pmatrix} -1 & 2i \\ -2i & -4 \end{pmatrix} \begin{pmatrix} z_1 \\ z_2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}$$
     これより、 $-z_1 + 2i z_2 = 0 \implies z_1 = 2i z_2$ を得ます。
     $z_2 = 1$ と選ぶと、固有ベクトルは $\mathbf{v}_1 = \begin{pmatrix} 2i \\ 1 \end{pmatrix}$ となります。
     そのノルムは $\|\mathbf{v}_1\| = \sqrt{|2i|^2 + |1|^2} = \sqrt{4 + 1} = \sqrt{5}$ です。
     正規化した単位固有ベクトルは次のようになります：
     $$\mathbf{u}_1 = \frac{1}{\sqrt{5}} \begin{pmatrix} 2i \\ 1 \end{pmatrix}$$
   * **固有値 $\lambda_2 = -1$ に対する固有ベクトル $\mathbf{u}_2$：**
     $$(A + I)\mathbf{x} = \mathbf{0} \implies \begin{pmatrix} 4 & 2i \\ -2i & 1 \end{pmatrix} \begin{pmatrix} z_1 \\ z_2 \end{pmatrix} = \begin{pmatrix} 0 \\ 0 \end{pmatrix}$$
     これより、 $4z_1 + 2i z_2 = 0 \implies z_2 = 2i z_1$ を得ます。
     $z_1 = 1$ と選ぶと、固有ベクトルは $\mathbf{v}_2 = \begin{pmatrix} 1 \\ 2i \end{pmatrix}$ となります。
     そのノルムは $\|\mathbf{v}_2\| = \sqrt{|1|^2 + |2i|^2} = \sqrt{5}$ です。
     正規化した単位固有ベクトルは次のようになります：
     $$\mathbf{u}_2 = \frac{1}{\sqrt{5}} \begin{pmatrix} 1 \\ 2i \end{pmatrix}$$

3. **ユニタリ行列 $U$ と対角行列 $D$ の構成**
   固有ベクトル $\mathbf{u}_1$ と $\mathbf{u}_2$ の内積（エルミート内積）を確認します：
   $$\mathbf{u}_1^{\dagger} \mathbf{u}_2 = \frac{1}{5} \begin{pmatrix} -2i & 1 \end{pmatrix} \begin{pmatrix} 1 \\ 2i \end{pmatrix} = \frac{1}{5} (-2i + 2i) = 0$$
   互いに直交しているため、これらを列ベクトルとする行列 $U$ はユニタリ行列（ $U^{\dagger} U = I$ ）となります。
   $$U = \frac{1}{\sqrt{5}} \begin{pmatrix} 2i & 1 \\ 1 & 2i \end{pmatrix}, \quad D = U^{\dagger} A U = \begin{pmatrix} 4 & 0 \\ 0 & -1 \end{pmatrix}$$

---


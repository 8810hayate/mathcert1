# Walkthrough - Appending New SUKEN 1st Grade Topics

We have successfully expanded the Mathematics Certification Test Grade 1 (数検1級) study guide with 6 new advanced topics, bringing the total number of problems to **23**.

## Changes Made

We updated [suken_1_ultimate_guide.md](file:///C:/Users/kazuo-suyama/.gemini/antigravity/brain/1ee1630b-7539-4f2d-ac0f-546be883fc58/suken_1_ultimate_guide.md) to add the following:

1. **Table of Contents & Meta Details**
   * Updated the total question count from 17 to 23.
   * Registered all 6 new problems in the Table of Contents.

2. **I. 線形代数 (Linear Algebra)**
   * **Added 【問題1-4】 2次形式と正定値性（シルベスターの基準）**
     * Solved the parameter range of $a$ for which $q(x,y,z) = x^2 + 2axy + y^2 + 2ayz + z^2$ is positive definite.
     * Demonstrated the application of Sylvester's Criterion checking the positivity of principal minors ($D_1 > 0$, $D_2 > 0$, $D_3 > 0$).

3. **II. 微分積分学 (Calculus)**
   * **Added 【問題2-4】 フーリエ級数展開と無限級数の和（バーゼル問題）**
     * Calculated the Fourier series expansion of $f(x) = x^2$ on $[-\pi, \pi]$ using integration by parts.
     * Substituted $x = \pi$ to prove the famous Euler identity: $\sum_{n=1}^{\infty} \frac{1}{n^2} = \frac{\pi^2}{6}$.

4. **III. 微分方程式 (Differential Equations)**
   * **Added 【問題3-3】 ベルヌーイの微分方程式**
     * Solved the non-linear first-order differential equation: $y' + \frac{y}{x} = x y^2$.
     * Demonstrated reducing it to a linear ODE using the substitution $u = y^{-1}$ and solving it via an integrating factor.

5. **IV. 複素解析 (Complex Analysis)**
   * **Added 【問題4-3】 複素関数のローラン展開**
     * Expanded $f(z) = \frac{1}{z(z-2)}$ in Laurent series in the regions (i) $0 < |z| < 2$ and (ii) $|z| > 2$.
     * Illustrated the use of geometric series convergence criteria ($|w| < 1$).

6. **VII. 代数学・整数論 (Algebra & Number Theory)**
   * **Added 【問題7-3】 多項式環の剰余環と体の同型**
     * Proved the ring isomorphism: $\mathbb{R}[x]/(x^2+1) \cong \mathbb{C}$.
     * Utilized the First Isomorphism Theorem for rings by showing that the evaluation homomorphism $\phi(p(x)) = p(i)$ is surjective and has $\operatorname{Ker}(\phi) = (x^2+1)$.

7. **VIII. 確率・統計 (Probability & Statistics)**
   * **Added 【問題8-4】 2次元連続型確率変数の同時分布・周辺分布・共分散**
     * Analyzed the joint PDF $f(x,y) = c(x+y)$ on the unit square.
     * Determined $c = 1$, derived marginal densities, proved that variables $X$ and $Y$ are dependent, and calculated the covariance $\operatorname{Cov}(X,Y) = -\frac{1}{144}$.

## Verification Result

All 6 problems were solved and cross-checked for absolute mathematical correctness. The Markdown structure and LaTeX mathematical notation have been verified to render properly.

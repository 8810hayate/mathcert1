# Implementation Plan - Expanding the SUKEN Grade 1 Ultimate Guide

This plan outlines the additions of 6 critical advanced math topics to the ultimate study guide [suken_1_ultimate_guide.md](file:///C:/Users/kazuo-suyama/.gemini/antigravity/brain/1ee1630b-7539-4f2d-ac0f-546be883fc58/suken_1_ultimate_guide.md) to ensure complete coverage of the Mathematics Certification Test Grade 1 (数検1級) syllabus.

## Proposed Changes

We will modify [suken_1_ultimate_guide.md](file:///C:/Users/kazuo-suyama/.gemini/antigravity/brain/1ee1630b-7539-4f2d-ac0f-546be883fc58/suken_1_ultimate_guide.md) to append 6 new problems and detailed explanations under their respective existing fields. We will also update the Table of Contents at the beginning of the file.

### Summary of New Problems

1. **线形代数 (Linear Algebra)**
   * **【問題1-4】2次形式と正定値性（シルベスターの基準）**
     * *Problem:* Find the parameter range of $a$ for which the quadratic form $q(x,y,z) = x^2 + 2axy + y^2 + 2ayz + z^2$ is positive definite.
     * *Purpose:* To cover Sylvester's criterion on principal minors for positive definiteness.

2. **微分積分学 (Calculus)**
   * **【問題2-4】フーリエ級数展開と無限級数の和 ($\zeta(2) = \pi^2/6$)**
     * *Problem:* Expand $f(x) = x^2$ on $[-\pi, \pi]$ as a Fourier series and evaluate the Basel problem sum $\sum_{n=1}^{\infty} \frac{1}{n^2}$.
     * *Purpose:* To cover Fourier series expansion, periodic boundary extensions, and infinite series evaluation.

3. **微分方程式 (Differential Equations)**
   * **【問題3-3】ベルヌーイの微分方程式**
     * *Problem:* Solve the non-linear first-order ODE $y' + \frac{y}{x} = x y^2 \quad (x > 0)$.
     * *Purpose:* To cover standard non-linear ODE techniques using substitutions ($u = y^{1-n}$).

4. **複素解析 (Complex Analysis)**
   * **【問題4-3】複素関数のローラン展開**
     * *Problem:* Find the Laurent series of $f(z) = \frac{1}{z(z-2)}$ in regions (i) $0 < |z| < 2$ and (ii) $|z| > 2$.
     * *Purpose:* To cover Laurent expansions in different annular domains around a singularity.

5. **代数学・整数論 (Algebra & Number Theory)**
   * **【問題7-3】多項式環の剰余環と体の同型（第一同型定理）**
     * *Problem:* Prove that the quotient ring $\mathbb{R}[x]/(x^2+1)$ is isomorphic to the complex field $\mathbb{C}$.
     * *Purpose:* To cover ring homomorphisms, ideal definitions, quotient rings, and the First Isomorphism Theorem for rings.

6. **確率・統計 (Probability & Statistics)**
   * **【問題8-4】2次元連続型確率変数の同時分布・周辺分布・共分散**
     * *Problem:* Given joint PDF $f(x,y) = c(x+y)$ on $[0, 1] \times [0, 1]$, (i) find $c$, (ii) find marginals, (iii) check independence, (iv) find covariance.
     * *Purpose:* To cover joint densities, marginal integrals, variable independence, and expectations/covariance calculations.

---

## Verification Plan

### Manual Verification
1. **Mathematical Check:** Individually recalculate and verify all calculations, coefficients, bounds, and algebraic steps for all 6 new problems to ensure 100% mathematical accuracy.
2. **Markdown Rendering Check:** Check the formatting of LaTeX expressions and Markdown headings inside the updated file.

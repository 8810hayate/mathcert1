# Implementation Plan - Expanding Category-wise Mock Problems to 116

This plan outlines the approach to adding **4 new critical mathematical problem patterns** to the Mathematics Certification Test Grade 1 (数検1級) category-wise mock exams database, raising the total problem count from 112 to **116**. These additions will target advanced college-level calculations that frequently appear in the syllabus.

## User Review Required

> [!NOTE]
> We will append 4 new custom problems to `EXTRA_PROBLEMS` in the parser script, bringing the total to **116** problems. All categorized markdown files will be automatically regenerated.

### 4 New Proposed Problems

1. **微分積分学 (Calculus)**: **積分記号下の微分 (Leibniz's Rule)**
   - *Problem:* Evaluate the parametric improper integral $I(a) = \int_0^\infty \frac{e^{-x} \sin(ax)}{x} \,dx \quad (a \in \mathbb{R})$ using differentiation under the integral sign.
   - *Target:* Advanced techniques in improper integration.

2. **線形代数 (Linear Algebra)**: **複素内積空間とエルミート行列の対角化**
   - *Problem:* Find the eigenvalues and orthonormal eigenvectors of the Hermitian matrix $A = \begin{pmatrix} 3 & 2i \\ -2i & 0 \end{pmatrix}$, and construct a unitary matrix $U$ that diagonalizes it.
   - *Target:* Orthonormalization and diagonalization over the complex field.

3. **代数学・整数論 (Algebra & Number Theory)**: **代数的数の最小多項式と拡大次数**
   - *Problem:* Find the minimal polynomial of $\alpha = \sqrt{2} + \sqrt{3}$ over $\mathbb{Q}$, and determine the degree of the field extension $[\mathbb{Q}(\sqrt{2}, \sqrt{3}) : \mathbb{Q}]$.
   - *Target:* Field theory and algebraic numbers.

4. **確率・統計 (Probability & Statistics)**: **条件付き期待値と条件付き分散**
   - *Problem:* For the joint density $f(x, y) = 2$ on $0 < y < x < 1$, find the conditional density $f_{X|Y}(x \mid y)$, the conditional expectation $E[X \mid Y = y]$, and the conditional variance $\operatorname{Var}(X \mid Y = y)$.
   - *Target:* Conditional probability distributions and expectations.

---

## Proposed Changes

### 1. Update Parser Script `scratch/parse_mocks.js`
- **[MODIFY]** [parse_mocks.js](file:///C:/Users/kazuo-suyama/.gemini/antigravity/brain/58520328-496d-4add-9d61-ac6c000109b3/scratch/parse_mocks.js)
  - Append the 4 new problems to the end of the `EXTRA_PROBLEMS` array.

### 2. Update Validator Script `scratch/verify_mocks.js`
- **[MODIFY]** [verify_mocks.js](file:///C:/Users/kazuo-suyama/.gemini/antigravity/brain/58520328-496d-4add-9d61-ac6c000109b3/scratch/verify_mocks.js)
  - Update the expected total problems assertion from 112 to **116**.

---

## Verification Plan

### Automated Verification
Run the parser and validator using Node.js:
1. Generate the files: `node C:\Users\kazuo-suyama\.gemini\antigravity\brain\58520328-496d-4add-9d61-ac6c000109b3\scratch\parse_mocks.js`
2. Verify correctness: `node C:\Users\kazuo-suyama\.gemini\antigravity\brain\58520328-496d-4add-9d61-ac6c000109b3\scratch\verify_mocks.js`
   - Checks total count is exactly 116.
   - Verifies LaTeX `$$` markers are correctly paired and balanced.
3. Regenerate the titles list:
   - Run the list generator script to refresh `titles.txt`.

### Manual Verification
1. Inspect the updated markdown files in [mock_by_category](file:///c:/Projects/mathcert1/mock_by_category) to ensure readability and formatting.

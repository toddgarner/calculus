# Section 5.5 Numerical Integration

## The Big Idea

**The core problem:** Sometimes you can't find an antiderivative. Functions like $e^{-x^2}$, $\sin(x^3)$, and $\frac{\sin x}{x}$ have no elementary antiderivatives—the [Fundamental Theorem of Calculus](Section%205.4%20The%20Fundamental%20Theorem%20of%20Calculus.md) can't help you directly.

**The solution:** Approximate the definite integral numerically by breaking the interval into pieces and using geometric shapes to estimate the area.

**Two situations requiring numerical integration:**
1. When the antiderivative **cannot be expressed with elementary functions**
2. When you **don't know the function itself**—only data points (like speedometer readings)

---

## Key Formulas

### Setup (Used by All Methods)
For $\int_a^b f(x)\,dx$ with $n$ subintervals:

$$\Delta x = \frac{b-a}{n}$$

Endpoints: $x_1 = a$, $x_2 = a + \Delta x$, ..., $x_{n+1} = b$

---

### Left Hand Rule

$$\int_a^b f(x)\,dx \approx \Delta x \left[ f(x_1) + f(x_2) + \cdots + f(x_n) \right]$$

- Approximates $f(x)$ with **constant functions** (rectangles)
- Rarely used in practice—Trapezoidal Rule is better with same effort

---

### Right Hand Rule

$$\int_a^b f(x)\,dx \approx \Delta x \left[ f(x_2) + f(x_3) + \cdots + f(x_{n+1}) \right]$$

- Also uses **constant functions** (rectangles)
- Rarely used in practice

---

### Trapezoidal Rule

$$\int_a^b f(x)\,dx \approx \frac{\Delta x}{2} \left[ f(x_1) + 2f(x_2) + 2f(x_3) + \cdots + 2f(x_n) + f(x_{n+1}) \right]$$

- Approximates $f(x)$ with **linear functions** (trapezoids)
- Equals the **average of Left and Right Hand Rules**
- Coefficient pattern: **1, 2, 2, 2, ..., 2, 1**
- **n can be any positive integer** (no restriction)

---

### Simpson's Rule

$$\int_a^b f(x)\,dx \approx \frac{\Delta x}{3} \left[ f(x_1) + 4f(x_2) + 2f(x_3) + 4f(x_4) + \cdots + 4f(x_n) + f(x_{n+1}) \right]$$

- Approximates $f(x)$ with **quadratic functions** (parabolas)
- Requires $n$ to be **even**
- Coefficient pattern: **1, 4, 2, 4, 2, ..., 4, 1**
- **Exact for polynomials of degree ≤ 3**

---

### Error Bounds

**Trapezoidal Rule Error:**
$$E_T \leq \frac{(b-a)^3}{12n^2} M \quad \text{where } M = \max|f''(x)| \text{ on } [a,b]$$

**Simpson's Rule Error:**
$$E_S \leq \frac{(b-a)^5}{180n^4} M \quad \text{where } M = \max|f^{(4)}(x)| \text{ on } [a,b]$$

> [!tip] Key Observations
> - Larger intervals → larger error
> - More subintervals (larger $n$) → smaller error
> - Simpson's error depends on 4th derivative → **exact for cubics** (4th derivative = 0)

---

## Method Comparison

| Method | Approximates f with | Coefficient Pattern | Notes |
|--------|---------------------|---------------------|-------|
| Left/Right Hand | Constants | All 1's | Obsolete |
| Trapezoidal | Linear | 1, 2, 2, ..., 2, 1 | Average of L/R |
| Simpson's | Quadratic | 1, 4, 2, 4, ..., 4, 1 | n must be even |

---

## Worked Problems

### Problem 1
> **T/F: Simpson's Rule is a method of approximating antiderivatives.**

**Answer: FALSE**

Simpson's Rule approximates **definite integrals** (specific numerical values), not antiderivatives (functions). You get a number, not a function.

---

### Problem 2
> **What are the two basic situations where approximating the value of a definite integral is necessary?**

**Answer:**
1. When the antiderivative **cannot be expressed with elementary functions** (like $\int e^{-x^2} dx$)
2. When you **don't know the function itself**—you only have data points

---

### Problem 3
> **Why are the Left and Right Hand Rules rarely used?**

**Answer:** The Trapezoidal Rule is just as easy to compute and gives better results (it's the average of Left and Right). No practical reason to use inferior methods.

---

### Problem 4
> **Simpson's Rule is based on approximating portions of a function with what type of function?**

**Answer: Quadratic functions (parabolas)**

Simpson's Rule fits a parabola through every three consecutive points.

---

### Problem 9
> $$\int_0^3 (x^3 + 2x^2 - 5x + 7)\, dx \text{ with } n = 4$$

**Setup:** Using standard setup
- $a = 0$, $b = 3$, $n = 4$
- $\Delta x = \frac{3-0}{4} = 0.75$
- Endpoints: $x_1 = 0$, $x_2 = 0.75$, $x_3 = 1.5$, $x_4 = 2.25$, $x_5 = 3$

Let $f(x) = x^3 + 2x^2 - 5x + 7$

| $x_i$ | $f(x_i)$ |
| ----- | -------- |
| 0     | 7        |
| 0.75  | 4.797    |
| 1.5   | 7.375    |
| 2.25  | 17.266   |
| 3     | 37       |

**(a) Trapezoidal Rule:** (pattern: 1, 2, 2, 2, 1)
$$T_4 = \frac{0.75}{2}[7 + 2(4.797) + 2(7.375) + 2(17.266) + 37]$$
$$= 0.375[7 + 9.594 + 14.75 + 34.532 + 37] = 0.375(102.876) = \boxed{38.58}$$

**(b) Simpson's Rule:** (pattern: 1, 4, 2, 4, 1)
$$S_4 = \frac{0.75}{3}[7 + 4(4.797) + 2(7.375) + 4(17.266) + 37]$$
$$= 0.25[7 + 19.188 + 14.75 + 69.064 + 37] = 0.25(147) = \boxed{36.75}$$

**(c) Exact value:**
$$\int_0^3 (x^3 + 2x^2 - 5x + 7)\, dx = \left[\frac{x^4}{4} + \frac{2x^3}{3} - \frac{5x^2}{2} + 7x\right]_0^3$$
$$= 20.25 + 18 - 22.5 + 21 = \boxed{36.75}$$

> [!success] Simpson's Rule is Exact!
> Since $f(x)$ is a cubic polynomial (degree 3), Simpson's Rule gives the **exact answer**. The 4th derivative is zero, so the error bound is zero.

---

### Problem 11
> $$\int_0^{2\pi} \cos x\, dx \text{ with } n = 4$$

**Setup:** $\Delta x = \frac{2\pi - 0}{4} = \frac{\pi}{2}$

| $x_i$ | $\cos(x_i)$ |
|-------|-------------|
| 0 | 1 |
| $\pi/2$ | 0 |
| $\pi$ | -1 |
| $3\pi/2$ | 0 |
| $2\pi$ | 1 |

**(a) Trapezoidal Rule:**
$$T_4 = \frac{\pi/2}{2}[1 + 2(0) + 2(-1) + 2(0) + 1] = \frac{\pi}{4}[1 - 2 + 1] = \boxed{0}$$

**(b) Simpson's Rule:**
$$S_4 = \frac{\pi/2}{3}[1 + 4(0) + 2(-1) + 4(0) + 1] = \frac{\pi}{6}[1 - 2 + 1] = \boxed{0}$$

**(c) Exact value:**
$$\int_0^{2\pi} \cos x\, dx = [\sin x]_0^{2\pi} = 0 - 0 = \boxed{0}$$

All methods give the exact answer due to the symmetry of cosine over a full period.

---

### Problem 13
> $$\int_0^1 \cos(x^2)\, dx \text{ with } n = 6$$

**Setup:** $\Delta x = \frac{1-0}{6} = \frac{1}{6} \approx 0.1667$

| $x_i$ | $x_i^2$ | $\cos(x_i^2)$ |
| ----- | ------- | ------------- |
| 0     | 0       | 1             |
| 1/6   | 0.0278  | 0.9996        |
| 1/3   | 0.1111  | 0.9938        |
| 1/2   | 0.25    | 0.9689        |
| 2/3   | 0.4444  | 0.9022        |
| 5/6   | 0.6944  | 0.7692        |
| 1     | 1       | 0.5403        |

**Trapezoidal Rule:** (pattern: 1, 2, 2, 2, 2, 2, 1)
$$T_6 = \frac{1/6}{2}[1 + 2(0.9996 + 0.9938 + 0.9689 + 0.9022 + 0.7692) + 0.5403]$$
$$= \frac{1}{12}[1 + 2(4.6337) + 0.5403] = \frac{1}{12}(10.8077) \approx \boxed{0.9006}$$

**Simpson's Rule:** (pattern: 1, 4, 2, 4, 2, 4, 1)
$$S_6 = \frac{1/6}{3}[1 + 4(0.9996) + 2(0.9938) + 4(0.9689) + 2(0.9022) + 4(0.7692) + 0.5403]$$
$$= \frac{1}{18}[1 + 3.9984 + 1.9876 + 3.8756 + 1.8044 + 3.0768 + 0.5403]$$
$$= \frac{1}{18}(16.2831) \approx \boxed{0.9046}$$

---

### Problem 15
> $$\int_0^5 \sqrt{x^2 + 1}\, dx \text{ with } n = 6$$

**Setup:** $\Delta x = \frac{5-0}{6} = \frac{5}{6} \approx 0.8333$

| $x_i$ | $\sqrt{x_i^2 + 1}$ |
| ----- | ------------------ |
| 0     | 1                  |
| 5/6   | 1.3017             |
| 5/3   | 1.9437             |
| 5/2   | 2.6926             |
| 10/3  | 3.4801             |
| 25/6  | 4.2850             |
| 5     | 5.0990             |

**Trapezoidal Rule:**
$$T_6 = \frac{5/6}{2}[1 + 2(1.3017 + 1.9437 + 2.6926 + 3.4801 + 4.2850) + 5.0990]$$
$$= \frac{5}{12}[1 + 2(13.7031) + 5.0990] = \frac{5}{12}(33.5052) \approx \boxed{13.96}$$

**Simpson's Rule:**
$$S_6 = \frac{5/6}{3}[1 + 4(1.3017) + 2(1.9437) + 4(2.6926) + 2(3.4801) + 4(4.2850) + 5.0990]$$
$$= \frac{5}{18}[1 + 5.2068 + 3.8874 + 10.7704 + 6.9602 + 17.14 + 5.0990]$$
$$= \frac{5}{18}(50.0638) \approx \boxed{13.91}$$

---

### Problem 22
> **Find n such that error < 0.0001 for** $\int_1^4 \frac{1}{\sqrt{x}}\, dx$

Let $f(x) = x^{-1/2}$

Using Error Bounds:

**(a) Trapezoidal Rule:** Need $f''(x)$ and $M = \max|f''(x)|$
- $f'(x) = -\frac{1}{2}x^{-3/2}$
- $f''(x) = \frac{3}{4}x^{-5/2}$
- On $[1, 4]$, max at $x = 1$: $M = \frac{3}{4}$

Apply Trapezoidal error formula:
$$E_T \leq \frac{(4-1)^3}{12n^2} \cdot \frac{3}{4} = \frac{27}{12n^2} \cdot \frac{3}{4} = \frac{27}{16n^2}$$

Set $\frac{27}{16n^2} < 0.0001$:
$$n^2 > \frac{27}{16 \cdot 0.0001} = 16875 \implies n > 129.9$$

$$\boxed{n \geq 130}$$

**(b) Simpson's Rule:** Need $f^{(4)}(x)$ and $M = \max|f^{(4)}(x)|$
- $f'''(x) = -\frac{15}{8}x^{-7/2}$
- $f^{(4)}(x) = \frac{105}{16}x^{-9/2}$
- On $[1, 4]$, max at $x = 1$: $M = \frac{105}{16}$

Apply Simpson's error formula:
$$E_S \leq \frac{(4-1)^5}{180n^4} \cdot \frac{105}{16} = \frac{243}{180n^4} \cdot \frac{105}{16} = \frac{25515}{2880n^4}$$

Set $\frac{25515}{2880n^4} < 0.0001$:
$$n^4 > \frac{25515}{0.288} = 88593.75 \implies n > 17.25$$

$$\boxed{n \geq 18}$$ (must be even for Simpson's Rule)

> [!note] Efficiency Comparison
> Trapezoidal needs 130 subintervals, Simpson's needs only 18 for the same accuracy!

---

### Problem 24
> **Find n such that error < 0.0001 for** $\int_0^5 x^4\, dx$

Let $f(x) = x^4$

Using Error Bounds:

**(a) Trapezoidal Rule:**
- $f''(x) = 12x^2$
- On $[0,5]$, max at $x = 5$: $M = 12(25) = 300$

Apply Trapezoidal error formula:
$$E_T \leq \frac{(5-0)^3}{12n^2} \cdot 300 = \frac{125 \cdot 300}{12n^2} = \frac{3125}{n^2}$$

Set $\frac{3125}{n^2} < 0.0001$:
$$n^2 > 31250000 \implies n > 5590$$

$$\boxed{n \geq 5591}$$

**(b) Simpson's Rule:**
- $f^{(4)}(x) = 24$ (constant!)
- $M = 24$

Apply Simpson's error formula:
$$E_S \leq \frac{(5-0)^5}{180n^4} \cdot 24 = \frac{3125 \cdot 24}{180n^4} = \frac{1250}{3n^4}$$

Set $\frac{1250}{3n^4} < 0.0001$:
$$n^4 > \frac{1250}{0.0003} = 4166666.67 \implies n > 45.2$$

$$\boxed{n \geq 46}$$ (must be even)

> [!note] Dramatic Difference
> Trapezoidal needs ~5591 subintervals while Simpson's needs only 46. This shows why Simpson's Rule is preferred for smooth functions.

---

## Quick Reference: Coefficient Patterns

| n | Trapezoidal (÷2) | Simpson's (÷3) |
|---|------------------|----------------|
| 2 | 1, 2, 1 | 1, 4, 1 |
| 4 | 1, 2, 2, 2, 1 | 1, 4, 2, 4, 1 |
| 6 | 1, 2, 2, 2, 2, 2, 1 | 1, 4, 2, 4, 2, 4, 1 |

---

## Related Notes
- [Section 5.3 Riemann Sums](Section%205.3%20Riemann%20Sums.md) - Foundation for these methods
- [Section 5.4 The Fundamental Theorem of Calculus](Section%205.4%20The%20Fundamental%20Theorem%20of%20Calculus.md) - When you CAN find antiderivatives

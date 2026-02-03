# Section 5.4 The Fundamental Theorem of Calculus

## Big Picture

The Fundamental Theorem of Calculus (FTC) bridges differentiation and integration: **Part 1** reveals that differentiation and integration are inverse operations, while **Part 2** provides a practical method to evaluate definite integrals using antiderivatives instead of computing limits of Riemann sums.

---

## Key Terms and Formulas

### Integral as a Function

When we let the upper bound of a definite integral vary, we create a function:

$$F(x) = \int_a^x f(t) \, dt$$

This computes the **area under $f$** on the interval $[a, x]$.

![Figure 5.4.1 - Area Function F(x)](images/Figure%205.4.1%20-%20Area%20Function%20F(x).png)

**Key Property:** $F(a) = \int_a^a f(t) \, dt = 0$

---

### Theorem 5.4.1 — The Fundamental Theorem of Calculus, Part 1

> [!theorem] FTC Part 1
> Let $f$ be continuous on $[a, b]$ and let $F(x) = \int_a^x f(t) \, dt$.
>
> Then $F$ is a differentiable function on $(a, b)$, and
> $$F'(x) = f(x)$$

**In other notation:**
$$\frac{d}{dx}\left[\int_a^x f(t) \, dt\right] = f(x)$$

> [!tip] What This Means
> The derivative of an integral function **returns the original integrand** evaluated at the upper limit. This proves that $F(x)$ is an antiderivative of $f(x)$.

---

### Theorem 5.4.2 — The Fundamental Theorem of Calculus, Part 2

> [!theorem] FTC Part 2
> Let $f$ be continuous on $[a, b]$ and let $F$ be **any** antiderivative of $f$. Then
> $$\int_a^b f(x) \, dx = F(b) - F(a)$$

**Derivation Sketch:**
$$\int_a^b f(t) \, dt = \int_a^c f(t) \, dt + \int_c^b f(t) \, dt = -F(a) + F(b) = F(b) - F(a)$$

---

### Evaluation Notation

| Notation | Meaning |
|----------|---------|
| $F(x) \Big\|_a^b$ | $F(b) - F(a)$ |
| $\left[ F(x) \right]_a^b$ | $F(b) - F(a)$ |

> [!tip] The Constant $C$ Cancels
> Any antiderivative works because:
> $$[F(b) + C] - [F(a) + C] = F(b) - F(a)$$
> So we typically choose $C = 0$ for simplicity.

---

### FTC Part 1 with Chain Rule

When the upper limit is a function $g(x)$ instead of just $x$:

$$\frac{d}{dx}\left[\int_a^{g(x)} f(t) \, dt\right] = f(g(x)) \cdot g'(x)$$

| Upper Limit | Derivative Formula |
|-------------|-------------------|
| $x$ | $f(x)$ |
| $g(x)$ | $f(g(x)) \cdot g'(x)$ |
| $a$ (constant) in upper, $h(x)$ in lower | $-f(h(x)) \cdot h'(x)$ |

> [!tip] Reversed Bounds
> If the variable is in the **lower** bound:
> $$\int_{g(x)}^a f(t) \, dt = -\int_a^{g(x)} f(t) \, dt$$
> Then differentiate with a negative sign.

> [!tip] Both Bounds Have $x$
> If both limits are functions of $x$, split using a constant:
> $$\int_{h(x)}^{g(x)} f(t)\,dt = \int_0^{g(x)} f(t)\,dt - \int_0^{h(x)} f(t)\,dt$$
> Then differentiate each piece separately.

---

### Theorem 5.4.3 — Area Between Curves

> [!theorem] Area Between Curves
> Let $f(x)$ and $g(x)$ be continuous on $[a, b]$ where $f(x) \geq g(x)$ for all $x$ in $[a, b]$.
>
> The area of the region bounded by $y = f(x)$, $y = g(x)$, $x = a$, and $x = b$ is:
> $$\text{Area} = \int_a^b \left[ f(x) - g(x) \right] dx$$

![Figure 5.4.2 - Area Between Curves](images/Figure%205.4.2%20-%20Area%20Between%20Curves.png)

**Logic:** Area between = (Area under top) − (Area under bottom)

---

### Theorem 5.4.4 — Mean Value Theorem of Integration

> [!theorem] MVT for Integrals
> Let $f$ be continuous on $[a, b]$. There exists a value $c$ in $[a, b]$ such that:
> $$\int_a^b f(x) \, dx = f(c)(b - a)$$

**Geometric Interpretation:**
There exists a rectangle with:
- **Width:** $(b - a)$
- **Height:** $f(c)$

whose area **exactly equals** the area under the curve.

![Figure 5.4.5 - MVT Rectangle](images/Figure%205.4.5%20-%20MVT%20Rectangle.png)

---

### Definition 5.4.1 — Average Value of a Function

> [!definition] Average Value
> Let $f$ be continuous on $[a, b]$. The **average value** of $f$ on $[a, b]$ is:
> $$f_{\text{avg}} = \frac{1}{b - a} \int_a^b f(x) \, dx$$

> [!tip] Connection to MVT
> The average value $f_{\text{avg}} = f(c)$ where $c$ is the value guaranteed by the Mean Value Theorem.

---

### Motion Applications Summary

| Function | Integral Gives |
|----------|---------------|
| Velocity $v(t)$ | $\int_a^b v(t) \, dt =$ **Displacement** (change in position) |
| Speed $\|v(t)\|$ | $\int_a^b \|v(t)\| \, dt =$ **Distance traveled** |
| Acceleration $a(t)$ | $\int_a^b a(t) \, dt =$ **Change in velocity** |

> [!tip] Key Insight
> Integrating a **rate of change** function gives **total change**.

---

### Common Antiderivatives Reference

| Function $f(x)$ | Antiderivative $F(x)$ |
|-----------------|----------------------|
| $x^n$ | $\frac{x^{n+1}}{n+1}$ (for $n \neq -1$) |
| $\frac{1}{x}$ | $\ln\|x\|$ |
| $e^x$ | $e^x$ |
| $a^x$ | $\frac{a^x}{\ln a}$ |
| $\sin x$ | $-\cos x$ |
| $\cos x$ | $\sin x$ |
| $\sec^2 x$ | $\tan x$ |
| $\csc x \cot x$ | $-\csc x$ |

---

## Worked Problems

### Problem 1
> **How are definite and indefinite integrals related?**

**Answer:** We can evaluate a **definite integral** (a number) using an **indefinite integral** (antiderivative).

Using FTC Part 2: find the antiderivative $F(x)$, then compute $F(b) - F(a)$.

---

### Problem 2
> **What constant of integration is most commonly used when evaluating definite integrals?**

**Answer:** $C = 0$

The constant cancels when computing $F(b) - F(a)$, so we choose zero for simplicity. See Evaluation Notation.

---

### Problem 3
> **T/F: If $f$ is a continuous function, then $F(x) = \int_a^x f(t)\,dt$ is also a continuous function.**

**Answer: TRUE**

By FTC Part 1, $F$ is actually **differentiable**, which is even stronger than continuous. (Differentiable implies continuous.)

---

### Problem 4
> **The definite integral can be used to find "the area under a curve." Give two other uses for definite integrals.**

**Answer:** (Pick any two)
1. **Displacement** — integrating velocity (see Motion Applications)
2. **Change in velocity** — integrating acceleration
3. **Average value** of a function (see Average Value)
4. **Area between curves** (see Area Between Curves)

---

### Problem 5
> $$\int_1^3 (3x^2 - 2x + 1)\,dx$$

Using FTC Part 2:

**Step 1:** Find antiderivative
$$F(x) = x^3 - x^2 + x$$

**Step 2:** Evaluate $F(b) - F(a)$
$$F(3) = 27 - 9 + 3 = 21$$
$$F(1) = 1 - 1 + 1 = 1$$

**Answer:** $21 - 1 = \boxed{20}$

---

### Problem 7
> $$\int_{-1}^{1} (x^3 - x^5)\,dx$$

**Antiderivative:** $F(x) = \frac{1}{4}x^4 - \frac{1}{6}x^6$

**Evaluate:**
$$F(1) = \frac{1}{4} - \frac{1}{6} = \frac{1}{12}$$
$$F(-1) = \frac{1}{4} - \frac{1}{6} = \frac{1}{12}$$

**Answer:** $\frac{1}{12} - \frac{1}{12} = \boxed{0}$

> [!note] Why Zero?
> Both $x^3$ and $x^5$ are **odd functions**. On a symmetric interval $[-1, 1]$, positive and negative areas cancel.

---

### Problem 9
> $$\int_0^{\pi/4} \sec^2 x\,dx$$

Using Antiderivatives Reference: antiderivative of $\sec^2 x$ is $\tan x$

$$= \tan x \Big|_0^{\pi/4} = \tan\frac{\pi}{4} - \tan 0 = 1 - 0 = \boxed{1}$$

---

### Problem 11
> $$\int_{-1}^{1} 5^x\,dx$$

Using Antiderivatives Reference: antiderivative of $a^x$ is $\frac{a^x}{\ln a}$

$$F(x) = \frac{5^x}{\ln 5}$$

**Evaluate:**
$$F(1) - F(-1) = \frac{5}{\ln 5} - \frac{1/5}{\ln 5} = \frac{5 - 0.2}{\ln 5} = \boxed{\frac{24}{5\ln 5}}$$

---

### Problem 13
> $$\int_0^{\pi} (2\cos x - 2\sin x)\,dx$$

**Antiderivative:** $F(x) = 2\sin x + 2\cos x$

**Evaluate:**
$$F(\pi) = 2(0) + 2(-1) = -2$$
$$F(0) = 2(0) + 2(1) = 2$$

**Answer:** $-2 - 2 = \boxed{-4}$

---

### Problem 15
> $$\int_0^4 \sqrt{t}\,dt$$

Rewrite as $t^{1/2}$. Antiderivative: $\frac{t^{3/2}}{3/2} = \frac{2}{3}t^{3/2}$

**Evaluate:**
$$\frac{2}{3}(4)^{3/2} - \frac{2}{3}(0) = \frac{2}{3}(8) = \boxed{\frac{16}{3}}$$

> [!tip] Computing $4^{3/2}$
> $4^{3/2} = (4^{1/2})^3 = 2^3 = 8$

---

### Problem 17
> $$\int_1^8 \sqrt[3]{x}\,dx$$

Rewrite as $x^{1/3}$. Antiderivative: $\frac{x^{4/3}}{4/3} = \frac{3}{4}x^{4/3}$

**Evaluate:**
$$\frac{3}{4}(8)^{4/3} - \frac{3}{4}(1)^{4/3} = \frac{3}{4}(16) - \frac{3}{4}(1) = 12 - \frac{3}{4} = \boxed{\frac{45}{4}}$$

> [!tip] Computing $8^{4/3}$
> $8^{4/3} = (8^{1/3})^4 = 2^4 = 16$

---

### Problem 19
> $$\int_1^2 \frac{1}{x^2}\,dx$$

Rewrite as $x^{-2}$. Antiderivative: $\frac{x^{-1}}{-1} = -\frac{1}{x}$

**Evaluate:**
$$-\frac{1}{2} - \left(-\frac{1}{1}\right) = -\frac{1}{2} + 1 = \boxed{\frac{1}{2}}$$

---

### Problem 21
> $$\int_0^1 x\,dx$$

**Antiderivative:** $\frac{1}{2}x^2$

$$= \frac{1}{2}(1)^2 - \frac{1}{2}(0)^2 = \boxed{\frac{1}{2}}$$

---

### Problem 23
> $$\int_0^1 x^3\,dx$$

**Antiderivative:** $\frac{1}{4}x^4$

$$= \frac{1}{4}(1)^4 - 0 = \boxed{\frac{1}{4}}$$

---

### Problem 25
> $$\int_{-4}^{4} dx$$

This is $\int_{-4}^{4} 1\,dx$. Antiderivative: $x$

$$= 4 - (-4) = \boxed{8}$$

> [!note] Geometric View
> Rectangle with width 8 and height 1. Area = 8.

---

### Problem 27
> $$\int_{-2}^{2} 0\,dx$$

Antiderivative of 0 is any constant (use 0).

$$= 0 - 0 = \boxed{0}$$

---

### Problem 29
> **Explain why:**
> **(a)** $\int_{-1}^{1} x^n\,dx = 0$ when $n$ is a positive odd integer
> **(b)** $\int_{-1}^{1} x^n\,dx = 2\int_0^1 x^n\,dx$ when $n$ is a positive even integer

**(a) Odd powers:** When $n$ is odd, $f(x) = x^n$ is an **odd function** (symmetric about origin).
- Left half ($[-1, 0]$): negative area
- Right half ($[0, 1]$): positive area (same magnitude)
- They cancel → total = 0

**(b) Even powers:** When $n$ is even, $f(x) = x^n$ is an **even function** (symmetric about y-axis).
- Left half and right half have **identical** areas
- Total = 2 × (right half)

---

### Problem 31
> **Find a value $c$ guaranteed by the MVT for** $\int_0^2 x^2\,dx$

Using MVT for Integrals: find $c$ where $f(c)(b-a) = \int_a^b f(x)\,dx$

**Step 1:** Evaluate the integral
$$\int_0^2 x^2\,dx = \frac{1}{3}x^3\Big|_0^2 = \frac{8}{3}$$

**Step 2:** Set up MVT equation
$$c^2 \cdot (2-0) = \frac{8}{3}$$
$$2c^2 = \frac{8}{3}$$
$$c^2 = \frac{4}{3}$$
$$c = \frac{2}{\sqrt{3}} = \boxed{\frac{2\sqrt{3}}{3}} \approx 1.15$$

(We take the positive root since $c$ must be in $[0, 2]$)

---

### Problem 33
> **Find a value $c$ guaranteed by the MVT for** $\int_0^1 e^x\,dx$

**Step 1:** Evaluate the integral
$$\int_0^1 e^x\,dx = e^x\Big|_0^1 = e - 1$$

**Step 2:** Set up MVT equation
$$e^c \cdot (1-0) = e - 1$$
$$e^c = e - 1$$
$$c = \ln(e-1) \approx \boxed{0.54}$$

---

### Problem 38
> **Find the average value of $y = x^2$ on $[0, 4]$**

Using Average Value formula:

$$f_{\text{avg}} = \frac{1}{b-a}\int_a^b f(x)\,dx = \frac{1}{4-0}\int_0^4 x^2\,dx$$

**Evaluate the integral:**
$$\int_0^4 x^2\,dx = \frac{1}{3}x^3\Big|_0^4 = \frac{64}{3}$$

**Divide by interval width:**
$$f_{\text{avg}} = \frac{1}{4} \cdot \frac{64}{3} = \boxed{\frac{16}{3}}$$

---

### Problem 41
> **Find the displacement for $v(t) = -32t + 20$ ft/s on $[0, 5]$**

Using Motion Applications: integrate velocity to get displacement.

$$\int_0^5 (-32t + 20)\,dt = \left[-16t^2 + 20t\right]_0^5$$

**Evaluate:**
$$= [-16(25) + 20(5)] - 0 = -400 + 100 = \boxed{-300 \text{ ft}}$$

> [!note] Interpretation
> Negative displacement means the ball ended up 300 ft **below** its starting position.

---

### Problem 43
> **Find the displacement for $v(t) = 10$ ft/s on $[0, 3]$**

$$\int_0^3 10\,dt = 10t\Big|_0^3 = 30 - 0 = \boxed{30 \text{ ft}}$$

> [!note] Geometric View
> Constant velocity = rectangle. Width 3, height 10, area = 30.

---

### Problem 49
> **Find the change in velocity for $a(t) = t$ ft/s² on $[0, 2]$**

Using Motion Applications: integrate acceleration to get change in velocity.

$$\int_0^2 t\,dt = \frac{1}{2}t^2\Big|_0^2 = \frac{1}{2}(4) - 0 = \boxed{2 \text{ ft/s}}$$

---

### Problem 51
> **Sketch and find the area enclosed by $y = 2x$, $y = 5x$, and $x = 3$**

Using Area Between Curves:

**The region:** A triangle with vertices at $(0,0)$, $(3, 6)$, and $(3, 15)$.

- Top function: $y = 5x$
- Bottom function: $y = 2x$
- Bounds: $x = 0$ to $x = 3$

$$\text{Area} = \int_0^3 (5x - 2x)\,dx = \int_0^3 3x\,dx$$

$$= \frac{3}{2}x^2\Big|_0^3 = \frac{3}{2}(9) = \boxed{\frac{27}{2}}$$

---

### Problem 53
> **Sketch and find the area enclosed by $y = x^2 - 2x + 5$ and $y = 5x - 5$**

**Step 1:** Find intersection points
$$x^2 - 2x + 5 = 5x - 5$$
$$x^2 - 7x + 10 = 0$$
$$(x-2)(x-5) = 0$$
$$x = 2, \quad x = 5$$

**Step 2:** Determine which is on top (test $x = 3$)
- Line: $5(3) - 5 = 10$
- Parabola: $9 - 6 + 5 = 8$

The **line** is on top.

**Step 3:** Integrate using Area Between Curves
$$\text{Area} = \int_2^5 [(5x-5) - (x^2-2x+5)]\,dx = \int_2^5 (-x^2 + 7x - 10)\,dx$$

**Antiderivative:** $F(x) = -\frac{1}{3}x^3 + \frac{7}{2}x^2 - 10x$

**Evaluate:**
$$F(5) = -\frac{125}{3} + \frac{175}{2} - 50 = -\frac{250}{6} + \frac{525}{6} - \frac{300}{6} = -\frac{25}{6}$$

$$F(2) = -\frac{8}{3} + 14 - 20 = -\frac{8}{3} - 6 = -\frac{26}{3}$$

$$F(5) - F(2) = -\frac{25}{6} - \left(-\frac{26}{3}\right) = -\frac{25}{6} + \frac{52}{6} = \boxed{\frac{27}{6} = \frac{9}{2}}$$

---

### Problem 55
> **Find $F'(x)$ where $F(x) = \int_2^{x^3+x} \frac{1}{t}\,dt$**

Using FTC with Chain Rule:

- Integrand: $f(t) = \frac{1}{t}$
- Upper limit: $g(x) = x^3 + x$
- Derivative of upper limit: $g'(x) = 3x^2 + 1$

$$F'(x) = f(g(x)) \cdot g'(x) = \frac{1}{x^3+x} \cdot (3x^2 + 1) = \boxed{\frac{3x^2+1}{x^3+x}}$$

---

### Problem 57
> **Find $F'(x)$ where $F(x) = \int_x^{x^2} (t+2)\,dt$**

**Both limits have $x$!** Using FTC with Chain Rule, split at a constant:

$$F(x) = \int_0^{x^2}(t+2)\,dt - \int_0^x(t+2)\,dt$$

**Differentiate each piece:**

First piece: $\frac{d}{dx}\int_0^{x^2}(t+2)\,dt = (x^2+2)(2x)$

Second piece: $\frac{d}{dx}\int_0^x(t+2)\,dt = (x+2)(1)$

**Combine:**
$$F'(x) = (x^2+2)(2x) - (x+2)$$
$$= 2x^3 + 4x - x - 2$$
$$= \boxed{2x^3 + 3x - 2}$$

---

## Key Takeaways

> [!important] The Big Three Ideas
> 1. **FTC Part 1:** Differentiation undoes integration — $\frac{d}{dx}\int_a^x f(t) \, dt = f(x)$
> 2. **FTC Part 2:** Definite integrals can be computed using antiderivatives — $\int_a^b f(x) \, dx = F(b) - F(a)$
> 3. **Integration = Total Change:** Integrating a rate gives the total accumulated change

---

## Related Sections

- [Section 5.2 The Definite Integral of Calculus](Section%205.2%20The%20Definite%20Integral%20of%20Calculus.md) — Definition via Riemann sums
- [Section 5.3 Riemann Sums](Section%205.3%20Riemann%20Sums.md) — Approximation methods
- [Section 5.5 Numerical Integration](Section%205.5%20Numerical%20Integration.md) — When antiderivatives can't be found

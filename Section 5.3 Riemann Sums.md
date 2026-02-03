## Big Picture

This section uses the fundamental calculus technique:
1. **Approximate** → 2. **Refine** → 3. **Take limits** → 4. **Get exact answer**

We find the exact area under a curve (definite integral) by approximating with rectangles, using more and more rectangles, and taking the limit as n → ∞.

---

## Key Terms and Formulas

### Summation Notation

![Figure 5.3.4 - Summation Notation](images/Figure%205.3.4%20-%20Summation%20Notation.png)

---

### Integral Notation

```
                    b   ← upper bound
                   ⌠
                   |  f(x) dx
                   ⌡
                    a   ← lower bound
```

> [!tip] Remember
> **a** is the `lower bound` and **b** is the `upper bound`

---

### Three Rules for Rectangle Heights

| Rule                      | Where to measure height |
| ------------------------- | ----------------------- |
| **Left Hand Rule (LHR)**  | f(left endpoint)        |
| **Right Hand Rule (RHR)** | f(right endpoint)       |
| **Midpoint Rule (MPR)**   | f(midpoint)             |

```
    Left Hand Rule          Right Hand Rule         Midpoint Rule

    Heights: 0,3,4,3        Heights: 3,4,3,0       Heights: 1.75,3.75,3.75,1.75
    Sum = 10                Sum = 10               Sum = 11
```

As n → ∞, all three rules converge to the exact integral value.

---

### Key Idea 5.3.1: Core Formulas

**Width of Each Subinterval (Partition)**
$$\Delta x = \frac{b-a}{n}$$

**Evaluation Points**

| Rule | Formula |
|------|---------|
| Right Hand | $x_{i+1} = a + i \cdot \Delta x$ |
| Left Hand | $x_i = a + (i-1) \cdot \Delta x$ |
| Midpoint | $\frac{x_i + x_{i+1}}{2}$ |

**The Summations**

$$\text{Left Hand Rule: } \sum_{i=1}^{n} f(x_i)\Delta x$$

$$\text{Right Hand Rule: } \sum_{i=1}^{n} f(x_{i+1})\Delta x$$

$$\text{Midpoint Rule: } \sum_{i=1}^{n} f\left(\frac{x_i + x_{i+1}}{2}\right)\Delta x$$

---

### Theorem 5.3.1: Properties of Summations

These formulas let you skip adding up every term!

| # | Property | Formula |
|---|----------|---------|
| 1 | Constant | $\sum_{i=1}^{n} c = c \cdot n$ |
| 2 | Sum/Difference | $\sum_{i=m}^{n}(a_i \pm b_i) = \sum_{i=m}^{n}a_i \pm \sum_{i=m}^{n}b_i$ |
| 3 | Constant Multiple | $\sum_{i=m}^{n} c \cdot a_i = c \cdot \sum_{i=m}^{n}a_i$ |
| 4 | Splitting | $\sum_{i=m}^{j}a_i + \sum_{i=j+1}^{n}a_i = \sum_{i=m}^{n}a_i$ |
| 5 | Sum of i | $\sum_{i=1}^{n} i = \frac{n(n+1)}{2}$ |
| 6 | Sum of i² | $\sum_{i=1}^{n} i^2 = \frac{n(n+1)(2n+1)}{6}$ |
| 7 | Sum of i³ | $\sum_{i=1}^{n} i^3 = \left[\frac{n(n+1)}{2}\right]^2$ |

> [!tip] Key Point
> Just plug in **n** (the upper bound). The formula handles everything from 1 to n automatically!

**If Sum Doesn't Start at 1:**

$$\sum_{i=k}^{n} = \sum_{i=1}^{n} - \sum_{i=1}^{k-1}$$

---

### Taking Limits: The Shortcut

When top and bottom have the same highest power of n, just look at the leading coefficients:

$$\frac{n^2 + 2n + 1}{4n^2} \rightarrow \frac{1}{4}$$

The lower order terms (2n, 1) don't matter as n → ∞.

---

## Steps for Riemann Sum Formula Problems

**Given:** $\int_a^b f(x)\,dx$ with n subintervals

> [!tip] Remember
> **a** is the `lower bound` and **b** is the `upper bound`

**Step 1:** Find Δx (partition)
$$\Delta x = \frac{b-a}{n}$$

**Step 2:** Find the evaluation point
- Right Hand Rule: $x_{i+1} = a + i \cdot \Delta x$
- Left Hand Rule: $x_i = a + (i-1) \cdot \Delta x$
- Midpoint Rule: $\frac{x_i + x_{i+1}}{2}$

**Step 3:** Find the height
$$f(\text{evaluation point})$$

**Step 4:** Find area of one rectangle
$$f(\text{evaluation point}) \cdot \Delta x$$

**Step 5:** Sum it up
$$\sum_{i=1}^{n}[\text{area formula}]$$

**Step 6:** Apply Theorem 5.3.1 formulas

**Step 7:** Simplify

**Step 8:** Plug in n = 10, 100, 1000

**Step 9:** Take limit as n → ∞

---

## Worked Problems

### Problem 1
> **Riemann Sums are typically calculated using (one of:) the Left Hand Rule, the Right Hand Rule, or the _____ Rule.**

**Answer: Midpoint**

See Three Rules for Rectangle Heights.

---

### Problem 2
> **What is the upper bound in the summation** $\sum_{i=7}^{14} a_i$?

**Answer: 14**

Using Summation Notation, the upper bound is the number on top of the sigma.

---

### Problem 3
> **What is "the i-th term" of the summation** $\sum_{i=1}^{n} i^3$?

**Answer: $i^3$**

The summand (what we're adding) is $i^3$. See Summation Notation.

---

### Problem 4
> **T/F: The Right Hand Rule is a Riemann Sum.**

**Answer: TRUE**

All three rules (Left, Right, Midpoint) are Riemann Sums. See Three Rules for Rectangle Heights.

---

### Problem 5
> **Evaluate** $\sum_{i=2}^{4} i^2$

Using Summation Notation, add up each term:
$$2^2 + 3^2 + 4^2 = 4 + 9 + 16 = \boxed{29}$$

---

### Problem 7
> **Evaluate** $\sum_{i=-2}^{2} \sin\left(\frac{\pi i}{2}\right)$

Compute each term:
- $i = -2$: $\sin(-\pi) = 0$
- $i = -1$: $\sin(-\pi/2) = -1$
- $i = 0$: $\sin(0) = 0$
- $i = 1$: $\sin(\pi/2) = 1$
- $i = 2$: $\sin(\pi) = 0$

$$0 + (-1) + 0 + 1 + 0 = \boxed{0}$$

---

### Problem 9
> **Evaluate** $\sum_{i=1}^{5} \frac{1}{i}$

$$\frac{1}{1} + \frac{1}{2} + \frac{1}{3} + \frac{1}{4} + \frac{1}{5} = \frac{60 + 30 + 20 + 15 + 12}{60} = \boxed{\frac{137}{60}}$$

---

### Problem 11
> **Evaluate** $\sum_{i=1}^{4} \left(\frac{1}{i} - \frac{1}{i+1}\right)$

This is a **telescoping series**. Write out the terms:
$$\left(1 - \frac{1}{2}\right) + \left(\frac{1}{2} - \frac{1}{3}\right) + \left(\frac{1}{3} - \frac{1}{4}\right) + \left(\frac{1}{4} - \frac{1}{5}\right)$$

Most terms cancel:
$$= 1 - \frac{1}{5} = \boxed{\frac{4}{5}}$$

---

### Problem 13
> **Write in summation notation:** $3 + 6 + 9 + 12 + 15$

Pattern: each term is $3i$ where $i$ goes from 1 to 5.

$$\boxed{\sum_{i=1}^{5} 3i}$$

---

### Problem 15
> **Write in summation notation:** $\frac{1}{2} + \frac{2}{3} + \frac{3}{4} + \frac{4}{5}$

Pattern: each term is $\frac{i}{i+1}$ where $i$ goes from 1 to 4.

$$\boxed{\sum_{i=1}^{4} \frac{i}{i+1}}$$

---

### Problem 17
> **Evaluate using Theorem 5.3.1:** $\sum_{i=1}^{10} 5$

Using Property 1 (constant):
$$\sum_{i=1}^{n} c = c \cdot n$$

$$5 \cdot 10 = \boxed{50}$$

---

### Problem 19
> **Evaluate using Theorem 5.3.1:** $\sum_{i=1}^{10} (3i^2 - 2i)$

Using Properties 2, 3, 5, and 6:
$$= 3\sum_{i=1}^{10} i^2 - 2\sum_{i=1}^{10} i$$

$$= 3 \cdot \frac{10(11)(21)}{6} - 2 \cdot \frac{10(11)}{2}$$

$$= 3 \cdot 385 - 2 \cdot 55 = 1155 - 110 = \boxed{1045}$$

---

### Problem 21
> **Evaluate using Theorem 5.3.1:** $\sum_{i=1}^{10} (-4i^3 + 10i^2 - 7i + 11)$

Split and apply formulas:
$$= -4\sum i^3 + 10\sum i^2 - 7\sum i + 11\sum 1$$

$$= -4\left[\frac{10(11)}{2}\right]^2 + 10 \cdot \frac{10(11)(21)}{6} - 7 \cdot \frac{10(11)}{2} + 11 \cdot 10$$

$$= -4(3025) + 10(385) - 7(55) + 110$$

$$= -12100 + 3850 - 385 + 110 = \boxed{-8525}$$

---

### Problem 23
> **Evaluate:** $1 + 2 + 3 + \cdots + 100$

This is $\sum_{i=1}^{100} i$. Using Property 5:

$$\frac{100(101)}{2} = \boxed{5050}$$

---

### Problem 25
> **Evaluate:** $\sum_{i=11}^{20} i$

Sum doesn't start at 1, so subtract:
$$\sum_{i=11}^{20} i = \sum_{i=1}^{20} i - \sum_{i=1}^{10} i$$

$$= \frac{20(21)}{2} - \frac{10(11)}{2} = 210 - 55 = \boxed{155}$$

---

### Problem 27
> **Evaluate:** $\sum_{i=7}^{12} 4$

Using Property 1: constant × (number of terms)

Number of terms from 7 to 12 = 6

$$4 \cdot 6 = \boxed{24}$$

---

### Problem 29
> **Approximate** $\int_{-3}^{3} x^2\, dx$ **using Left Hand Rule with 6 rectangles.**

**Setup:** Using Key Idea 5.3.1
- $\Delta x = \frac{3-(-3)}{6} = 1$
- Left endpoints: $-3, -2, -1, 0, 1, 2$

| $x_i$ | $f(x_i) = x^2$ |
|-------|----------------|
| -3 | 9 |
| -2 | 4 |
| -1 | 1 |
| 0 | 0 |
| 1 | 1 |
| 2 | 4 |

$$LHR = \Delta x \cdot \sum f(x_i) = 1 \cdot (9 + 4 + 1 + 0 + 1 + 4) = \boxed{19}$$

---

### Problem 31
> **Approximate** $\int_0^{\pi} \sin(x)\, dx$ **using Right Hand Rule with 6 rectangles.**

**Setup:** Using Key Idea 5.3.1
- $\Delta x = \frac{\pi - 0}{6} = \frac{\pi}{6}$
- Right endpoints: $\frac{\pi}{6}, \frac{2\pi}{6}, \frac{3\pi}{6}, \frac{4\pi}{6}, \frac{5\pi}{6}, \pi$

| $x_{i+1}$ | $\sin(x_{i+1})$ |
|-----------|-----------------|
| $\pi/6$ | $1/2$ |
| $\pi/3$ | $\sqrt{3}/2$ |
| $\pi/2$ | $1$ |
| $2\pi/3$ | $\sqrt{3}/2$ |
| $5\pi/6$ | $1/2$ |
| $\pi$ | $0$ |

$$RHR = \frac{\pi}{6}\left(\frac{1}{2} + \frac{\sqrt{3}}{2} + 1 + \frac{\sqrt{3}}{2} + \frac{1}{2} + 0\right) = \frac{\pi}{6}(2 + \sqrt{3}) \approx \boxed{1.954}$$

---

### Problem 33
> **Approximate** $\int_1^{2} \ln(x)\, dx$ **using Midpoint Rule with 3 rectangles.**

**Setup:** Using Key Idea 5.3.1
- $\Delta x = \frac{2-1}{3} = \frac{1}{3}$
- Midpoints: $\frac{7}{6}, \frac{9}{6}, \frac{11}{6}$

| Midpoint | $\ln(\text{midpoint})$ |
|----------|------------------------|
| 7/6 ≈ 1.167 | 0.154 |
| 9/6 = 1.5 | 0.405 |
| 11/6 ≈ 1.833 | 0.606 |

$$MPR = \frac{1}{3}(0.154 + 0.405 + 0.606) = \frac{1}{3}(1.165) \approx \boxed{0.388}$$

---

### Problem 35
> **Find the Riemann Sum formula for** $\int_0^1 x^3\, dx$ **using Right Hand Rule. Then compute for n = 10, 100, 1000 and take the limit.**

**Step 1:** $\Delta x = \frac{1}{n}$
→ Using Δx = (b-a)/n with a=0, b=1

**Step 2:** $x_{i+1} = \frac{i}{n}$
→ Right Hand Rule: $(a + i \cdot \Delta x)$ — this is the **width (x)**

**Step 3:** $f\left(\frac{i}{n}\right) = \frac{i^3}{n^3}$
→ Since $f(x) = x^3$ — this is the **height (y)**

**Step 4:** $\frac{i^3}{n^3} \cdot \frac{1}{n} = \frac{i^3}{n^4}$
→ Width × height = area of one rectangle

**Step 5:** $\sum_{i=1}^{n} \frac{i^3}{n^4} = \frac{1}{n^4} \sum_{i=1}^{n} i^3$
→ Sum all the rectangles

**Step 6:** $= \frac{1}{n^4} \cdot \left[\frac{n(n+1)}{2}\right]^2$
→ Using Property 7 for $\sum i^3$

**Step 7:** $= \frac{(n+1)^2}{4n^2}$

**Step 8:**
- n = 10 → $\frac{121}{400}$ = 0.3025
- n = 100 → $\frac{10201}{40000}$ = 0.255025
- n = 1000 → $\frac{1002001}{4000000}$ = 0.25050025

**Step 9:** Using Taking Limits:
$$\lim_{n \to \infty} \frac{(n+1)^2}{4n^2} = \boxed{\frac{1}{4}}$$

> [!success] The Pattern
> As n increases, the approximation approaches 1/4. The exact integral is $\frac{1}{4}$.

---

### Problem 39
> **Find the Riemann Sum formula for** $\int_{-10}^{10} (5-x)\, dx$ **using Right Hand Rule.**

**Step 1:** $\Delta x = \frac{20}{n}$
→ Using Δx = (b-a)/n with a=-10, b=10

**Step 2:** $x_{i+1} = -10 + \frac{20i}{n}$
→ Right Hand Rule: $(a + i \cdot \Delta x)$

**Step 3:** $f\left(-10 + \frac{20i}{n}\right) = 5 - \left(-10 + \frac{20i}{n}\right) = 15 - \frac{20i}{n}$
→ Plug into $f(x) = 5-x$

**Step 4:** $\left(15 - \frac{20i}{n}\right) \cdot \frac{20}{n} = \frac{300}{n} - \frac{400i}{n^2}$

**Step 5:** $\sum_{i=1}^{n}\left(\frac{300}{n} - \frac{400i}{n^2}\right) = \frac{300}{n}\sum 1 - \frac{400}{n^2}\sum i$

**Step 6:** Using Properties 1 and 5:
$$= \frac{300}{n} \cdot n - \frac{400}{n^2} \cdot \frac{n(n+1)}{2} = 300 - \frac{200(n+1)}{n}$$

**Step 7:** $= 300 - 200 - \frac{200}{n} = 100 - \frac{200}{n}$

**Step 8:**
- n = 10 → 80
- n = 100 → 98
- n = 1000 → 99.8

**Step 9:** Using Taking Limits:
$$\lim_{n \to \infty} \left(100 - \frac{200}{n}\right) = \boxed{100}$$

---

## Related Notes
- [Section 5.2 The Definite Integral of Calculus](Section%205.2%20The%20Definite%20Integral%20of%20Calculus.md) - Definition of the definite integral
- [Section 5.4 The Fundamental Theorem of Calculus](Section%205.4%20The%20Fundamental%20Theorem%20of%20Calculus.md) - Skip Riemann sums with antiderivatives!

## The Big Idea

**The core concept:** The definite integral $\int_a^b f(x)\,dx$ computes the **total signed area** between a function and the x-axis over $[a,b]$.

**Physical interpretation:** For velocity functions, this signed area equals **displacement**—area above the axis is forward motion, area below is backward motion.

**Two methods for evaluation:**
1. **Geometric** — use area formulas for triangles, rectangles, semicircles
2. **Antiderivatives** — covered in [[Section 5.4 The Fundamental Theorem of Calculus|Section 5.4]]

---

## Key Formulas

### Definition 5.2.1 — The Definite Integral
^definite-integral-definition

$$\int_a^b f(x)\,dx = \text{(Area above x-axis)} - \text{(Area below x-axis)}$$

- $a$ and $b$ are the **bounds of integration**
- The result is called **total signed area**

---

### Theorem 5.2.1 — Properties of the Definite Integral
^properties

|  #  | Property          | Formula                                                                               |
| :-: | :---------------- | :------------------------------------------------------------------------------------ |
|  1  | Zero Width        | $\displaystyle\int_a^a f(x)\,dx = 0$                                                  |
|  2  | Additivity        | $\displaystyle\int_a^b f(x)\,dx + \int_b^c f(x)\,dx = \int_a^c f(x)\,dx$              |
|  3  | Reversal          | $\displaystyle\int_a^b f(x)\,dx = -\int_b^a f(x)\,dx$                                 |
|  4  | Sum/Difference    | $\displaystyle\int_a^b [f(x) \pm g(x)]\,dx = \int_a^b f(x)\,dx \pm \int_a^b g(x)\,dx$ |
|  5  | Constant Multiple | $\displaystyle\int_a^b k \cdot f(x)\,dx = k \cdot \int_a^b f(x)\,dx$                  |

---

### Geometric Area Formulas
^area-formulas

| Shape | Formula |
|:-----:|:-------:|
| Rectangle | $A = \text{base} \times \text{height}$ |
| Triangle | $A = \frac{1}{2} \times \text{base} \times \text{height}$ |
| Trapezoid | $A = \frac{1}{2}(b_1 + b_2) \times h$ |
| Semicircle | $A = \frac{1}{2}\pi r^2$ |

---

### Velocity-Displacement Connection
^displacement

$$\text{Displacement} = \int_a^b v(t)\,dt$$

- Area **above** t-axis → forward motion (positive)
- Area **below** t-axis → backward motion (negative)

---

## Worked Problems

### Problem 1
> **What is "total signed area"?**

**Answer:** Total signed area is the area between $f(x)$ and the x-axis where regions **above** the x-axis count as **positive** and regions **below** count as **negative**. This is exactly what the [[#^definite-integral-definition|definite integral]] computes.

---

### Problem 2
> **What is "displacement"?**

**Answer:** Displacement is the **net change in position** from starting point. Unlike total distance traveled, displacement accounts for direction—moving backward subtracts from forward progress. By the [[#^displacement|velocity-displacement connection]], displacement equals the definite integral of velocity.

---

### Problem 3
> **What is $\int_3^3 \sin x\, dx$?**

**Answer:** $\boxed{0}$

By [[#^properties|Property 1 (Zero Width)]], when upper and lower bounds are equal, there's no width, hence no area.

---

### Problem 4
> **Give a single definite integral equal to $\int_0^1 (2x+3)\,dx + \int_1^2 (2x+3)\,dx$**

**Answer:** $\boxed{\int_0^2 (2x+3)\,dx}$

By [[#^properties|Property 2 (Additivity)]], adjacent integrals combine: $\int_0^1 + \int_1^2 = \int_0^2$

---

### Problem 5
> **Given $y = -2x + 4$, evaluate the definite integrals.**

![[Figure 5.2 Exercise 5 - Linear Function.png]]

**Setup:** Line with y-intercept 4, x-intercept at $x = 2$ (solve $-2x + 4 = 0$)

**(a) $\int_0^1 (-2x+4)\,dx$**

Trapezoid above x-axis from $x=0$ to $x=1$:
- Base = 1
- Heights: $f(0) = 4$, $f(1) = 2$

Using [[#^area-formulas|trapezoid formula]]: $A = \frac{1}{2}(4 + 2)(1) = \boxed{3}$

**(b) $\int_0^2 (-2x+4)\,dx$**

Triangle above x-axis from $x=0$ to $x=2$:
- Base = 2, Height = 4

Using [[#^area-formulas|triangle formula]]: $A = \frac{1}{2}(2)(4) = \boxed{4}$

**(c) $\int_0^3 (-2x+4)\,dx$**

Two regions—apply [[#^definite-integral-definition|signed area]]:
- Triangle above x-axis on $[0,2]$: Area = 4
- Triangle below x-axis on $[2,3]$: Base = 1, Height = $|f(3)| = 2$, Area = $\frac{1}{2}(1)(2) = 1$

$$4 - 1 = \boxed{3}$$

**(d) $\int_1^3 (-2x+4)\,dx$**

Two regions—apply [[#^definite-integral-definition|signed area]]:
- Trapezoid above x-axis on $[1,2]$: $\frac{1}{2}(2+0)(1) = 1$
- Triangle below x-axis on $[2,3]$: $\frac{1}{2}(1)(2) = 1$

$$1 - 1 = \boxed{0}$$

**(e) $\int_2^4 (-2x+4)\,dx$**

Triangle below x-axis on $[2,4]$—by [[#^definite-integral-definition|signed area]], this is negative:
- Base = 2, Height = $|f(4)| = 4$

$$-\frac{1}{2}(2)(4) = \boxed{-4}$$

**(f) $\int_0^1 (-6x+12)\,dx$**

Notice $-6x+12 = 3(-2x+4)$. By [[#^properties|Property 5 (Constant Multiple)]]:
$$3 \cdot \int_0^1 (-2x+4)\,dx = 3(3) = \boxed{9}$$

---

### Problem 7
> **Given the graph of $f(x)$** (piecewise linear, peak at $(1,4)$, through $(0,0)$, $(2,4)$, $(4,0)$)

![[Figure 5.2 Exercise 7 - Piecewise Linear.png]]

**(a) $\int_0^2 f(x)\,dx$**

Triangle with base 2, height 4. Using [[#^area-formulas|triangle formula]]:
$$\frac{1}{2}(2)(4) = \boxed{4}$$

**(b) $\int_2^4 f(x)\,dx$**

Triangle with base 2, height 4. Using [[#^area-formulas|triangle formula]]:
$$\frac{1}{2}(2)(4) = \boxed{4}$$

**(c) $\int_2^4 2f(x)\,dx$**

By [[#^properties|Property 5 (Constant Multiple)]]: $2 \cdot \int_2^4 f(x)\,dx = 2(4) = \boxed{8}$

**(d) $\int_0^1 4x\,dx$**

The line $y = 4x$ from 0 to 1 forms a triangle. Using [[#^area-formulas|triangle formula]]:
- Base = 1, Height = 4

$$\frac{1}{2}(1)(4) = \boxed{2}$$

**(e) $\int_2^3 (2x-4)\,dx$**

Line through $(2,0)$ and $(3,2)$—triangle above x-axis. Using [[#^area-formulas|triangle formula]]:
- Base = 1, Height = 2

$$\frac{1}{2}(1)(2) = \boxed{1}$$

**(f) $\int_2^3 (4x-8)\,dx$**

Notice $4x-8 = 2(2x-4)$. By [[#^properties|Property 5 (Constant Multiple)]]: $2(1) = \boxed{2}$

---

### Problem 9
> **Given $f(x) = \sqrt{4-(x-2)^2}$** (semicircle centered at $(2,0)$ with radius 2)

![[Figure 5.2 Exercise 9 - Semicircle.png]]

**(a) $\int_0^2 f(x)\,dx$**

Quarter circle with radius 2. Using [[#^area-formulas|semicircle formula]] (half of it):
$$\frac{1}{4}\pi(2)^2 = \boxed{\pi}$$

**(b) $\int_2^4 f(x)\,dx$**

Quarter circle with radius 2. Using [[#^area-formulas|semicircle formula]] (half of it):
$$\frac{1}{4}\pi(2)^2 = \boxed{\pi}$$

**(c) $\int_0^4 f(x)\,dx$**

Full semicircle with radius 2. Using [[#^area-formulas|semicircle formula]]:
$$\frac{1}{2}\pi(2)^2 = \boxed{2\pi}$$

**(d) $\int_0^4 5f(x)\,dx$**

By [[#^properties|Property 5 (Constant Multiple)]]: $5 \cdot \int_0^4 f(x)\,dx = 5(2\pi) = \boxed{10\pi}$

---

### Problem 11
> **Given graph with labeled areas: 59, 11, 21**

![[Figure 5.2 Exercise 11 - Labeled Areas.png]]

**(a) $\int_0^1 f(x)\,dx$**

Region on $[0,1]$ is above x-axis with given area 59. By [[#^definite-integral-definition|signed area]]:
$$\boxed{59}$$

**(b) $\int_0^2 f(x)\,dx$**

By [[#^properties|Property 2 (Additivity)]] and [[#^definite-integral-definition|signed area]]:
- Region on $[0,1]$ above: $+59$
- Region on $[1,2]$ below: $-11$

$$59 - 11 = \boxed{48}$$

**(c) $\int_0^3 f(x)\,dx$**

Continuing with [[#^properties|Property 2 (Additivity)]] and [[#^definite-integral-definition|signed area]]:
$$59 - 11 - 21 = \boxed{27}$$

**(d) $\int_1^2 (-3f(x))\,dx$**

By [[#^properties|Property 5 (Constant Multiple)]]: 
$$-3 \cdot \int_1^2 f(x)\,dx = -3(-11) = \boxed{33}$$

---

### Problem 13
> **Given $f(x) = 3x^2 - 3$ with labeled areas: 4, 4**

![[Figure 5.2 Exercise 13 - Cubic Areas.png]]

**(a) $\int_{-2}^{-1} f(x)\,dx$**

Region on $[-2,-1]$ is above x-axis with given area 4. By [[#^definite-integral-definition|signed area]]:
$$\boxed{4}$$

**(b) $\int_1^2 f(x)\,dx$**

Region on $[1,2]$ is above x-axis with given area 4. By [[#^definite-integral-definition|signed area]]:
$$\boxed{4}$$

**(c) $\int_{-1}^1 f(x)\,dx$**

The function $3x^2 - 3 = 3(x-1)(x+1)$ has roots at $x = \pm 1$. The parabola opens upward, so it's **below** the x-axis on $[-1,1]$. By [[#^definite-integral-definition|signed area]], this is negative:
$$\boxed{-4}$$

**(d) $\int_0^1 f(x)\,dx$**

By symmetry of $f(x) = 3x^2-3$ about the y-axis, this is half of $\int_{-1}^1 f(x)\,dx$:
$$\frac{1}{2}(-4) = \boxed{-2}$$

---

### Problem 16
> **Velocity graph given** (see figure)

![[Figure 5.2 Exercise 16 - Velocity Graph.png]]

**(a) What is the object's maximum velocity?**

Reading from the graph peak: $\boxed{3 \text{ ft/s}}$

**(b) What is the object's maximum displacement?**

Using [[#^displacement|velocity-displacement connection]], track position by computing signed areas:

The entire region from $t=0$ to $t=5$ appears to be above the t-axis (all positive velocity), so displacement keeps increasing. Maximum occurs at $t=5$.

Total area (trapezoid-like shape): $\boxed{7.5 \text{ ft}}$

**(c) What is the object's total displacement on $[0, 5]$?**

Same as maximum displacement since velocity is always positive:
$$\boxed{7.5 \text{ ft}}$$

---

### Problem 17
> **$v(t) = -32t + 64$ ft/s, initial height 48 ft**

**Setup:** Find when $v(t) = 0$: $-32t + 64 = 0 \Rightarrow t = 2$ s

**(a) Maximum velocity?**

At $t = 0$: $v(0) = 64$ ft/s 

$$\boxed{64 \text{ ft/s}}$$

**(b) Maximum displacement?**

Using [[#^displacement|velocity-displacement connection]], displacement equals area under velocity curve.

From $t=0$ to $t=2$, velocity is positive (object rising). Using [[#^area-formulas|triangle formula]]:
$$\frac{1}{2}(2)(64) = \boxed{64 \text{ ft}}$$

**(c) When does maximum displacement occur?**

Maximum displacement occurs when velocity changes from positive to negative (object stops rising):
$$\boxed{t = 2 \text{ s}}$$

**(d) When will the object reach height 0?**

Height = initial height + displacement = $48 + \int_0^t v(\tau)\,d\tau$

By [[#^displacement|velocity-displacement connection]], we need total displacement = $-48$ ft.

- From $t=0$ to $t=2$: displacement = $+64$ ft
- From $t=2$ onward: velocity is negative, object falls

At time $t > 2$, additional displacement = $-\frac{1}{2}(t-2)(32(t-2)) = -16(t-2)^2$

Total displacement: $64 - 16(t-2)^2$

Set height = 0: $48 + 64 - 16(t-2)^2 = 0$
$$112 = 16(t-2)^2$$
$$(t-2)^2 = 7$$
$$t = 2 + \sqrt{7} \approx \boxed{4.65 \text{ s}}$$

---

### Problem 19
> **Given:** $\int_0^2 f(x)\,dx = 5$, $\int_0^3 f(x)\,dx = 7$, $\int_0^2 g(x)\,dx = -3$, $\int_2^3 g(x)\,dx = 5$
>
> **Find:** $\int_0^2 [f(x) + g(x)]\,dx$

By [[#^properties|Property 4 (Sum/Difference)]]:
$$\int_0^2 f(x)\,dx + \int_0^2 g(x)\,dx = 5 + (-3) = \boxed{2}$$

---

### Problem 21
> **Find:** $\int_2^3 [3f(x) + 2g(x)]\,dx$

**Step 1:** Find $\int_2^3 f(x)\,dx$ using [[#^properties|Property 2 (Additivity)]]:

$$\int_0^2 f + \int_2^3 f = \int_0^3 f$$
$$5 + \int_2^3 f = 7$$
$$\int_2^3 f(x)\,dx = 2$$

**Step 2:** Apply [[#^properties|Property 4 (Sum/Difference)]] and [[#^properties|Property 5 (Constant Multiple)]]:
$$3\int_2^3 f(x)\,dx + 2\int_2^3 g(x)\,dx = 3(2) + 2(5) = \boxed{16}$$

---

### Problem 23
> **Given:** $\int_0^3 s(t)\,dt = 10$, $\int_3^5 s(t)\,dt = 8$, $\int_3^5 r(t)\,dt = -1$, $\int_0^5 r(t)\,dt = 11$
>
> **Find:** $\int_0^3 [s(t) + r(t)]\,dt$

**Step 1:** Find $\int_0^3 r(t)\,dt$ using [[#^properties|Property 2 (Additivity)]]:

$$\int_0^3 r + \int_3^5 r = \int_0^5 r$$
$$\int_0^3 r + (-1) = 11$$
$$\int_0^3 r(t)\,dt = 12$$

**Step 2:** Apply [[#^properties|Property 4 (Sum/Difference)]]:
$$\int_0^3 s(t)\,dt + \int_0^3 r(t)\,dt = 10 + 12 = \boxed{22}$$

---

### Problem 25
> **Find:** $\int_3^3 [\pi s(t) - 7r(t)]\,dt$

By [[#^properties|Property 1 (Zero Width)]], when bounds are equal:
$$\boxed{0}$$

---

## Quick Reference

| Situation | Property | Result |
|:----------|:---------|:-------|
| Same upper/lower bound | [[#^properties\|Property 1]] | 0 |
| Bounds reversed | [[#^properties\|Property 3]] | Negate the integral |
| Split at a point | [[#^properties\|Property 2]] | Add integrals over subintervals |
| Sum of functions | [[#^properties\|Property 4]] | Sum of integrals |
| Constant multiple | [[#^properties\|Property 5]] | Factor out the constant |
| Linear function | [[#^area-formulas\|Area formulas]] | Triangle or trapezoid |
| $\sqrt{r^2 - x^2}$ | [[#^area-formulas\|Area formulas]] | Semicircle with radius $r$ |
| Velocity to displacement | [[#^displacement\|Displacement]] | Signed area under $v(t)$ |

---

## Common Mistakes

> [!warning] Watch Out!
> 1. **Forgetting signs** — Area below x-axis is NEGATIVE per [[#^definite-integral-definition|Definition 5.2.1]]
> 2. **Confusing bounds** — $\int_a^b \neq \int_b^a$ by [[#^properties|Property 3]]
> 3. **Velocity vs. speed** — [[#^displacement|Displacement]] uses signed area; distance uses total area

---

## Related Notes
- [[Section 5.3 Riemann Sums]] — How definite integrals are formally defined
- [[Section 5.4 The Fundamental Theorem of Calculus]] — Connecting derivatives and integrals

# Chapter 2 — Exercise 2.1

## Problem Statement

We consider $(\mathbb{R} \setminus \{-1\}, \star)$, where
$$a \star b := ab + a + b, \qquad a, b \in \mathbb{R} \setminus \{-1\}$$

1. **(a)** Show that $(\mathbb{R} \setminus \{-1\}, \star)$ is an Abelian group.
2. **(b)** Solve $3 \star x \star x = 15$ in the Abelian group $(\mathbb{R} \setminus \{-1\}, \star)$.

---

## Solution

### (a) Showing that $(\mathbb{R} \setminus \{-1\}, \star)$ is an Abelian group

First, notice that we can rewrite the operation by adding and subtracting $1$ to factor it:
$$a \star b = ab + a + b + 1 - 1 = (a + 1)(b + 1) - 1$$

1. **Closure**:
   Take any $a, b \in \mathbb{R} \setminus \{-1\}$. Then $a + 1 \neq 0$ and $b + 1 \neq 0$, so their product in $\mathbb{R}$ is non-zero:
   $$(a + 1)(b + 1) \neq 0 \implies (a + 1)(b + 1) - 1 \neq -1$$
   Therefore $a \star b \in \mathbb{R} \setminus \{-1\}$.

2. **Associativity**:
   For any $a, b, c \in \mathbb{R} \setminus \{-1\}$:
   $$(a \star b) \star c = \big((a+1)(b+1) - 1\big) \star c = \big((a+1)(b+1) - 1 + 1\big)(c+1) - 1 = (a+1)(b+1)(c+1) - 1$$
   $$a \star (b \star c) = a \star \big((b+1)(c+1) - 1\big) = (a+1)\big((b+1)(c+1) - 1 + 1\big) - 1 = (a+1)(b+1)(c+1) - 1$$
   Hence $(a \star b) \star c = a \star (b \star c)$.

3. **Neutral element**:
   We look for $e \in \mathbb{R} \setminus \{-1\}$ such that $a \star e = a$ for all $a \in \mathbb{R} \setminus \{-1\}$:
   $$(a + 1)(e + 1) - 1 = a \implies (a + 1)(e + 1) = a + 1$$
   Since $a + 1 \neq 0$, dividing both sides by $a + 1$ gives $e + 1 = 1 \implies e = 0 \in \mathbb{R} \setminus \{-1\}$.

4. **Inverse element**:
   For a given $a \in \mathbb{R} \setminus \{-1\}$, we need $a^{-1} \in \mathbb{R} \setminus \{-1\}$ such that $a \star a^{-1} = e = 0$:
   $$(a + 1)(a^{-1} + 1) - 1 = 0 \implies a^{-1} + 1 = \frac{1}{a + 1} \implies a^{-1} = \frac{1}{a + 1} - 1 = \frac{-a}{a + 1}$$
   This is well-defined because $a \neq -1$, and $a^{-1} \neq -1$ because $a^{-1} + 1 = \frac{1}{a+1} \neq 0$.

5. **Commutativity (Abelian)**:
   Since real addition and multiplication commute:
   $$a \star b = ab + a + b = ba + b + a = b \star a$$

---

### (b) Solving $3 \star x \star x = 15$

Using the factored form $(a+1)(b+1)(c+1) - 1$ from part (a):
$$3 \star x \star x = (3 + 1)(x + 1)(x + 1) - 1 = 4(x + 1)^2 - 1$$

Setting this equal to $15$:
$$\begin{aligned}
4(x + 1)^2 - 1 &= 15 \\
4(x + 1)^2 &= 16 \\
(x + 1)^2 &= 4 \\
x + 1 &= \pm 2
\end{aligned}$$

This yields two solutions in $\mathbb{R} \setminus \{-1\}$:
- $x + 1 = 2 \implies x = 1$
- $x + 1 = -2 \implies x = -3$

**Verification**:
- For $x = 1$: $3 \star 1 = 3(1) + 3 + 1 = 7$, and $7 \star 1 = 7(1) + 7 + 1 = 15$.
- For $x = -3$: $3 \star (-3) = 3(-3) + 3 - 3 = -9$, and $(-9) \star (-3) = 27 - 9 - 3 = 15$.

# Exercice 1

$R_{1}(x,y)=x^2+y^2+1$

$\frac{\partial f}{\partial x}=2x$, $\frac{\partial f}{\partial y}=2y$

$$
H_{f(x,y)} = \begin{pmatrix}
2 & 0 \\
0 & 2
\end{pmatrix}
$$

$$
f(u) = \frac{1}{2} u^T A u + b^T u + c
$$

$$
f(x,y) = \frac{1}{2} 
\begin{pmatrix} x & y \end{pmatrix}
\begin{pmatrix} 2 & 0 \\ 0 & 2 \end{pmatrix}
\begin{pmatrix} x \\ y \end{pmatrix} + 1
$$

---

$h(x,y) = x^2 - 2xy + 5y^2 + y$

$$
H = \begin{pmatrix} 2 & -2 \\ -2 & 10 \end{pmatrix}
$$

$\frac{\partial h}{\partial x} = 2x - 2y$, $\frac{\partial h}{\partial y} = 10y + 1 - 2x$, $\frac{\partial^2 h}{\partial x \partial y} = -2$, $\frac{\partial^2 h}{\partial y \partial x} = -2$, $\frac{\partial^2 h}{\partial x^2} = 2$, $\frac{\partial^2 h}{\partial y^2} = 10$

---

$$
f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}
$$

$\frac{\partial f}{\partial x} = 3x - 1 + 2y$, $\frac{\partial f}{\partial y} = 2y + 2x - 2$, $\frac{\partial^2 f}{\partial x^2} = 3$, $\frac{\partial^2 f}{\partial y^2} = 2$, $\frac{\partial^2 f}{\partial x \partial y} = 2$

$$
f(x,y) = \frac{1}{2} 
\begin{pmatrix} x & y \end{pmatrix}
\begin{pmatrix} 3 & 2 \\ 2 & 2 \end{pmatrix}
\begin{pmatrix} x \\ y \end{pmatrix}
+ \begin{pmatrix} -1 \\ -2 \end{pmatrix}^T
\begin{pmatrix} x \\ y \end{pmatrix} + \frac{5}{2}
$$

$$
\Delta = 25 - 8 = 17 > 0
$$

$$
x_1 = \frac{-b - \sqrt{\Delta}}{2a}, \quad x_2 = \frac{-b + \sqrt{\Delta}}{2a}
$$

$$
\nabla f = 0 \implies 
\begin{cases}
3x - 1 + 2y = 0 \\
2y + 2x - 2 = 0
\end{cases} 
\implies x = -1, y = 2
$$

$$
f(-1,2) = 0 \quad \text{(erreur sur le calcul de fin, se référer à l'exercice 6)}
$$

---

# Exercice 2

$g(x,y) = \frac{e^{x+y}}{\sqrt{x+y}}$, $D_g = \{ (x,y) \in \mathbb{R}^2 \mid x+y > 0 \}$

$u = x + y$, $u > 0$, $g(u) = \frac{e^u}{\sqrt{u}}$

$$
g'(u) = e^u u^{-1/2} - \frac{1}{2} e^u u^{-3/2} = e^u \left( u^{-1/2} - \frac{1}{2} u^{-3/2} \right)
$$

$$
g''(u) = e^u \left( u^{-1/2} - u^{-3/2} + \frac{3}{4} u^{-5/2} \right) = e^u u^{-5/2} \left( u^2 - u + \frac{3}{4} \right)
$$

$\Delta = 1^2 - 4 \times \frac{3}{4} = -2 < 0$, donc le polynôme est toujours positif et $g$ est convexe.

$$
\frac{\partial g}{\partial x} = \frac{\partial g}{\partial y} = \frac{e^{x+y} \left( \sqrt{x+y} - \frac{1}{2\sqrt{x+y}} \right)}{x+y}
$$

$$
Z = f(a,b) + \frac{\partial f}{\partial x}(a,b)(x-a) + \frac{\partial f}{\partial y}(a,b)(y-b)
$$

---

# Exercice 3

$$
f(x,y) = x e^y + y e^x
$$

$$
\begin{cases}
xy = 1 \\
x e^{1/x} + e^x = 0
\end{cases}
$$

$$
\frac{\partial f}{\partial x} = e^y + y e^x, \quad \frac{\partial f}{\partial y} = x e^y + e^x
$$

$$
\nabla f = \begin{pmatrix} e^y + y e^x \\ x e^y + e^x \end{pmatrix}
$$

$$
\nabla f = 0 \iff 
\begin{cases}
e^y + y e^x = 0 \\
x e^y + e^x = 0
\end{cases} \iff 
y = \frac{1}{x}, \quad x e^{1/x} + e^x = 0
$$

$$
\phi(x) = x e^{1/x} + e^x, \quad \phi'(x) = -\frac{1}{x^2} e^{1/x} + e^{1/x} + e^x
$$

$$
\frac{\partial^2 f}{\partial x^2} = y e^x = -e^{-1}, \quad \frac{\partial^2 f}{\partial y^2} = x e^y = -e^{-1}
$$

$$
\frac{\partial^2 f}{\partial y \partial x} = \frac{\partial^2 f}{\partial x \partial y} = e^y + e^x = 2 e^{-1}
$$

$$
H = \begin{pmatrix} -e^{-1} & 2 e^{-1} \\ 2 e^{-1} & -e^{-1} \end{pmatrix}, \quad \det H = -3 e^{-2}
$$

---

# Exercice 4

$$
f(x) = \frac{1}{1 + e^x}, \quad Df = \mathbb{R}
$$

$$
f'(x) = \frac{-e^x}{(1 + e^x)^2}, \quad f''(x) = \frac{e^x (e^x - 1)}{(1 + e^x)^3}
$$

$$
f''(x) > 0 \implies x > 0, \quad f''(x) < 0 \implies x < 0
$$

$$
f(x) \text{ convexe sur } ]0; +\infty[, \quad f(x) \text{ concave sur } ]-\infty; 0[
$$

---

# Exercice 6

$$
f : \mathbb{R}^2 \to \mathbb{R}, \quad
f(x,y) = \frac{3}{2}x^2 + y^2 - x + 2xy - 2y + \frac{5}{2}
$$

$$
H = \begin{pmatrix} 3 & 2 \\ 2 & 2 \end{pmatrix}, \quad
\det(H - \lambda I) = (3-\lambda)(2-\lambda) - 4 = \lambda^2 - 5\lambda + 2
$$

$$
\Delta = 17, \quad x_1 = \frac{5 + \sqrt{17}}{2}, \quad x_2 = \frac{5 - \sqrt{17}}{2}
$$

$$
\nabla f = 0 \implies
\begin{cases}
3x + 2y - 1 = 0 \\
2x + 2y - 2 = 0
\end{cases} \implies x = -1, y = 0
$$

$$
X^{(K+1)} = X^{(K)} + \alpha W^{(K)}, \quad W^{(K)} = -\nabla f(X^{(K)}), \quad X^0 = (0,0)
$$

$$
X^{(1)} = X^{(0)} + \frac{5}{19} W^{(0)}, \quad f(X^{(1)}) = f\left(\frac{5}{19}, \frac{10}{19}\right)
$$

# Exercice 1

$R_{1}(x,y)=x^2+y^2+1$

$\frac{\delta f}{\delta x}=2x$, $\frac{\delta f}{\delta y}=2y$

$$H_{f(x,y)}\left( \begin{array} \\
2&0 \\
0&2
\end{array} \right)$$
$$f(u)=\frac{1}{2}u Au+b+u+c$$
$$f(x,y)=\frac{1}{2} \left( \begin{array}
&2 &0 \\
0&2
\end{array} \right) \left( \begin{array}
&x \\
y
\end{array} \right)+1$$


---
$h(x,y)=x^2-2xy+5y^2+y$
$$H=\left( \begin{array}
&2&-2 \\
-2&10
\end{array} \right)$$
$\frac{\delta h}{\delta x}=2x-2y$, $\frac{\delta h}{\delta y}=10y+1-2x$, $\frac{\delta^2 h}{\delta x\delta y}=-2$,$\frac{\delta^2 h}{\delta y\delta x}=-2$, $\frac{\delta^2 h}{\delta^2 x}=2$,$\frac{\delta^2 h}{\delta^2 y}=10$

---
$$\begin{align}
&f(x,y)=\frac{3}{2}x^2+y^2-x+2xy-2y+\frac{5}{2} \\

\end{align}$$


$\frac{\delta f}{\delta x}=3x-1+2y$,$\frac{\delta f}{\delta y}=2y+2x-2$,$\frac{\delta^2 f}{\delta x^2}=3$,$\frac{\delta^2 f}{\delta y^2}=2$,$\frac{\delta^2 f}{\delta xy}=2$,$\frac{\delta^2 f}{\delta yx}=2$

$$\begin{align}
&f(x,y)=\frac{1}{2}(x,y)\left( \begin{array}
&3&2 \\
2&2
\end{array} \right)\left( \begin{array}
&x \\
y
\end{array} \right)+(-1,-2)\left( \begin{array}
&x \\
y
\end{array} \right)+\frac{5}{2} \\
&f(x,y)=\frac{1}{2}(x,y)\left( \begin{array}
&3&2 \\
2&2
\end{array} \right)\left( \begin{array}
&x \\
y
\end{array} \right)+(-1,-2)\left( \begin{array}
&x \\
y
\end{array} \right)+\frac{5}{2} \\
&\begin{array}
& \Delta=25-8=17>0 \\
x_{1}=\frac{-b-\sqrt{ \Delta }}{2a} &x_{2}=\frac{-b+\sqrt{ \Delta }}{2a} \\
= \frac{5-\sqrt{ 17 }}{2}&=\frac{5+\sqrt{ 17 }}{2}
\end{array} \\
&\nabla f=0\implies \underset{\begin{array}
&x+1=0 \\
x=0
\end{array}}{\begin{cases}
3x-1+2y=0 \\
2y+2x-2=0
\end{cases}}~~~~
\begin{array}
2y-4=0 \\
2y=4 \\
y=2
\end{array} \\
&f(-1,2)=\frac{3}{2}+\cancel{4-4}-4+\frac{5}{2}=4-4=0
\end{align}$$

_____

# Exercice 2

$g(x,y)=\frac{e^{x+y}}{\sqrt{ x+y }}$
$D_{g}=\{ (x,y)\in\mathbb{R}^2|x+y>0 \}$

$u=x+y$, $u>0$, $g(u)=\frac{e^u}{\sqrt{ u }}$, 
$$\begin{align}
&g'(u)=&\frac{e^u-\frac{1}{2\sqrt{ u }}e^u}{u}=e^uu^{\frac{1}{2}}-\frac{1}{2}e^uu^{-\frac{3}{2}} \\
&g''(u)=&e^u\left( u^{-\frac{1}{2}}-\frac{u^{-2/3}}{2} -\frac{1}{2}u^{-3/2}+\frac{3}{4}u^{-5/2} \right) \\
&g''(u)=&e^u\left(u^{-1/2} -u^{-3/2}+\frac{3}{4}u^{-5/2} \right) \\
&g''(u)=&e^uu^{-5/2}\left( u^2-u+\frac{3}{4} \right) \\
 \\
 \\
\end{align}$$
$\Delta =1^2-4\times \frac{3}{4}=-2<0$, donc pas de racine réelle donc le polynôme est toujours positif donc $g$ est convexe.

$$\begin{align}
&\frac{\delta g}{\delta x}=\frac{e^{x+y}\times \sqrt{ x+y }-\frac{1}{2\sqrt{ x+y }}e^{x+y}}{x+y}=\frac{e^{x+y}\left( \sqrt{ x+y }-\frac{1}{2\sqrt{ x+y }} \right)}{x+y} \\
&\frac{\delta g}{\delta y}=\frac{e^{x+y}\left( \sqrt{ x+y }-\frac{1}{2\sqrt{ x+y }} \right)}{x+y}  \\
&\frac{\delta g}{\delta x}=\frac{\delta g}{\delta y} \\
 \\
&Z=f(a,b)+\frac{\delta f}{\delta x}(a,b)(x-a)+\frac{\delta f}{\delta y}(a,b)(y-b) \\
&Z=e^1+\frac{1}{2}e^1(x-1)+\frac{1}{2}ye^1
\end{align}$$

# Exercice 3

$$\begin{align}
&f(x,y)=xe^y+ye^x \\
&\begin{cases}
xy=1 \\
xe^{1/x}+e^x=0
\end{cases} \\
 \\
&\frac{\delta f}{\delta x}=e^y+ye^x \\
&\frac{\delta f}{\delta y}=xe^y+e^x \\
 \\
&\nabla f=\left( \begin{array}
ee^y+ye^x \\
xe^y+e^x
\end{array} \right) \\
 \\
&\nabla f=0\Leftrightarrow\begin{cases}
e^y+ye^x=0 \\
xe^y+e^x=0
\end{cases}\Leftrightarrow\begin{cases}
e^y=-ye^x \\
xye^x+e^x=0
\end{cases}\Leftrightarrow e^x(1-xy)=0 \\
&\Leftrightarrow xy=1 \Leftrightarrow y=\frac{1}{x} \Leftrightarrow xe^{1/x}+e^x=0
\end{align}$$

$$\begin{align}
&\phi(x)=xe^{1/x}+e^x \\
&\phi'(x)=\frac{e_{1}1}{x}-\frac{e^{1/x}}{x}+e^x \\
&=\frac{e^{1/x}}{#}
\end{align}$$
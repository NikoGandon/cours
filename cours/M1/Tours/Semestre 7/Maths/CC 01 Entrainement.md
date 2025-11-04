---
share_link: https://share.note.sx/nrfmuhl3#PvJ5oET0rQTMRCDIPQVnT6Lz4m6Ossy+i/BjQRHLeuw
share_updated: 2025-11-04T14:51:27+01:00
---
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
>[!error] Erreur sur le calcul de fin, se référer à l'exercice 6


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
&=e^{1/x}+\left( 1-\frac{1}{x} \right)+e^x \\
 \\
&\phi(-1)=-e^{-1}+e^{-1}=0 \\
&\text{ on peut déduire que la seule racine est } -1 \text{ sur } x \in ]-\infty;0[ \\
&1-\frac{1}{x}>0 \text{ car } \frac{1>1}{x} \\
 \\
 \\
&\frac{\delta^2 f}{\delta^2 x}=ye^x=-e^{-1} \\
&\frac{\delta^2 f}{\delta^2 y}=xe^y=-e^{-1} \\
&\frac{\delta^2f}{\delta y \delta x}=e^y+e^x=2e^{-1} \\
&\frac{\delta f}{\delta x \delta y}=e^y+e^x
 \\
 \\
 \\
&H=\left( \begin{array}
-e^{-1} & 2e^{-1} \\
2e^{-1} & -e^{-1}
\end{array} \right) \\
 \\
&\det H=e^{-2}-4e^{-2}=-3e^{-2} \\

\end{align}$$

# Exercice 4

$$\begin{align}
& f(x)=\frac{1}{1+e^x} \\
&Df=\mathbb{R} \\
&f'(x)=\frac{-e^x}{(1+e^x)^2} \\
 \\
 \\
&f''(x)=\frac{-e^x(1+e^x)^2+e^x(2e^{2x}+2e^x)}{(1+e^x)^4} \\
&f''(x)=\frac{e^x(1+e^x)^{\cancel{2}}+\cancel{1+e^x}2e^{2x}}{(1+e^x)^{\cancel{4}3}} \\
&f''(x)=\frac{-e^x(1+e^x)+2e^{2x}}{(1+e^x)^3}=\frac{e^x(e^x-1)}{(1+e^x)^3} \\
\\
&\boxed{f''(x)=\frac{e^x(e^x-1)}{(1+e^x)^3}=\frac{-e^x+e^{2x}}{(1+e^x)^3}}
 \\
 \\
&f''(x)>0\implies e^x-1>0 \\
 \\
&f''(x)<0\implies e^x-1<0 \\
&\implies e^x<1 \\
 \\
&f(x)\text{ convexe sur } ]0;+\infty[ \\
&f(x) \text{ concave sur } ]-\infty,0[ \\
 \\
&f\left( \sum \lambda;x; \right)\leq \sum \lambda; f(x;) \\
 \\
&\text{Soit }n \geq 2, ~~ f(x)\mapsto\mathbb{R} \\
&\text{Une fonction convexe alors } \forall (\lambda_{1},\lambda_{2},\dots,\lambda_{n})\in\mathbb{R}^n_{+} \\
&\text{De plus, } \sum^n_{i=1}\lambda_{i}=1\text{ et } \forall (x_{1},\dots,x_{n}) \in I^n \\
&f\left( \sum^n_{i=1} \lambda_{1}x_{1}\right)\leq \sum^n_{i=1}\lambda_{i_{1}}f(xi)
\end{align}$$

>[!note] Non fini

# Exercice  6

$$\begin{align}
&f:\mathbb{R}^2\to\mathbb{R} \\
&f(x,y)=\frac{3}{2}x^2+y^2-x+2xy-2y+\frac{5}{2} \\
&H=\left( \begin{array}
&3&2 \\
2&2
\end{array} \right) \\
& \frac{1}{2}(x,y)\left( \begin{array}
&3&2 \\
2&2
\end{array} \right)\left(\begin{array}
&x \\
y
\end{array} \right)-(-1,2)\left( \begin{array}
&x \\
y
\end{array} \right)+\frac{5}{2} \\
 \\
&\det\left( \begin{array}
&3-\lambda&2 \\
2&2-\lambda
\end{array} \right)= (3-\lambda)(2-\lambda)-4=\lambda^2-5\lambda2\\
&\delta=17 \\
&x_{1}=\frac{5+\sqrt{ 17 }}{2}\\
&x_{2}=\frac{5-\sqrt{ 17 }}{2}
 \\
 \\
&\nabla f=0\Leftrightarrow\left( \begin{array}
&3x+2y-1 \\
2y+2x-2
\end{array} \right)=0\Leftrightarrow \begin{cases}
3x+2y-1=0 \\
2y+2x-2=0
\end{cases} \\
&\Leftrightarrow \begin{cases}
3x-2x+2-1=0 \\
y=-x+1
\end{cases}\Leftrightarrow\begin{cases}
x=-1 \\
y=0
\end{cases}~~~~(-1;2) \text{ Unique}\\
 \\
 \\ \\
&X^{(K+1)}=X^{(K)}+\alpha W^{(K)} \\
&W^{(K)}=-\nabla f(X^{(K)}) \\
&X^0=(0,0) \\
 \\
&\begin{cases}
3x+2y-1 \\
-2x+2y-2
\end{cases} \\
 \\
 & (0,0)+\left(\begin{array}
\frac{1}{2} \\
1
\end{array}  \right) \\ \\
&X^{(1)}=X^{(0)}+\alpha W^{(0)} \\
 & W^{(0)}=-\nabla f(X^{(0)}) \\
&=-\nabla f(0,0) \\
&=-1\left( \begin{array}
-1 \\
-2
\end{array} \right) \\
&=\left( \begin{array}
&1 \\
2
\end{array} \right) \\
&X^{(1)}=\left(\frac{1}{2},1\right) \\
&X^{(1)}=(0,0)+\frac{1}{2}\left(\begin{array}
1 \\
2
\end{array}\right)=\left( \begin{array}
\frac{1}{2} \\
1
\end{array} \right) \\
&f(X^{(1)})=? \\
 \\
&\text{GPO}, \forall \alpha>0,f(X^{(k)}+\alpha W^{(K)})\leq f(X^{K}+\alpha^*W^{(K)}) \\
&f(x)= \langle \nabla f(U^{(0)}+\alpha U^{(0)})| W^{(0)}\rangle \\
&= \langle \nabla f(\alpha,2\alpha)|(1,2)\rangle \\
\\
&f(\alpha, 2\alpha)\text{ doit être minimisée} \\
&=f_{K}(\alpha)=f(X^{(k)}+\alpha W^{(k)}) \\
 \\
&\text{Minimiser } f(\alpha,2\alpha)=\frac{3}{2}\alpha^2+4\alpha^2-\alpha+4\alpha^4-4\alpha+\frac{5}{2} \\
&=\frac{19}{2}\alpha^2-5\alpha+\frac{5}{2} \\
 \\
 \\
&\Delta=25-4\left( \frac{19}{2} \right)\left( \frac{5}{2} \right)=25-4\left( \frac{95}{4} \right)=25-95=-70<0 \\
&\frac{5}{2\left( \frac{19}{2} \right)}=\frac{5}{19} \\ \\
 \\
&f(\alpha,2\alpha)=19\alpha-5 \\
&19\alpha-5=0 \\
&19\alpha=5 \\
&\alpha=\frac{5}{19} \\
 \\
&\alpha^*=\frac{5}{19}  \\
&X^{(1)}=X^{(0)}+\frac{5}{19W^{(0)}} \\
&f(X^{(1)})=f\left( \frac{5}{19}, \frac{10}{19} \right)
\end{align}$$

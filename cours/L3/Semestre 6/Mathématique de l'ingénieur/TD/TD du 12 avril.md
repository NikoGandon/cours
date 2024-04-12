$f(x,y,z)=(x-2)^2 + (y-1)^2+z^2$
avec la contrainte $x^2+y^2+z^2=1$

$L(\lambda, x, y, z) = \lambda(x^2 + y^2 + z^2 -1) + f(x,y,z)$
$L(\lambda, x, y, z) = \lambda(x^2 + y^2 + z^2 -1) + (x-2)^2 + (y-1)^2+z^2$

$$
\left( 
\begin{array}{c}
\frac{dL}{d \lambda} \\
\frac{dL}{d x} \\
\frac{dL}{d y} \\ 
\frac{dL}{d z} \end{array} \right)
=
\left( 
\begin{array}{c}
x^2+y^2+z^2-1 \\
2x-4+2 \lambda x \\
2y-2+2 \lambda y \\ 
2z+2 \lambda z
\end{array}
\right)
$$

$$
H = 
\left( 
\begin{array}{c}
 0 & 2x & 2y & 2z\\
	 2x & 2+2\lambda & 0 & 0\\
 2y & 0 & 2+2\lambda & 0 \\
2z & 0 & 0 & 2+2\lambda\\
\end{array}
\right)
$$
On cherche les valeurs qui annulent $\frac{dL}{d \lambda} \frac{dL}{d x} \frac{dL}{d y}\frac{dL}{d z}$
$$\begin{cases}
x^2+y^2+z^2=1 \\
x+\lambda x=2 \\
y+\lambda y=1 \\
z+\lambda z = 0  & (4)
\end{cases}
$$
$$
(4)\Leftrightarrow z=0 \text{ ou } \lambda =-1
$$
Si $z=0$ :
$$
\begin{cases}
x^2+y^2=1 \\
x(1+\lambda)=2 \\
y(1+\lambda)=1
\end{cases}
$$
$\lambda \neq -1$
$x=\frac{2}{1+\lambda}$
$y=\frac{1}{1+\lambda}$
$$(1) \Leftrightarrow \frac{5}{(1+\lambda)^2}=1$$
$$\Leftrightarrow 
\begin{cases}
\lambda=-1+\sqrt{ 5 } \\
\text{ou} \\
\lambda = -1 - \sqrt{  5 }
\end{cases}$$
alors
$$
\begin{cases}
x=\frac{2}{\sqrt{ 5 }} =\frac{2\sqrt{ 5 }}{ 5 } \\
y=\frac{1}{\sqrt{ 5 }} = \frac{\sqrt{ 5 }}{5} \\
z=0 \\
\lambda=-1+\sqrt{ 5 }
\end{cases}
$$
$$
\begin{cases}
\lambda = - 1 - \sqrt{ 5 } \\
x = -\frac{2}{\sqrt{ 5 }} \\
y = -\frac{1}{\sqrt{ 5 }} \\
z = 0
\end{cases}$$
$$H=
\left(
\begin{array}{c}
0 & \frac{4}{\sqrt{ 5 }} & \frac{2}{\sqrt{ 5 }}  & 0 \\
\frac{4}{\sqrt{ 5 }} & 2\sqrt{ 5 } & 0 & 0 \\
\frac{2}{\sqrt{ 5 }} & 0 & 2\sqrt{ 5 } & 0 \\
0 & 0 & 0 & 2\sqrt{ 5 } 
\end{array}
\right)$$
$$H=
\left(
\begin{array}{c}
0 & -\frac{4}{\sqrt{ 5 }} & -\frac{2}{\sqrt{ 5 }}  & 0 \\
-\frac{4}{\sqrt{ 5 }} & -2\sqrt{ 5 } & 0 & 0 \\
-\frac{2}{\sqrt{ 5 }} & 0 & -2\sqrt{ 5 } & 0 \\
0 & 0 & 0 & - 2\sqrt{ 5 } 
\end{array}
\right)
$$
Suite : 
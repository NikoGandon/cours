# Exercice 2

Soit $f: \mathbb{R}^2 \to \mathbb{R}$
$f(x,y)= -2x^2-xy-2y^2+12x+4y$

1. Les extrêmes locaux
   Nous dérivons $f$ : 
   $X = \frac{\delta f}{\delta x} = -4x-y+12$ 
   $Y = \frac{\delta f}{\delta y} = -4y-x+4$
   $$\overrightarrow{\text{grad}} f =
   \left( 
   \begin{matrix}
        
        \frac{\delta f}{\delta x} \\
        \frac{\delta f}{\delta y}
      
\end{matrix}
\right)
$$
$$\overrightarrow{\text{grad}}f=0 \Leftrightarrow
\left\{
\begin{matrix}
  -4x-y=-12 \\
  -4y-x=-4
\end{matrix}
\right.
\Leftrightarrow
\left\{
\begin{matrix}
   4x+y=12 \\
   4y-x=4
\end{matrix}
\right.
$$
$$x=
\frac{
\left\|
\begin{matrix}
12 & 1 \\
4 & 4
\end{matrix}
\right\|
}{
\left\|
\begin{matrix}
4 & 1 \\
1 & 4
\end{matrix}
\right\|
} = \frac{44}{15}$$
$$y=
\frac{
\left\|
\begin{matrix}
4 & 12 \\
1 & 4
\end{matrix}
\right\|
}{
\left\|
\begin{matrix}
4 & 12 \\
1 & 4
\end{matrix}
\right\|
} = \frac{4}{15}$$
$$(1) \left\{
\begin{matrix}
  ax+by+cz=\alpha \\
  a'x + b'y + c'z = \beta \\
  a''x + b''y + c''z = \phi
\end{matrix}
\right.
$$
$$(1) \Leftrightarrow AX = B
\Leftrightarrow X=A^{-1}.B
$$
$$A=\left(
\begin{matrix}
a & b & c \\
a' & b' & c' \\
a'' & b'' & c''
\end{matrix}
\right)$$
$$B=\left(
\begin{matrix}
  \alpha \\
  \beta \\
  \Phi
\end{matrix}
\right)$$
$$X=
\left(
\begin{matrix}
  x \\
y \\
z
\end{matrix}
\right)
$$
$$H=
\left( 
\begin{matrix}
 \frac{\delta^{2} f}{\delta x^{2}} & \frac{\delta}{\delta x}\left(\frac{\delta f}{\delta y}\right) \\
\frac{\delta^{2} f}{\delta y \delta x}  & \frac{\delta^{2} f}{\delta y^{2}}
\end{matrix}
\right)=
\left(
\begin{matrix}
  -4 & -1 \\
-1 & -4
\end{matrix}
\right)$$
$$\left\{
\begin{matrix}
\text{det} \left(
\frac{
\delta^{2}f}{\delta x^{2}}
\right)=-4 =\det_{1}\\
\text{det} \left(
H
\right)=-15=\det_{2}
\end{matrix}
\right.$$
$$\left\{
\begin{matrix}
(-1)^1 \times det_{1} = 4\\
(-1)^2 \times \det_{2} = 15
\end{matrix}
\right.$$

   
2. Les extrêmes locaux lorsque $x$ et $y$ sont liés par la relation $2x+y=1$ 
   $$L(x,y,\lambda)=-2x^2-xy-2y^2+12x+4y+\lambda(2x+y-1)$$
   $$\overrightarrow{\text{grad}}L =
   \left(
     \begin{matrix}
       2x + y - 1 &&&\frac{\delta L}{\delta \lambda} \\
       -4x - y + 12 + 2\lambda &&&\frac{\delta L}{\delta x} \\
       -x - 4y + 4 + 1 &&&\frac{\delta L}{\delta y}
     \end{matrix}
   \right)
   $$
On cherche les racines des $\overrightarrow{\text{grad}}L$ :
$$\left\{
\begin{matrix}
2x+y=1 \\
4x+y-2\lambda = 12 \\
x+4y-\lambda = 4
\end{matrix}
\right.$$

Calcul de $x$ et $y$ :
$$
\left\{
	\begin{matrix}
      2x+y=1 \\
      2x-2y=4
    \end{matrix}
\right.
$$
$$
\left\{
	\begin{matrix}
      8y=-3 \\
      2x=\frac{11}{8}
    \end{matrix}
\right.
\Leftrightarrow
\left\{
	\begin{matrix}
      y=-\frac{3}{8} \\
      x=\frac{11}{16}
    \end{matrix}
\right.
$$
$$x+4y-\lambda
\Leftrightarrow \lambda = 4 - \frac{11}{16} + \frac{3}{2} = -\frac{43}{16}$$

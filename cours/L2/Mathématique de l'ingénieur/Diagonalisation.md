## Diagonalisation et matrices diagonales
### 1. Motivation
$$
\begin{pmatrix}
a_1&0&\dots&0 \\ 0&a_2&\ddots&\vdots \\\vdots&\ddots&\ddots&0 \\
0&\dots&0&a_n \\
\end{pmatrix}
\begin{pmatrix}
b_1&0&\dots&0 \\ 0&b_2&\ddots&\vdots \\\vdots&\ddots&\ddots&0 \\
0&\dots&0&b_n \\
\end{pmatrix}=
\begin{pmatrix}
a_1b1&0&\dots&0 \\ 0&a_2b_2&\ddots&\vdots \\\vdots&\ddots&\ddots&0 \\
0&\dots&0&a_nb_n \\
\end{pmatrix}
$$
On déduit par réccurence :
$$
\begin{pmatrix}
a_1&0&\dots&0 \\ 0&a_2&\ddots&\vdots \\\vdots&\ddots&\ddots&0 \\
0&\dots&0&a_n \\
\end{pmatrix}^N=
\begin{pmatrix}
a_1^N&0&\dots&0 \\ 0&a_2^N&\ddots&\vdots \\\vdots&\ddots&\ddots&0 \\
0&\dots&0&a_n^N \\
\end{pmatrix}$$
#### Héridité
Soit $N\in\mathbb{N}$, on suppose que 
$$A^N=
\begin{pmatrix}
a_1^N&0\\\ddots\\0&a_n^N
\end{pmatrix}$$
On montre que 
$$A^{N+1}=
\begin{pmatrix}
a_1^{N+1}&0\\\ddots\\0&a_n^{N+1}
\end{pmatrix}
$$
$$A^{N+1}=A^N\times A = 
\begin{pmatrix}
a_1^N&0\\\ddots\\0&a_n^N
\end{pmatrix}\times
\begin{pmatrix}
a_1&0\\\ddots\\0&a_n
\end{pmatrix}=
A^N=
A^{N+1}=
\begin{pmatrix}
a_1^{N+1}&0\\\ddots\\0&a_n^{N+1}
\end{pmatrix}$$
## 2. Définition et résultat: 
Soit $A\in\mathbb{M}_n(\mathbb{R})$, $A$ est diagonisable si et seulement si il existe une base $\{v_2\dots v_n\}$ de $\mathbb{R}^n$  tel qie chaque $v_i$ est une valeur propre de A.
Si $f$ est une application linéaire, $f$ est diagonalisable si on peut trouver une base de $\mathbb{R}^n$ formée de veteur propre de $f$.
$$f(v_1)=\lambda;v;$$
Si $A$ est la matrice représentative de $f$ dans une base quelconque, alors
$f$ est diagonalisable $\Leftrightarrow$ $A$ est diagonalisable

### Exemple :
$$A = 
\begin{pmatrix}
7&-5\\10&-8
\end{pmatrix}
$$
$A$ admet $2$ et $-3$ comme valeur propre.
$$
  \begin{align}
    E_2 &= \begin{bmatrix}
           1\\1
         \end{bmatrix}
  \end{align}
$$
$$  \begin{align}
    E_3 &= \begin{bmatrix}
           1\\2
         \end{bmatrix}
  \end{align}
  $$
  Soit $B=\bigg\{\begin{pmatrix}1\\1\end{pmatrix},\begin{pmatrix}1\\2\end{pmatrix}\bigg\}$
  $B$ forme une base de $\mathbb{R}^2$ donc $A$ est diagonalisable.
  $$\begin{pmatrix}1&1\\1&2\end{pmatrix}\rightarrow\begin{pmatrix}1&1\\0&1\end{pmatrix} L_2-L_1$$
  On a gardé tous les vecteurs donc le rg est maximal.
  Donc $\begin{pmatrix}1\\1\end{pmatrix}\begin{pmatrix}1\\2\end{pmatrix}$ sont indépendants.

Montrons que $\bigg\{\begin{pmatrix}1\\1\end{pmatrix},\begin{pmatrix}1\\1\end{pmatrix}\bigg\}$  est une famille générationnelle de $\mathbb{R}^2$.
$$\begin{pmatrix}x\\y\end{pmatrix}=\alpha\begin{pmatrix}1\\1\end{pmatrix}+\beta\begin{pmatrix}1\\2\end{pmatrix}$$

$$
\begin{equation}
    \begin{cases}
      \alpha+\beta=x\\
      \alpha+2\beta=y
    \end{cases}       
\end{equation}
$$
$$\begin{equation}
	\begin{cases}
      \alpha+\beta=x\\
      0\beta=y-x
    \end{cases}       
\end{equation}
$$
$$
\begin{equation}
	\begin{cases}
      \alpha = x-(y-x)=2x-y\\
      \beta=y-x
    \end{cases}       
\end{equation}$$

Donc $\bigg\{\begin{pmatrix}1\\1\end{pmatrix}, \begin{pmatrix}1\\2\end{pmatrix}\bigg\}$ est une famille génératrice de $\mathbb{R}^2$.
- $\bigg\{\begin{pmatrix}1\\1\end{pmatrix}, \begin{pmatrix}1\\2\end{pmatrix}\bigg\}$ est indépendant et génératrice de $\mathbb{R}^2$ donc elle forme une base de $\mathbb{R}^2$ 
- $dim\mathbb{R}^2={card}\bigg\{\begin{pmatrix}1\\1\end{pmatrix}, \begin{pmatrix}1\\2\end{pmatrix}\bigg\}=2$
	De plus $\bigg\{\begin{pmatrix}1\\1\end{pmatrix}, \begin{pmatrix}1\\2\end{pmatrix}\bigg\}$ est indépendante, donc $\bigg\{\begin{pmatrix}1\\1\end{pmatrix}, \begin{pmatrix}1\\2\end{pmatrix}\bigg\}$ forme est une base de $\mathbb{R}^2$. 

  ### Théorème
  Soit $A \in \mathbb{M}_n(\mathbb{R})$ est diagonalisable alors ils existent une matrice $P$ inversible et une matrice diagonale $D$ tel que $$A=PDP^{-1}$$
  ### Démonstration
  $A$ est daigonalisable donc il existe $\{v_1\dots v_n\}$ de vecteur propre de $A$ qui forme une base de $\mathbb{R}^n$.
  On considère l'application linéaire telle que $A$ est sa matrice représentative dans la base canonique.
  $e_1=(1,0,\dots,0), e_i=(\dots,1,0)$  (à la position $i$)
  $$\begin{pmatrix}
  \lambda_1&0&\dots \\
  0&\lambda_2&\vdots \\
  0&\dots&\ddots \\
  0&0&\lambda_n
\end{pmatrix}$$

$$f(v)=(Av)$$
$$f(v_1)=(Av_i)=\lambda v_1=\lambda_1v_1+0v_2+\dots+0v_n
=
\begin{pmatrix}\lambda_1\\0\\\vdots\\0\end{pmatrix}_{b}$$
$$f(v_2)=(Av_i)=0v_1=\lambda_2v_1+0v_2+\dots+0v_n
=
\begin{pmatrix}0\\\lambda_2\\0\\\vdots\\0\end{pmatrix}_{b}$$
$f$ admet $A$ comme présentative dans la base canonique et admet $diag(\lambda_1\dots\lambda_n)=D$ comme representation dans la base $\{v_1\dots v_n\}$ donc il existe une matrice de passage tel que $A=PDP^{-1}$ 
$$
\begin{pmatrix}
7&-5\\10&-8
\end{pmatrix}$$
$$f(x,y)= (7x - 5y; 10x-8y)$$
$\alpha\in\mathbb{R}$ et $v_1, v_2\in\mathbb{R}$ , $(x_1,y_1)(x_2,y_2)$
$$f(\alpha v_2+v_1)=\alpha f(v_1)+f(v_2)$$
$$f(\alpha x_1+x_2, \alpha y_1 + y_2)=(7(\alpha x_1+x_2)-5(\alpha y_1 + y_2); 10(\alpha x_1+x_2) - 8(\alpha y_1 + y_2)$$ $= \alpha f(...)$ (impossible de déchiffrer le tableau..)

$$f(1,0)=(7,10)$$ $$f(0,1)=(-5, -8)$$
$$M_{f, BC}=A=
\begin{pmatrix}
7&-5\\10&-8
\end{pmatrix}$$
$$B = \bigg\{
\begin{pmatrix}
	1\\1
\end{pmatrix},
\begin{pmatrix}
	1\\0
\end{pmatrix}
\bigg\} = \alpha\begin{pmatrix}1\\1\end{pmatrix}+\beta\begin{pmatrix}1\\0\end{pmatrix}=2\begin{pmatrix}1\\1\end{pmatrix}+0\begin{pmatrix}1\\0\end{pmatrix}=\begin{pmatrix}2\\0\end{pmatrix}$$
...
$$M_{f,b_2}=\begin{pmatrix}2&10\\0&-3\end{pmatrix}$$
En sachant que la première colonne $f\begin{pmatrix}1\\1\end{pmatrix}$ et la deuxième est $f\begin{pmatrix}1\\0\end{pmatrix}$.




//le cours du 17/03 n'a pas pu être pris

- $A$ est diagonalisable si $\mathbb{R}^n$ admet une base de vecteur propre de $A$.
- $A$ est [[Matrice diagonalisable|diagonalisable]] :
	$$A=\begin{pmatrix}
\vdots &   & \vdots \\
v_{1} & \dots  & v_{n} \\
\vdots &  & \vdots
\end{pmatrix}
\begin{pmatrix}
\lambda_{1}  &   &  \\
& \ddots  &  \\
& & \lambda_{n}
\end{pmatrix}
\begin{pmatrix} \\
\vdots &  & \vdots \\
v_{2}
\end{pmatrix}
$$

Soit une urne contenant 10 boules dont :
- 4 blanches
- 2 noires
- 6 rouges
On tire 3 boules de façon exhaustive et simultanément.
Soit $V=(X,Y)$ le couple de variable tel que $X$ le nombre de boule blanche et $Y$ le nombre de boule noire.
$$P((X=2; Y=0))=\frac{6\times1\times4}{120}=\frac{24}{120}$$
$$P((X=0; Y=2))=\frac{1\times1\times4}{120}=\frac{4}{120}$$
$$P((X=1;Y=2))=\frac{4\times1\times1}{120}=\frac{4}{120}=\frac{1}{30}$$
$$P((X=3;Y=0))=\frac{4\times1\times1}{120}=\frac{4}{120}=\frac{1}{30}$$
<h2>Exercice 14</h2>
$$P(-1, 0)=\frac{1}{10}$$
$$P(X=-1)=\frac{2}{5}, P(Y=0)=\frac{2}{5}$$
<h2>Exercice 13</h2>
Soit 2 dés $A$ et $B$, $A$ a toutes ses faces équiprobables et porte le nombre $1$ sur 4 de ses faces et $-2$ sur les autres.
Le dé $B$ porte les valeurs $-2, -1, 0, 1, 2, 3$ mais n'est pas équilibré.
Les probabilités d'apparition forment une suite géométrique de raison $\frac{1}{2}$.
1) Les probabilités de la face de $B$ sont :
		$$P_b(Y_b=-2)=\alpha\Leftrightarrow P_b(Y_b=-1)=\times\frac{\alpha}{2}\Leftrightarrow P_b(Y_b=0) =\times\frac{\alpha}{4}$$
		$$P_b(Y_b=1)=\frac{\alpha}{8}\Leftrightarrow P_b(Y_b=2)=\frac{\alpha}{16}\Leftrightarrow P_b(Y_b=3)=\frac{\alpha}{32}$$
		$$\sum_{n=-2}^{3}P_b(Y_b=n)=1$$
		$$\Leftrightarrow a\bigg(+\frac{1}{2}+\frac{1}{4}+\frac{1}{8}+\frac{1}{16}+\frac{1}{32}\bigg)=1$$
		$$\Leftrightarrow a\lgroup\frac{32}{1+2+4+8+16+32}\rgroup=\frac{32}{63}$$
1. La loi du couple $(X,Y)$:
|X/Y| -2 | -1 | 0 | 1 | 2 | 3 |
| :--------------- | --------------- | --------------- | --------------- | --------------- | --------------- |---------------: |
|-2|4|3|2|1|0|1|
|1|1|0|1|2|3|4|

|X/Y| 0 | 1 | 2 | 3 | 4 | Total |
| :--------------- | --------------- | --------------- | --------------- | --------------- | --------------- |---------------: |
|-2|$\frac{2}{189}$ |$\frac{5}{189}$|$\frac{8}{189}$|$\frac{16}{189}$|$\frac{32}{189}$|$\frac{64}{189}$|$\frac{63}{189}=\frac{1}{3}$|
|1|$\frac{32}{189}$|$\frac{80}{189}$|$\frac{8}{189}$|$\frac{4}{189}$|$\frac{2}{189}$|$\frac{126}{189}=\frac{2}{3}$|
|Total|$\frac{34}{189}$|$\frac{85}{189}$|$\frac{16}{189}$|$\frac{20}{189}$|$\frac{34}{189}$|1/1|



3. La loi marginale de $Y$:
|$Y_j$ | 0 | 1 | 2 | 3 | 4 | Total |
| :--------------- | --------------- | --------------- | --------------- | --------------- | --------------- |---------------: |
|$P(Y=y_j)$ |$\frac{34}{189}$|$\frac{84}{189}$ |$\frac{16}{189}$|$\frac{20}{189}$|$\frac{34}{189}$|1|
4.  Les variables ne sont pas indépendantes :
$$P((X=-2)\cap(Y=0))=\frac{2}{189}$$
$$P(X=-2) \times P(Y=0) = \frac{34}{567}$$
<h2>Exercice 15</h2>
Soit $f$ la fonction de $\mathbb{R}$ dans $\mathbb{R}$ tel que 
$$f(x)= \bigg\lbrace$$


<h2>Exercice 5</h2>
20 sujets dont 12 révisés et 8 non révisés :
|$x_i$ |0|1|2|3|Total|
|:----- | ------ | ------ | -------| -------| -----:|
|$P(x_i)$|$\frac{14}{57}$|$\frac{28}{95}$|$\frac{44}{95}$|$\frac{11}{57}$|0|
$Card(A)=C^3_{20}=\binom{20}{3}=\frac{20!}{3!(20-3)!}=\frac{20\times19\times18}{3\times2}=\frac{10\times19\times18}{3}=10\times19\times6=1140$
$P(X=0)=\frac{C^7_8}{C^3_20}=\frac{\frac{8\times7\times6}{3\times2}}{1140}=\frac{8*7}{1140}=\frac{14}{57}$
$P(X=1)=\frac{C^2_8\times C^1_{12}}{C^3_{20}}=\frac{28}{95}$
$P(X=2)=\frac{C^1_8\times C^2_{12}}{C^3_{20}}=\frac{44}{95}$
$P(X=3)=\frac{C^3_{12}}{C^3_{20}}=\frac{11}{57}$
$P($Total$)=\frac{14}{57}+\frac{28}{95}+\frac{44}{95}+\frac{11}{57}=\frac{25}{57}+\frac{72}{95}=\frac{25}{3\times{19}}+\frac{72}{5\times{19}}=\frac{125+}{5\times{3}\times{19}}$  

<h2>Exercice 11</h2>
Soit $f$ la fonction définit sur $\mathbb{R}$ par $f(x)=k\times{exp(-|x|)}$. 
1) Pour déterminer $k$:
$$
\int^{+\infty}_{-\infty}k.e^{-|x|}dx=k\int^{+\infty}_{-\infty}e^{-|x|}dx=k\int^{0}_{-\infty}e^{-x}dx+\int^{+\infty}_{0}e^{-x}dx$$
Donc :
$$=k\bigg(\bigg[e^x\bigg]^0_{-\infty}+\bigg[e^x\bigg]^{+\infty}_0\bigg)$$
D'où :
$$k((1-\lim_{x\rightarrow-\infty}e^x)+(0-(-1))=2k$$
On conclut que $2k=1$, $k=\frac{1}{2}$.
2) La fonction de répartition de $X$ est :
   $$F(x)=\int^{+\infty}_{-\infty}{f(t)dt}=\frac{1}{2}\int^{+\infty}_{-\infty}{e^{-|t|}}$$
   Où $X\leq0$:
   $$F(x)=\frac{1}{2}\int^{x}_{-\infty}{e^tdt}=\frac{1}{2}\bigg[e^t\bigg]^x_{-\infty}=\frac{1}{2}e^x$$
	Où $x\geq0$ :
	$$\int^{x}_{0}{f(t)dt}=\frac{1}{2}\int^{+\infty}_{-\infty}{e^{-|t|}dt}$$
	$$=\frac{1}{2}\int^{x}_{0}{e^{-t}}=\frac{1}{2}\bigg[-e^{-t}\bigg]^x_0$$
$$=\frac{1}{2}\bigg(-e^{-x}+e^0\bigg)=\frac{1}{2}\bigg(1-e^{-t}\bigg)$$
	Donc on a :
	$$F(x)=\int^{0}_{-\infty}{f(t)dt}+\int^{x}_{0}{f(t)dt}$$$$=\frac{1}{2}e^0+\frac{1}{2}(1-e^{-x})=1-\frac{1}{2}e^{-x}$$$$F(x)=1-\frac{1}{2}e^{-x}$$
	
3) Soit $Y=X^2$, la répartition et la densité de $Y$ est :
	
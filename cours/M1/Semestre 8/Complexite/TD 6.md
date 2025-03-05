# Exercice 1

$|x| =\text{nombre de bits pour représenter (i.e. encoder) le nombre } x$
En binaire (base 2), il faut $\log_{2}(x)$ bits pour représenter $x$.

$|x| = \log_{2}(x)$

>[!info] Rappel
>$\log_{b}a=\frac{\log_{c}a}{\log_{c}b}$
>
>Pour $b$ et $c$ des constantes, $\log_{b}a$ et $\log_{c}b$ différents au plus d'une constante multi???


$$\begin{aligned} 101101 \\ +~~~ 001110 \\ \hline 111011 \end{aligned}$$

Notons $x[i]$ le $i$ ème bit de $x$ où $x[i]$ est le bit de poids faible

```
addition(x,y):
	var <- 0
	pour i de 1 à max(|x|, |y|) faire :
		res[i] <- (x[i] + y[i] + var)
		si x[i] + y[i] + var >= 2 alors :
			var <- 1
		sinon :
			var <- 0
```

<u>Complexité de l'algo</u> :

Soit $k=max(|x|,|y|)$ la complexité est $\mathcal{O}(k)=\mathcal{O}(max(|x|,|y|))=\mathcal{O}(\max(\log(x), \log(y)))=\mathcal{O}(\log (x)+\log (y))$, donc c'est polynomiale en la taille de l'entrée.


```
AddLineaire(x,y):
	pour i de 1 à x faire :
		res[i] <- 1
	pour i de 1 à y faire :
		res[x+i] <- 1
	retourne res
```

<u>Complexité de l'algo</u> :

$\mathcal{O}(x+y)$ qui est linéaire par la taille de l'entrée si $x$ et $y$ sont représenté en linéaire (ce qui n'est pas un encodage raisonnable).

Mais si $x$ et $y$ sont représentés en binaire alors la complexité de l'algo reste $\mathcal{O}(x+y)$ ce qui n'est plus linéaire, mais expérimental en la taille de l'entrée. 

>[!info] 
>Taille de l'entrée (lorsqu'elle est en binaire) $\log(x)+\log(y)$ complexité $\mathcal{O}(2^{\log(x)}+2^{\log(y)})$


# Exercice 2

Le problème du sac à dos :

<u>Entrée</u> :
- Poids $p_{1}, p_{2}, \dots, p_{n}$ des $n$ objets
- Valeurs $v_{1}, v_{2}, \dots, v_{n}$ des $n$ objets
- Capacité $W \in \mathbb{N}$

<u>Sortie</u> :
$S \subseteq \{ 1,\dots,n \}$ qui maximise la valeur des objets choisis dans $S$ et tel que la somme des poids des objets de $S$ n'excède pas $W$.

```
solve_KS(p_1,...,p_n, v_1, ..., v_n, W):
	pour j de 0 à W faire :
		...                 // O(W)
	pour i de 1 à n faire :
		pour j de 0 à W faire :
			...             // O(n x W)
```

Alors le temps d'exécution est $\mathcal{O}(n\times W)$

> Combien de bits sont nécessaires pour représenter une entrée (ou une instance) du problème ?

$$
\begin{aligned}
&\log_{2}(p_{1})+\dots+\log_{2}(p_{n})+\log_{2}(v_{1})+\dots+\log_{2}(v_{n})+\log(W) \\  \\
&\leq n\times \log(\underset{1\leq i\leq n}{\max(p_{i})})+n \times \log(\underset{1\leq i\leq n}{\max(v_{i})}) + \log(W) \\  \\
&\leq n \times \left[ \log(\max p_{i}) + \log(\max v_{i}) \right] + \log(W)
\end{aligned}
$$

$\mathcal{O}(n \times W)$ n'est pas polynomial. Il l'est uniquement si les données numériques sont représentées en unaire (qui n'est pas ??).
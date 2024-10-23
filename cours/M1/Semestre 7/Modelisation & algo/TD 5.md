# Exercice 1

Soit $n=20$, on a en moyenne $n^2=20^2=400$ paquets

Au début, la probabilités d'obtenir une nouvelle vignette est grande

Mais si on possède déjà beaucoup de vignettes, alors la proba d'en obtenir une nouvelle devient petite.

Par exemple, si on a déjà $n-1$ vignettes, alors la proba de trouver la vignette manquante dans un paquet est $\frac{1}{n}$

Soit $X$ la **variable aléatoire** définie ainsi :
$X=\text{nombre de paquet à acheter pour constituer la collection complète des n vignettes}$
Le nombre attendu de paquets à acheter est donné par l'espérance mathématique de $X$

```desmos-graph
left=-1;right=11;
bottom = -1;top = 6;
---
(1,1)
(2,2)
(3,2)
(4,3)
(5,3)
(6,3)
(7,3)
(8,4)
(9,5)
(10,5)
```


Si on a collecté $y$ vignettes, la proba d'en obtenir une nouvelle dans le prochain paquet est $p=\frac{n-j}{n}$

Pour faciliter le calcul de $E(X)$, on remplace $X$ par une somme de variables aléatoires :
Soit $X_{j}$ le nombre de paquets achetés entre le moment où l'on a $j$ vignettes et celui où l'on a $j+1$

Donc $X=X_{1}+X_{2}+\dots+X_{n-1}$

$E(X)=E\left( \overset{n+1}{\underset{j=0}{\sum}}  X_{i} \right) = E\left( \overset{n+1}{\underset{j=0}{\sum }}X_{j} \right)$

Par définition de l'espacement :

$$E(X_{j}) = \sum^{+\infty}_{k=0} k \times p(X_{j}=k)=\sum^{+\infty}_{k=0} k \times(1-p)^{k-1}\times p$$
Théorème : $\overset{+\infty}{\underset{k=1}{\sum}}k\times(1-p)^k=\frac{1-p}{p^2}$

>[!info] 
>Ce théorème peut être dans l'examen

Ainsi, $$
\begin{align}
E(X_{j})=\frac{p}{1-p}\times \sum^{+\infty}_{k=1}k \times (1-p)^k \\
=\frac{p}{p}\times \frac{1-p}{p^2}\times \frac{1}{p}=\frac{n}{n-j}
\end{align}
$$
Donc
$$E(X)=\sum^{n-1}_{j=0}E(X_{j})=\sum^{n-1}_{j=0} \frac{n}{n-j}=n \sum^{n-1}_{j = 0} \frac{1}{n-j}$$

Pour la culture :
$H(n)=\overset{n}{\underset{i=1}{\sum}} \frac{1}{i}$ est le n-ième nombre de la série harmonique.

# Exercice 2



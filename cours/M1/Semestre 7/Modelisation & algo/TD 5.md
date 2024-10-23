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
$$E(X)=\sum^{n-1}_{j=0}E(X_{j})=\sum^{n-1}_{j=0} \frac{n}{n-j}=n \sum^{n-1}_{j = 0} \frac{1}{n-j}= n \sum^{n-1}_{i=1} \frac{1}{i} \approx n \times \ln(n)$$

Pour la culture :
$H(n)=\overset{n}{\underset{i=1}{\sum}} \frac{1}{i}$ est le n-ième nombre de la série harmonique.

$$\sum^{n}_{i=1} ~ \int^{n}_{i=1} \frac{1}{i}\, di =\frac{1}{1}+ \frac{1}{2}+ \frac{1}{3} + \dots$$

```dataviewjs
const labels = ['0-1', '1-2', '2-3', '3-4', '4-5', '5-6'];
const data = [0, 100, 50, 33, 25, 20];

const chartData = {  
    type: 'bar',

    data: {
        labels: labels,
        datasets: [{
            label: 'Numbers',
            data: data,
            backgroundColor: '#FFB1C1',
        }]
    }
}

window.renderChart(chartData, this.container);
```



$$\int \frac{1}{x}=\ln(x)$$
$$\int^{n}_{1} \frac{1}{x}\leq \sum^{n}_{i=1} \frac{1}{i} \leq \int^{n+1}_{2} \frac{1}{x-1}$$
# Exercice 2

1. Le temps d'exécution au pire des cas de l'algorithme est $\mathcal{O}$
   $\overset{n}{\underset{i=1}{\sum}}i= \frac{n(n-1)}{2}$
2. Le temps d'exécution est XXX.
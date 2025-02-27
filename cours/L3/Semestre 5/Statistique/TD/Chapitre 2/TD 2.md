---
quickshare-date: 26-10-2023 22:15:40
quickshare-url: https://noteshare.space/note/clo7mjcrv524201mwh5vc16en#313BxdFXZRHI3+OIkwUbs7tVzLY+gfUUgJw4CwZntdY
---
tags:
  - Maths
  - Probabilités
---


# Exercice 1
Fer Blanc : $X \leadsto \mathcal{N}(0.5,0.05)$
Papier : $Y\leadsto\mathcal{N}(0.05,0.02)$

$P(Epaisseur)$ entre $26.67$ et $28.58$
$50X\leadsto\mathcal{N}(2.5,0.25)$
$49Y\leadsto\mathcal{N}(2.45,0.58)$
$Z=50X+49Y$
$P(26.67\leq Z\leq 28.58)$ ?
$\sigma(X_{j})=0.05\times 5\sqrt{ 2 }=0.25\sqrt{2}$
$\sigma(Y_{p})=\sqrt{ 49\sigma^2(Y_{i})  }$
$\sigma(Y_{p})=7\times\sigma(Y_{i})$
$=7\times{0.02}=0.14$
$\sigma ^2  (Z)=\sigma^{2}(X_{j})+\sigma^{2}(Y_{P})$
$=0.25^2\times2+0.14^2$
$=0.321$
$Z\leadsto\mathcal{N}(27.45,\sqrt{ 0.321 })$
$$P(26.67\leq 28.58)=P(26.67-27.45\leq\mathcal{N}(0,\sqrt{ 0.321 })\leq(28.58-27.41))$$
$$=P(-0.78)\leq\mathcal{N}(0, \sqrt{ 0.321 }\leq 1.13)$$
$$=P(\frac{-0.78}{\sqrt{ 0.321 }}\leq\mathcal{N}(0,1)\leq \frac{1.13}{\sqrt{ 0.321 }})$$
$$=P(-1.377\leq\mathcal{N}(0,1)\leq 1.994)$$
$$=\Pi(1.994)-\Pi(-1.377)$$
$$=\Pi(1.994)-(1-\Pi(1.377))$$
$$=0.9767-1+0.9147=0.8914$$

# Exercice 1
On sait que le fer blanc sera la variable $X \leadsto \mathcal{N}(0.5,0.05)$
On sait que le papier sera la variable $Y \leadsto \mathcal{N}(0.05,0.02)$
$50X = (50 \times 0.5, \sqrt{ 50 \times 0.05^2})=(25,0.35)$
$49Y = (49 \times 0.05, \sqrt{ 49 \times 0.02^2})=(2.45,0.14)$
Soit $Z$ l'épaisseur de 50 fers blancs et 49 papiers
$Z=50X+49Y$
$P(26.67 \leq Z \leq 28.58)$ ?

$Z \leadsto \mathcal{N}(25 + 2.45, \sqrt{ 0.35^2 + 0.14^2}) \Leftrightarrow Z \leadsto \mathcal{N}(27.25,0.38)$

$26.67 \leq \mathcal{N}(27.25,0.38) \leq 28.58$
$26.67-27.45 \leq \mathcal{N}(0,0.38) \leq 28.58-27.45$
$\Leftrightarrow \frac{-0.78}{0.38}\leq \mathcal{N}(0,1) \leq \frac{1.13}{0.38}$
$\Leftrightarrow \Pi(-2.05)\leq \mathcal{N}(0,1) \leq \Pi(2.97)$
$\Leftrightarrow 1 - \Pi(2.05) \leq \mathcal{N}(0,1) \leq \Pi(2.97)$
$\Leftrightarrow 0.9905 - (1 - \Pi(2.05))-(1-0.9793)$
$\Leftrightarrow 0.9905 - 0.0207 = 0.9698$

# Exercice 2

En moyenne 3% des articles produits par une machine sont défectueux.
On doit trouver la probabilité $P$ qu'il y ait plus de 4 pièces défectueux dans un lot de 100 pièces choisis au hasard
1) Approximation par la loi de Poisson
	 $X \leadsto \mathcal{P}(3)$
	 $P(X\leq 4)$
	 $\Leftrightarrow P(X=4) + P(X=3) + P(X=2)+P(X=1)+P(X=0)$
	 $\Leftrightarrow \frac{3^4*e^{-3}}{4!}+\frac{3^3*e^{-3}}{3!}+\frac{3^2*e^{-3}}{2!}+3*e^{-3}+e^{-3}$
	 $\Leftrightarrow \frac{81\times e^{-3}}{24}+\frac{27 \times e^{-3}}{6}+\frac{9 \times e^{-3}}{2}+3\times e^{-3}+e^{-3}$
	 $\Leftrightarrow 0.1680+0.0224+0.0224+0.1494+0.0498=0.8152$
   
2) Approximation par la loi normale
	$X \leadsto \mathcal{N}(3, 1.7)$


# Exercice 3

Il peut y avoir max $97$ personnes, en sachant qu'en moyenne $4\%$ annule leur réservation.
Elle décide donc d'accepter $100$ personnes.
$X \leadsto \mathcal{B}(100, 0.96)$
$1-\sum^{100}_{i=98}(P(X=i))$
$\Leftrightarrow 1-(P(X=98)+P(X=99)+P(X=100))$
On utilise la loi normale comme approximation
$E(x)=96, \sigma=\sqrt{ v\times p \times  q }=1.95$
$P(X \leq 97)= \Pi\left( \frac{97.5-96}{1.95} \right)= \Pi(0.76)=0.7764$

# Exercice 4

Soit $X$ la variable suivant une loi normale de paramètre $m$ et $\sigma$,
$X \leadsto \mathcal{N}(m, \sigma)$
On sait que les insectes dont la durée de vie est $\geq 31$ jours représentent $11.90\%$ de la population, ceux dont la durée de vie est $\leq 25$ jours représentent $37.45\%$.

On sait que $m$ représentent l'espérance de la variable, $\sigma$ représente l'écart-type.
On peut déduire que ceux qui vivent $\geq 26$ jours et $\leq 30$ jours représentent $50.65\%$

```dataviewjs
const labels = ['<=25 jours', '26-30 jours', '>=31 jours'];
const data = [11.9, 50.65, 37.45];

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

On dira que $Z = \frac{x-µ}{\sigma}$
Pour $x = 25$ :
	$Z_{1}=\frac{25-µ}{\sigma}$
Pour $x = 31$:
	$Z_{2}=\frac{31-µ}{\sigma}$

# Exercice 6

1) Soit $X$ suit une loi binomiale
   On cherche $P(X \geq 13)$ :
   $X \leadsto \mathcal{B}(25,0.4)$
   La loi de Poisson ne peut pas être utilisée pour l'approximation : $25 \times 0.4 = 10 \geq 5$
   On peut utiliser la loi normale pour l'approximation.
   $P(X\geq 13)=P(X\geq 12.5)$
   $P(X\geq 12.5)=1-P(X\leq 12.5)$
	   $= 1-P(  \frac{x-10}{\sqrt{ 6 }}\leq \frac{2.5}{\sqrt{ 6 }})$
	Soit $Z = \frac{x-10}{\sqrt{ 6 }}$
	Donc $1-P(Z<1.02)$ 
		$1-0.8461$
		$0.1539$
   
2) Soit $X \leadsto \mathcal{B}(100,0.4)$
   $P(X>50)$
   $\Leftrightarrow P(X \geq 51)$
   $= P(X\geq 50.5)$
   $=1-P(X \leq 50.5)$
   $=1-P(\frac{x-40}{\sqrt{ 24 }}\leq \frac{50.5-40}{\sqrt{ 24 }})$
   $=1- \Pi(\frac{10.5}{\sqrt{ 24 }}) = 1 - \Pi(2.14)$
   $=1-0.9538$
   $=0.0162$
   
3) $P(X\geq \frac{n}{2}+1)=P(X^k \geq \frac{n+1}{2})$
   $$
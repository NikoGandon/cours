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

$26.67 \leq \mathcal{27.25,0.38} \leq 28.58$
$26.67-27.45 \leq \mathcal{N}(0,0.38) \leq 28.58-27.45$
$\Leftrightarrow \frac{-0.78}{0.38}\leq \mathcal{N}(0,1) \leq \frac{1.13}{0.38}$
$\Leftrightarrow \Pi(-2.05)\leq \mathcal{N}(0,1) \leq \Pi(2.97)$
$\Leftrightarrow 1 - \Pi(2.05) \leq \mathcal{N}(0,1) \leq \Pi(2.97)$
$\Leftrightarrow 0.9905 - (1 - \Pi(2.05))-(1-0.9793)$
$\Leftrightarrow 0.9905 - 0.0207 = 0.9698$

# Exercice 4



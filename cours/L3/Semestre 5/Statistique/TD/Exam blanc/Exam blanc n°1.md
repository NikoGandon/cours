# Exercice 1

1) $\rho(X,Y)=\frac{cov(X,Y)}{\sigma(X) \times \sigma(Y)}$
	$cov(X,Y)=\overline{X \times Y}-\overline{X} \times \overline{Y}$
	$= 272,139 - 149.7 \times 1.860$
	$=-6.303$
	$\sigma(X)=Var(X)^2$
	$= \sqrt{ \overline{X^2}-\overline{X}^2}$
	$=\sqrt{ 22640.3-149.7^2 }$
	$=\sqrt{ 230.21 } = 15.17$
	$\sigma(Y)=\sqrt{ 3.7115-1.860^2 }= \sqrt{ 0.2519 } = 0.5018$
	$\rho(X,Y)=(-\frac{6.303}{15.17 \times 0.5018})$
	$\approx-0.82$
	$0.7 \leq | \rho(X,Y) | \leq 1$
	On peut conclure qu'il existe une relation linéaire. Suite à une erreur, les résultats peuvent varier (mauvais cov (qui a été corrigé)).
2) La droite de régression de $X$ en $Y$ est :
	$a=\frac{cov(X,Y)}{Var(Y)}$
	$=\frac{-6.303}{0.2519}$
	$\approx-25.02$
	$b = \overline{X} - a \times \overline{Y}=149.7+25.02 \times 1.860=196$
	$f(x)=ax+b=-25.02x+196$
	$f(2.4)=-25.02 \times 2.4 + 196=135.952$

# Exercice 2

1) Soit une variable $X$ suivant la loi normale telle que $X \leadsto \mathcal{N}(22; 0.025)$
	Les pièces sont acceptables si elles ont un diamètre compris entre 21.95 et 22.05
	On sait qu'au cours d'une journée est produit plusieurs milliers de pièces
	$P(21.95 \leq X \leq 22.05)$ ?
	$=21.95 \leq \mathcal{N}(22;0.025)) \leq 22.05$
	$=21.95-22 \leq \mathcal{N}(0;0.025) \leq 22.05-22$
	$=-0.05 \leq \mathcal{N}(0;0.025) \leq 0.05$
	$=P(-\frac{0.05}{0.025}\leq \mathcal{N}(0;1) \leq \frac{0.05}{0.025})$
	$=P(-2 \leq \mathcal{N}(0;1) \leq 2)$
	$=1-\Pi(2)\leq \mathcal{N}(0;1) \leq \Pi(2)$
	$=1-0.9772 \leq \mathcal{N}(0;1) \leq 0.9772$
	$=0.0228\leq \mathcal{N}(0;1) \leq 0.9772$
	$0.9772-0.0228=0.9544$

2) 
	1) La loi suivi par $Y$ est la loi binomiale telle que $Y \leadsto \mathcal{B}(80;0.05)$
		La moyenne de cette loi est $80 \times 0.05=4$
		$\sigma=\sqrt{ 80 \times 0.05 \times 0.95 } \approx 1.95$
	2) La loi pouvant être utilisée par $Y$ pour l'approximation est la loi de Poisson
		$Y \leadsto \mathcal{P}(4)$
		$P(Y \leq 6)$
		$=\sum^{6}_{i=1}\left( \frac{4^i \times e^{-4}}{i!} \right)$
		$=0.073+0.146+0.195+0.195+0.156+0.104=0.871$
		
3) .
	1) La loi suivi par $Y$ est la loi binomiale telle que $Y \leadsto B(80;0.15)$
		La moyenne est $80 \times 0.15=12$
		$\sigma=\sqrt{ 80 \times 0.15 \times 0.85 }=\sqrt{ 10.2 } \approx 3.19$
	2) La loi pouvant être utilisé par $Z$ est la loi normale:
		$Z \leadsto \mathcal{N}(12, 3.19)$
		$P(Z \leq 6)$
		$\Pi(\frac{6.5-12}{\sqrt{ 10.2 }})$
		$=\Pi(-\frac{5.5}{\sqrt{ 10.2 }})$
		$=\Pi(-1.72)=1-\Pi(1.72)=1-0.9573=0.0427$

# Exercice 3

Soit $X$ suit approximativement la loi de Poisson $\mathcal{P}(4)$
1) Soit $Y$ représentant le nombre de pannes d'une machine par trimestre.
	Donc : $Y=4 \times 3=12$ donc $\lambda\geq10$
	On peut utiliser $Y \leadsto \mathcal{P}(12)$

2) En utilisant l'approximation de la loi de normale - car $\lambda=12\geq 10$ :
	$Y \leadsto \mathcal{N}(12, \sqrt{ 12 })$
	$P(X\leq 10)=\Pi(\frac{10.5-12}{\sqrt{ 12 }})=\Pi(-0.433)=1-\Pi(0.433)=1-0.6664=0.3336$
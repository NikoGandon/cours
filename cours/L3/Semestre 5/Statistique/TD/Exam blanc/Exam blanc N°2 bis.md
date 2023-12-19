# Exercice 1

Soit $X \leadsto \mathcal{N}(µ, \sigma),\:n = 100$  

1. Avant expérience, $µ = 2.02 \text{ et }\sigma = 0.2$
   En moyenne, le taux de cholestérol moyen dans la population est de $2$,
   Pour vérifier que le taux soit représentatif au seuil de $95\%$,
   $P(\overline{x}-a \leq \overline{X} \leq \overline{x}+a)=0.95$
   $\Leftrightarrow P(-a \leq \overline{X}-\overline{x}\leq a)=0.95$
   $\Leftrightarrow P( \frac{-a}{\frac{\sigma}{\sqrt{ n }}}\leq \frac{\overline{X}-\overline{x}}{\frac{\sigma}{\sqrt{ n }}} \leq \frac{a}{\frac{\sigma}{\sqrt{ n }}})=0.95$
   $\Leftrightarrow 2 \Pi(\frac{a}{\frac{\sigma}{\sqrt{ n }}}) - 1 = 0.95$
   $\Leftrightarrow2 \Pi(\frac{a}{\frac{\sigma}{\sqrt{ n }}})=0.95+1=1.95$
   $\Leftrightarrow \Pi\left( \frac{a}{\frac{\sigma}{\sqrt{ n }}} \right)=\frac{1.95}{2}=0.975$
   On sait que $\sigma=0.2 \text{ et } \sqrt{n}=10$ :
   $\Leftrightarrow \left( \frac{a}{\frac{0.2}{10}} \right) = 1.96$
   $\Leftrightarrow \frac{a \times 10}{0.2} = 1.96$
   $\Leftrightarrow a \times 10 = 1.96 \times 0.2 = 0.392$
   $\Leftrightarrow a = \frac{3.92}{10}=0.0392$
   Pour $\text{I.C. à 95\% :}$
    $[2.02-0.0392; 2.02+0.0392]$
    $[1.9808; 2.0592]$
    
2. En un mois, l'échantillon passe à $97$ :
   Leur taux moyen est à $2.09$ et $\sigma=0.25$
   On veut déterminer si il existe une différence significative au seuil de $95\% \text{ et à } 99\%$ :
   $\mathcal{N}\left( 2.09; \frac{0.25}{\sqrt{ 97 }} \right)-\mathcal{N}\left( 2.02; \frac{0.2}{\sqrt{ 100 }} \right)$
   $\sqrt{ \frac{\sigma_{1}^2}{\sqrt{ n_{1} }}; \frac{\sigma_{2}^2}{\sqrt{ n_{2} }} }$
   $=\sqrt{ \frac{0.25^2}{\sqrt{ 97 }} + \frac{0.25^2}{\sqrt{ 100 }} } = 0.0323$
   $\mathcal{N}\left( 2.09-2.02; \sqrt{ \frac{0.25^2}{\sqrt{ 97 }} + \frac{0.25^2}{\sqrt{ 100 }} } \right)$
   $\Leftrightarrow \mathcal{N}(0.07; 0.0323)$
   $P(\overline{x} - a \leq \overline{X} \leq \overline{x} + a ) = 0.95$
   $\Leftrightarrow P(-a \leq \overline{X} - \overline{x} \leq a) = 0.95$
   $\Leftrightarrow P\left( \frac{-a}{\frac{\sigma}{\sqrt{ n }}}; \frac{\overline{X} - \overline{x}}{\frac{\sigma}{\sqrt{ n }}}; \frac{a}{\frac{\sigma}{\sqrt{ n }}} \right) = 0.95$
   On sait que $\sigma = 0.25 \text{ et que } n = 97$ :
   $\Leftrightarrow P\left( \frac{-a}{0.0323} \leq \frac{\overline{X} - \overline{x}}{0.0323} \leq \frac{a}{0.0323} \right)=0.95$
   $\Leftrightarrow 2 \Pi\left( \frac{a}{0.0323} \right)-1=0.95$
   $\Leftrightarrow \Pi\left( \frac{a}{0.0323} \right) = 0.975$
   $\Leftrightarrow\left( \frac{a}{0.0323} \right)=..$
   $\Leftrightarrow a = 0.0323 \times .. = ..$
   
   On cherche au seuil de $99\%$ :
   $2\Pi\left( \frac{a}{0.0323} \right) - 1 = 0.99$
   $\Leftrightarrow \Pi\left( \frac{a}{0.0323} \right)= 0.995$
   $\Leftrightarrow (\frac{a}{0.0323})=2.575$
   $\Leftrightarrow a = 0.0323 \times 2.575 = 0.0831725$
# Exercice 2

Soit $X \leadsto \mathcal{N}(m, \sigma)$ :

1. On dit que $\sigma=0.15 \text{ et d'un échantillon de 20 ayant pour moyenne } \overline{x} =24.80$
	1. On peut déterminer avec : $\mathcal{N}\left( \overline{x}; \frac{\sigma}{\sqrt{ n }} \right) = \mathcal{N}\left( 24.80; \frac{0.15}{\sqrt{ 20 }} \right) = \mathcal{N}\left( 24.80; 0,0335 \right)$
	2. On cherche $\text{I.C. de } m \text{ au seuil de 95.44\%}$:
	   $P(\overline{x}-a \leq \overline{X} \leq \overline{x} + a)$
	   $\Leftrightarrow P( -a \leq \overline{X}-\overline{x} \leq a)$
	   $\Leftrightarrow P\left( -\frac{a}{\frac{\sigma}{\sqrt{ n }}} \leq \frac{\overline{X} - \overline{x}}{\frac{\sigma}{\sqrt{ n }}} \leq \frac{a}{\frac{\sigma}{\sqrt{ n }}} \right)$
	   $\Leftrightarrow 2\Pi\left( \frac{a}{\frac{\sigma}{\sqrt{ n }}} \right)-1 = 0.9544$
	   $\Leftrightarrow \Pi\left( \frac{a}{\frac{\sigma}{\sqrt{ n }}} \right)=\frac{1.9544}{2}=0.9772$
	   $\Leftrightarrow \frac{a}{0.0335}=2 \Leftrightarrow a = 2 \times 0.0335 = 0.067$
	   $[24.80-0.067; 24.80 + 0.067]$
	   $= [24.733; 24.867]$
	   	   
	3. On détermine la taille que devrait avoir l'échantillon pour que l'intervalle de confiance de $m$ au seuil de $99\%$ ait une amplitude de $0.03$ :
	   $2\Pi\left( \frac{0.015}{\frac{0.15}{\sqrt{ n }}} \right) - 1 = 0.99$
	   $\Leftrightarrow \Pi\left( \frac{0.015}{\frac{0.15}{\sqrt{ n }}} \right)=\frac{1.99}{2}=0.995$
	   $\Leftrightarrow \left( \frac{0.015}{\frac{0.15}{\sqrt{ n }}} \right)=2.575 \Leftrightarrow \frac{0.013 \times \sqrt{ n }}{0.15}=2.575$
	   $\Leftrightarrow 0.015 \times \sqrt{ n }=0.15 \times 2.575$
	   $\sqrt{ n }= \frac{0.15 \times 2.575}{0.015}=25.75 \Leftrightarrow n = 25.75^2 = 663$ ou $664$
2. A faire
	1. $\overline{x} = 24.73 \text{ et } \sigma = 0.14$
	2. On a calculé $m$ et $\sigma$ :
	   Pour l'estimateur du paramètre $m=\overline{x}$ :
	   Soit $\mathcal{N}(24.73, 0.14)$:
	   
	3. .
	4. .
	5. .
# Exercice 3

1. $$\overline{x}=\sum_{i=0}^{6}\left( \frac{n_{i} \times x_{i}}{\sum (n_{i})} \right)$$
   $\overline{x}=\frac{0 \times 14 + 1 \times 18 + 2 \times 11 + 3 \times 4 + 4 \times 2 + 5 \times 1 + 0}{50}$
   $\Leftrightarrow \overline{x} = 1.3$
   On sait que $V(X) = 1.41$
2. On sait que le degré de liberté est $n-1$, $n = 7$, or nous connaissons la variance donc le degré de liberté est moindre : $n-1-1 = 5$
   On sait que nous travaillons avec une loi de poisson dont $\lambda = \overline{x} = 1.3$
   On cherche $\lambda > \sigma$
   On cherche au risque de $5\%$ : donc au seuil de $95\%$ :
   Donc $\lambda \leq \sigma$, selon la loi de Khi 2 : 
   $P(U_{k}\geq U_{\alpha}) = \alpha$
   $P(U_{5}\geq U_{\alpha}) = \alpha$
   Sur le tableau, avec $k=5 \text{ et } \alpha = 0.95$, on trouve $U_{\alpha} = 1.15$
   On sait que la formule est $(n-1)\left( \frac{s^2}{\sigma ^ 2} \right)$
   $\Leftrightarrow 1.15 = 5 \times \frac{s^2}{\sigma ^ 2}$
   $\Leftrightarrow 1.15 \times 5 = \frac{s^2}{\sigma ^ 2}$
   $\Leftrightarrow \frac{1.15}{5} \times \sigma ^ 2 = s^2$
   $\Leftrightarrow \sigma^2=\frac{5}{1.15}\times s^2$
   $\Leftrightarrow \sigma = \sqrt{ \frac{5}{1.15} \times s^2 }$
   
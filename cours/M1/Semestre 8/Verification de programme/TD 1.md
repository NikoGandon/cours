# Exercice 1

1. Définir de manière inductive le type des booléens
	$$\forall b: \text{Bool} ~ ~ P(b)$$
	$$\frac{}{\text{True Bool}} ~ ~ ~ \frac{}{\text{False Bool}}$$

2. Donner le principe d'induction associé
	$\forall b ~ ~ P(b) \text{ si }$
	$P(\text{True})$
	$P(\text{False})$

3. Montrer par induction que tout booléen est soit ``True`` soit ``False``:
	Pour tout $b: \text{Bool} ~ ~ ~ b=\text{True} \lor b=\text{False}$
	On doit montrer $P(\text{True}) \text{ et } P(\text{False})$ :
	
	$P(\text{True})=(\text{True}=\text{True}) \lor (\text{True}=\text{False})$
	$P(\text{False})= (\text{False}=\text{True}) \lor (\text{False}=\text{False})$
	
4. Définir par induction les expressions booléennes $e=\text{true }| \text{ false}$
	$$\frac{}{\text{True: Expr}} ~ ~ ~ \frac{}{\text{False: Expr}}$$
	$$\frac{e:\text{Expr}}{\neg e:\text{Expr}} ~~~~ \frac{e_{1}:\text{Expr}~ ~ e_{2}:\text{Expr}}{e_{1}\land e_{2}:\text{Expr}} ~~~~ \frac{e_{1}:\text{Expr}~ ~ e_{2}:\text{Expr}}{e_{1}\lor e_{2}:\text{Expr}}$$
	
5. Donner le principe d'induction associée
	$$\forall e:\text{Expr}, P(e) \text{ si}$$
	- $P(\text{True})$
	- $P(\text{False}$
	- $\forall e ~ ~ P(e)\to P(\neg e)$
	- $\forall e_{1}e_{2}, P(e_{1})\to P(e_{2})\to P(e_{1}\land e_{2})\to P(e_{1}\lor e_{2})$
	  
6. Définir par récursion une fonction d'évaluation des expressions booléennes
	$\text{eval}(\text{true})=\text{True}$
	$\text{eval}(\text{false})=\text{False}$
	$\text{eval}(\neg e)=\neg\text{eval}(e)$
	$\text{eval}(e_{1}\land e_{2})=\text{eval}(e_{1})\land\text{eval}(e_{2})$
	$\text{eval}(e_{1}\lor  e_{2})=\text{eval}(e_{1})\lor\text{eval}(e_{2})$
	
7. Prouver que toute expression booléenne peut s'écrire comme une expression équivalente (même valeur) qui ne contient pas ``false``
	- $P(\text{true}) ~~~~~~~~ \text{true} \to \text{true} ~~~~~~~~ \text{même valeur}$
	- $P(\text{false}) ~~~~~~~~ \text{false} \to \neg\text{true} ~~~~~~~~ \text{même valeur}$
	- $$P(\neg e) \begin{cases}
\text{hyp}: e\to e' \\
\neg e\to \neg e' 
\end{cases}$$
	- $$P(e_{1}\land e_{2}) \begin{cases}
\text{hyp}: e_{1}\to e_{1}' \\
\text{hyp}: e_{2}\to e_{2}' \\
e_{1}\land e_{2}\to e_{1}' \land e_{2}'
\end{cases}$$


# Exercice 2

1. Définir le type des listes
	$$\frac{}{\text{nil}:\text{list nat}} ~~~~~~~~ \frac{l:\text{list nat} ~~~~ n:\text{nat}}{\text{Cons}(n,l).\text{list nat}}$$
	- $\forall l :\text{list nat}, P(l) \text{ si}$
		- $P(\text{nil})$
		- $\forall l:\text{list nat} ~~ n:\text{nat}, P(l)\to P(\text{Cons}(n,l))$
		- $\frac{}{\text{sorted}(\text{nil})}~~~~~~~~\frac{n:\text{nat}}{\text{sorted}(\text{Cons}(n,l))}$
		$$\frac{n:n<1}{o\leq n}~~~~~~~~\frac{n\leq m}{n\leq S(m)}$$

2. Donner le principe d'induction
	On veut montrer $\forall l,\text{si sorted}(l)\text{ alors } P(l)$
	
3. Définir par induction un prédicat $\text{sorted}: \forall \alpha ~~ \text{list } \alpha \to \text{prop}$ qui caractérise les listes triées + si d'autres prédicats sont nécessaires, les définir également (ainsi que leur principe d'induction)
	

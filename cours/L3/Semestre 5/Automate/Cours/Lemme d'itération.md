> [!note] 
>Soit $L$ un langage régulier sur $\sum$ alors il existe une constante $n \in \mathbb{N}$ telle que pour tout mot $w \in L$ avec $|w|\geq n$ on peut trouver $x,y,z \in \sum*$ tels que $w=xyz$ et
>- $y \neq \epsilon$
>- $|xy|\leq n$
>- $\forall k\geq 0$, le mot $xy^kz \in L$

>[!note] Pour déterminer $n$ :
> - Par les mots minimaux
> - Par le langage

Tout mot $xy^kz \in L$ $(k\geq 0)$ signifie une expression régulière définissant le langage $L$ telle que $L=L(XY^*Z)$

Voir la [[Demonstration du lemme d'itération]]
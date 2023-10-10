# Propriété 5 : Expressions Régulières pour Chemins AFD
Dans un AFD $A$ de $n$ états numéroté par $1,2,\dots,n$, il existe une expression régulière $R_{i,j}(k)(0\leq k\leq n)$ dont le langage est l'ensemble (peut être vide) de mots $w$ correspondant aux chemins de l'état $i$ à l'état $j$ sans contenir aucun état intermédiaire $>k$

# Propriété 6 : Expression Régulière pour Langage AFD
Soit $A$ un AFD de $n$ états numéroté par $1,2,\dots,n$, où 1 note l'état initial et $q_{1},q_{2},\dots q_{n} (1 \leq q_{1}\leq q_{2}\leq \dots\leq q_{n}\leq n$ sont les états finaux, alors l'expression régulière
$$R=R_{p:q_{1}}(n)+R_{p:q_{2}}(n)+\dots+R_{p:q_{m}}(n)$$
engendre le langage $L(A)$, c'est-à-dire $L(R)=L(A)$
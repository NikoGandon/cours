
# Exercice 2

1. $C$ est un transversal si et seulement si $S=V \backslash C$ est un stable
   $\implies$ soit $C$ est un transversal, par l'absurde, suppose que $V \backslash C$ ne soit pas stable. Donc il existe deux sommets $u$ et $v$ tel que  $\{ u,v \} \in E$. Puisque $C$ est un transversal, on a $u \in C$ ou $v \in C$. Donc il est impossible que $u \in V \backslash C$ et $v \in V \backslash C$. Donc il est impossible que $u \in C$ et $v \in E$.
   
2. ![[Drawing 2024-11-27 09.22.30.excalidraw|5000px]]
   $\nu(G)$ est la taille d'un couplage maximum. $M \subseteq E$ est un couplage si et seulement si $\forall m_{1} \in M, \forall m_{2} \in M, m_{1}\cap m_{2}=\emptyset$ (ensemble d'arête sans extrémité).
   Montrons que $\nu(G) \leq \tau(G)\leq 2\nu(G)$, où $\nu$ est le couplage maximal et $\tau$ la transversale maximale.
   Tout transversal doit contenir au moins l'une des extrémités de chacune des arêtes du couplage. De plus les arêtes n'ont aucune extrémité commune. Donc $\nu(G)\leq \tau(G)$. 
   Si on prend comme transversale deux extrémités des arêtes d'un couplage max, alors on a bien un transversal. En effet, supposons qu'il existe une arête $\{ u,v \}$ sans extrémité
   Dans le transversal (et donc le couplage), alors $\{ u,v \}$ pouvait être ajouté au couplage.
   
   3. Puisque le calcul d'un couplage max est un problème polynomial, on obtient 2-approx au problème transversal.
A la question 1: $\alpha(G)=m-\tau(G)$, avec l'algo qui calcule une 2-approx à $\tau(G)$:
$\nu(G) \leq \tau(G)\leq 2\times\nu(G)$
$\Leftrightarrow m-\nu(G)\geq m-\tau(G)\geq m-2\nu(G)$
$\Leftrightarrow m-\nu(G)\geq \alpha(G)\geq m-2\nu(G)$
Pour montrer que l'algo calcule aussi une 2-approx, $m-2\nu(G)\geq \frac{\alpha(G)}{2}$
Ce n'est pas vrai en général : ![[Drawing 2024-11-27 10.01.32.excalidraw|100px]]
$\nu$ est grand et donc $m-2\nu$ petit mais $\alpha$ grand.

# Exercice 2

1. $C$ est un transversal si et seulement si $S=V \backslash C$ est un stable
   $\implies$ soit $C$ est un transversal, par l'absurde, suppose que $V \backslash C$ ne soit pas stable. Donc il existe deux sommets $u$ et $v$ tel que  $\{ u,v \} \in E$. Puisque $C$ est un transversal, on a $u \in C$ ou $v \in C$. Donc il est impossible que $u \in V \backslash C$ et $v \in V \backslash C$. Donc il est impossible que $u \in C$ et $v \in E$.
   
2. ![[Drawing 2024-11-27 09.22.30.excalidraw]]
   $\nu(G)$ est la taille d'un couplage maximum. $M \subseteq E$ est un couplage si et seulement si $\forall m_{1} \in M, \forall m_{2} \in M, m_{1}\cap m_{2}=\emptyset$ (ensemble d'arête sans extrémité).
   Montrons que $\nu(G) \leq \tau(G)\leq 2\nu(G)$, où $\nu$ est le couplage maximal et $\tau$ la transversale maximale.
   $\nu(G)\leq \tau(G)\leq 2\nu(G)$ soit  
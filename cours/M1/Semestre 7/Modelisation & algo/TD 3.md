# Exercice 2

1. Soit $G_{1}=(V_{1}, E_{1})$ un graphe, $\text{TSP-magique}(G=(V,E))$ une procédure calculant une solution optimale au problème du voyageur de commerce. On cherche à utiliser $\text{TSP-magique}$ pour un cycle hamiltonien.
   On peut mettre toutes les arêtes connus du cycle hamiltonien sur un poids de $1$ et les arêtes non connus (deux points proche $(u,v)$) sur des poids lourds comme $+\infty$.
   Nous pouvons ensuite appliquer $\text{TSP-magique}$.
2. $G_{1}$ admet une solution au cycle hamiltonien si et seulement si par le graphe $G_1$ et la fonction de distance $d$ ainsi contrainte, la procédure $\text{TSP-magique}$ retourne un cycle dont le poids est $n$.
3. On peut trouver comme complexité $\mathcal{O}(n^{2} \times n^{2})$?

# Exercice 3

Soit $\text{TSP-magique}$ s'exécute en temps exponentiel $\mathcal{O}(n^2 2^n)$ et soit la librairie $\text{SuperGraphs}$ donne une procédure TSP-approx qui calcule une approximation au problème du TSP en temps polynomial. 

1. 
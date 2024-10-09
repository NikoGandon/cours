# Exercice 2

1. Soit $G_{1}=(V_{1}, E_{1})$ un graphe, $\text{TSP-magique}(G=(V,E))$ une procédure calculant une solution optimale au problème du voyageur de commerce. On cherche à utiliser $\text{TSP-magique}$ pour un cycle hamiltonien.
   On peut mettre toutes les arêtes connus du cycle hamiltonien sur un poids de $1$ et les arêtes non connus (deux points proche $(u,v)$) sur des poids lourds comme $+\infty$.
   Nous pouvons ensuite appliquer $\text{TSP-magique}$.
2. $G_{1}$ admet une solution au cycle hamiltonien si et seulement si par le graphe $G_1$ et la fonction de distance $d$ ainsi contrainte, la procédure $\text{TSP-magique}$ retourne un cycle dont le poids est $n$.
3. On peut trouver comme complexité en temps exponentiel

# Exercice 3

Soit $\text{TSP-magique}$ s'exécute en temps exponentiel $\mathcal{O}(n^2 2^n)$ et soit la librairie $\text{SuperGraphs}$ donne une procédure TSP-approx qui calcule une approximation au problème du TSP en temps polynomial. 

1. TSP-approx retourne une solution de cout $z=0$ si et seulement si le graphe $G_{1}$ contient un cycle hamiltonien.
   "$\Rightarrow$" si $z=0$ ou $z=n$, alors le cycle construit par TSP-approx n'utilise que des arêtes de $G_{1}$ et dans $G_{1}$ admet un cycle hamiltonien 
   "$\Leftarrow$" si $G_{1}$ admet un cycle hamiltonien alors le graphe $G$ admet une solution optimal à TSP de coût $z=0$ on a $$z^*=\begin{cases}
0 \\
n
\end{cases}$$
   Et donc, quelque soit $c$, on a $$
   c \times z^* = \begin{cases}
n \\
0
\end{cases}<\begin{cases}
 +\infty\\
1
\end{cases}$$
   Ainsi, on peut utiliser TSP-approx pour résoudre le cycle hamiltonien.
   $\frac{3}{2}=1.5$
   $$\forall x,y,z$$
   $$d(x,y) \leq d(x,y)+d(y,z)$$
2. A première vu nous venons de résoudre le cycle hamiltonien, soit un problème $\text{NP}$. Cela crée une illusion

# Exercice 4

1. Soit $\mathcal{T}$ un arbre couvrant minimum de $G=(V,E)$. On duplique les arêtes de $\mathcal{T}$ afin d'obtenir un graphe eulérien 
   Soit $\mathcal{C}$ un cycle qui est une solution optimale à TSP pour le graphe $G=(V,E)$, notons $z^*$ la distance totale de $\mathcal{C}$.
   Montrons que si $\mathcal{T}$ est un arbre couvrant de poids minimum, alors $\text{poids}(\mathcal{T}) \leq z^* (= \text{poids}(\mathcal{C}))$ :
   
   $\mathcal{C}$ contient tous les sommets et $\mathcal{C}$ est un cycle.
   Retirons à $\mathcal{C}$ une arête quelconque, on obtient $\mathcal{C}'$ qui est un arbre couvrant. Or, $\text{poids}(\mathcal{C}) \geq \text{poids}(\mathcal{T})$   
   
>[!info] Graphe eulérien
>Un graphe est eulérien s'il possède un chemin ou un cycle eulérien
>	 - Chemin eulérien : chemin parcourant chaque arêtes une fois.
>	- Cycle eulérien : cycle parcourant toutes les arêtes une fois et reviens au point de départ

2. 
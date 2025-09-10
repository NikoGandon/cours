
# Rappel 

## Parcours en largeur et parcours en profondeur

__Complexité__ : soit $G=(V,E)$ un graphe à $n$ sommets et $m$ arêtes ($n=|V|$ et $m=|E|)$
La complexité en temps de chacun de ces parcours est $\mathcal{O}(n+m)$

Un graphe peut être représenté
- Par une liste d'adjacence 
- par une matrice d'adjacence

![[Parcours en largeur]]

![[Parcours en profondeur]]
## Définition 
Soient $f$ et $g$ deux fonctions
On dit que $f(n)=\mathcal{O}(g(n))$ s'il existe deux constantes $c, n_{0} \geq 0$
telle que :
$$\forall n \geq n_{0},~~ f(n) \leq c \times g(n)$$


# Exercice 1 : composantes connexes
On cherche un algo de $\mathcal{O}(n)$ calculant les composantes connexes d'un graphe non orienté:
On récupère l'algo du parcours en largeur et on ajoute un ensemble des composants connexes 

$\forall v \in V$, faire
	l'état $[v] <- \text{"non atteint"}$
	*$c <- \{\}$* (ensemble composant connexe)
	$\forall v \in V$ faire
		si etat$[v] = \text{"non atteint"}$
			$c_{i}<- \{\}$
			Ajouter $v$ à la file de $F$
			etat$[v] <- \text{"atteint"}$
			tant que $F$ est non vide faire :
				$x <- \text{"extraire tete de F"}$
				Ajouter le sommet $x$ à $c_{i}$
				$\forall y \in N(x)$ faire :
					Si etat$[y] = \text{"non atteint"}$ faire :
						etat$[y] = \text{"atteint"}$
						ajouter $y$ à la file de $F$
				etat$[x] <- \text{"traite"}$
				Ajouter $c_i$ àc 

# Exercice 2 : vecteur de degrés

Soit $G = (V,E)$, un graphe contenant $n$ sommets et $m$ arêtes.
Sont [[Vecteur de degré]] est noté $d(G)$
 1. Chaque sommet est voisin avec les (au plus) $n-1$ ?? ?? sommets 
 2. 
>[!info] 
   La somme des degrés est nécessairement un nombre pair car 
   $\sum_{v=1}d(v)=2m$ (ou $2n$ je ne sais pas)

Par exemple : $d(G)=[2, 0, 0, 0]$ ou $d(G)=[3, 3, 3, 1]$

3.  Démontrer $v=[s, t_{1}, \dots, t_{n}, d_{1}, \dots, d_{k}]$ un vecteur d'entier positifs ou nuls dont les composantes sont triés par ordre décroissant. Soit $v'=[t_{1}-1, \dots, t_{s}-1, d_{1}, \dots, d_{k}]$ le vecteur obtenu de $v$ en y supprimant $s$ et en soustrayant $1$ de chacune des $s$ composantes suivant $s$ dans $v$. Notons $v''$ le vecteur obtenu de $v'$ en triant ses composantes par ordre décroissant.
	1. Voir photo de Bob
	2. .
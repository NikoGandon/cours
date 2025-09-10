$\forall v \in V$, faire
	l'état $[v] <- \text{"non atteint"}$
	$\forall v \in V$ faire
		si etat$[v] = \text{"non atteint"}$
			Ajouter $v$ à la file de $F$
			etat$[v] <- \text{"atteint"}$
			tant que $F$ est non vide faire :
				$x <- \text{"extraire tete de F"}$
				$\forall y \in N(x)$ faire :
					Si etat$[y] = \text{"non atteint"}$ faire :
						etat$[y] = \text{"atteint"}$
						ajouter $y$ à la file de $F$
### Propriété du parcours en largeur
Il visite tout les voisins d'un sommet, puis tous les sommets à distance 2, puis ceux à distance 3, ... .
Chaque sommet est ajouté précisément une fois à la file $F$. A chaque fois qu'un sommet est ajouté à $F$ un état passe de *non atteint* à *atteint* et une fois qu'un sommet est *atteint*, il ne peut plus revenir dans l'état *non atteint*. Cela garanti qu'un sommet peut pas être ajouté plus d'une fois à la file.
De plus, chaque liste d'adjacence est parcourue une fois, lorsque le sommet est extrait de la file de $F$.

$\forall v \in V$ faire :
	etat$[v] <- \text{"non atteint"}$
$\forall v \in V$ faire :
	si etat$[v] = \text{"non atteint"}$ faire
		etat$[v] <- \text{"atteint"}$
		parcours_rec(v)

parcours_rec(x) {
	$\forall y \in N(x)$ faire
		si etat$[y] = \text{"non atteint"}$ alors
			etat$[y] <- \text{"atteint"}$
			parcours_rec(y)
		etat$[x] <- \text{"traite"}$
}

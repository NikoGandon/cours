1. Done
2. 19 tables et 4 types
3. Done
___

1. On voit la somme qu'ont rapporté au total les ventes.
2. Done
3. On voit la somme qu'ont rapporté au total les ventes dans chaque départements
4. ``SELECT SUM(*), DISTINCT departementName FROM Sales, Department INNER JOIN ?``
5. .
   1. Comme la 4) mais répartis dans les différentes régions du monde
   2. Le département technologie sauf dans East 
6. Done
7. Done
8. Done

____
1. Done
2. On obtiens une courbe de croissance sur les ventes
3. .
	1. Nous avons le nombre de ventes affiché par année
	2. Nous avons le nombre de ventes affiché en 2015
4. Il y a une croissance similaire entre les différentes régions
___
1. Done
2. Longitude et latitude
3. Done
4. On peut voir les états américains qui ont effectué le plus de vente
5. Done 
6. On obtient une visualisation des endroits effectuant le plus de vente plus précis : on peut voir avec des points + gros les endroits avec le plus de vente
7. .
	1. Comme le 6), mais avec en plus des couleurs
	2. rouge & petit -> déficit, bleu & grand -> profit

___
1. Done
2. Done
3. Done 
4. Done 
5. ?
6. Done
7. Done
8. Done
____

1. Done
2. Done
3. Done
4. Done
5. Done
6. Done

___
1. Done
2. Done
3. Done
4. Il peut y avoir des doublons ou des manques, par exemple il n'y a pas l'état d'Alaska et Hawaii
5. On affiche deux tableaux : 
	1. Tableau des ventes par états
	2. Tableau de la population par états en 2010
6. ``SELECT (SUM([Sales]) / SUM([Census population (2010)])*1000) FROM STATES-UTF8 INNER JOIN (SELECT * FROM SALES-UTF8 GROUP BY 'State') ON WHERE ?`` ``
7. Done
8. Done

___

1. Done
2. Done
3. On peut voir le nombre de vente et de profit par état dans un nuage de point.
4. Cluster1 et Cluster2, 
5. Done
6. Done
7. Done
8. Done

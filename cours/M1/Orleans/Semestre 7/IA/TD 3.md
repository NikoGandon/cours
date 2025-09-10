
# Exercice 1

1. On cherche un nœud qui maximise sa fitness. Pour cela, on se déplace dans l’espace de recherche de nœud en nœud.
2. Pour la recherche locale, il faut : 
	- Une fonction d’évaluation/objectif ou mesure de fitness (pr avoir le score de chaque état) 
	- Une fonction de voisinage (pr générer les voisins)
3. Un nœud doit contenir les informations pr obtenir sa fitness et son voisinage
2. Soit
```python
def escalade (etat):
	valeur_max = valeur(etat_init)
	etat_courant = etat_init 
	ancien_max = None 
	while ancien_max != valeur_max :
		ancien_max = valeur_max
		voisins = tousVoisins(etat_courant)
		for vois in voisins :
			if (valeur(vois) > valeur_max) : 
				valeur_max = valeur(vois) 
				etat_courant = vois 
	return etat_courant
```
5. La recherche par escalade peut avoir plusieurs limitations : 
   - __Cul de sac__ : Si voisins sont moins bons, blocage
   - __Optimum local__ : Solution locale bonne, mais pas forcément globale
   - __Plateau__ : Voisins ayant la même valeur, l'algo peut errer

# Exercice 2

1. 
	1. __État__ : il y a $N$ reines sur un échiquier $N \times N$, chaque reine est dans une colonne différentes, un état peut être représenté par un tableau $[r_{1}, r_{2}, \dots, r_{n}]$, $r_{i}$ est la ligne où la reine est placé dans la colonne $i$. 
	2. __Voisinage__ : Le voisinage d'un état est l'ensemble des états en déplaçant une reine sur une ligne de sa colonne  
	3. __Taille du voisinage__ : Chaque reine peut se déplacer dans $N-1$ autres lignes de sa colonne, la taille du voisinage est donc $N \times (N - 1)$
	4. __Taille de l'espace de recherche__ : L'espace de recherche contient $N!$ états possibles
2. On peut regarder le nombre de paire de reines en conflit
```
valeur(etat) = -(Nombre de paire de reines en conflit)
```
3. On peut réfléchir à deux méthodes : 
   - __Voisinage restreint__ : Prendre une reine avec le plus de conflits et ne déplacer que cette reine
   - __Aléatoire__ : Déplacer une reine choisi au hasard à chaque étape  
4. 
```python
def tousVoisins(etat) : 
	voisins = []
	N = len(etat)
	for col in range(N - 1) :
		for lign in range(i + 1, N) :
			voisin = etat.copy()
			voisin[col], voisin[lign] = voisin[lign], voisin[col]
			voisins.append(voisin)
	return voisins


def valeur(etat) :
	N = len(etat)
	conflits = 0
	for i in range(N - 1):
		for j in range(i + 1,N - 1):
			if(etat[i] == etat[j]):
				conflits += 1
			if(etat[i] - i == etat[j] - j):
				conflits += 1
			if (etat[i] + i == etat[j] + j):
				conflits += 1
	return conflits
```

# Exercice 3

Soit le tableau suivant comparant la recherche informé et la recherche locale pour le problème des $n$-reines avec $A^*$ et la recherche par escalade avec les résultats obtenus :

|   Algo   |           $n = 8$            |             $n = 16$             |             $n = 32$             |
| :------: | :--------------------------: | :------------------------------: | :------------------------------: |
|  $A^*$   | temps élevé, succès $100\%$  | temps plus élevé, succès $100\%$ | temps très élevé, succès $100\%$ |
| Escalade | temps faible, succès $100\%$ |   temps faible, succès $85\%$    |   temps faible, succès $60\%$    |
1. Pour utilise $A^*$ il nous faut une heuristique et aussi trouver une fonction de coût
2. $A^*$ serait exhaustif sur l'espace de recherche
3. La localité change. En augmentant la taille de $n$, on réduit les chances de tomber sur l'optimum global
4. Vu la taille, il faudrait lancer une recherche locale, quitte à la lancer plusieurs fois

# Exercice 4

1. On part de plusieurs endroits, donc plus de chance de tomber sur le maximum local
2. $k=1$ on a une recherche par escalade classique
   $k=\infty$ est sans intérêt, car on n'aurait aucun gain de temps par rapport à une recherche informée. 
3. .
4. On ne peut pas garantir de trouver le max global.
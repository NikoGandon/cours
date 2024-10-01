# Exercice 1

1. 
2. Fonction de voisinage?
3. .
4. Soit
```python
def escalade (etat):
	while True :
		voisins = tousVoisins(etat)
		meilleurVoisin = etat
		for voisin in voisins:
			if valeur(voisin) > valeur(meilleurVoisin) :
				meilleurVoisin = voisin
		if (meilleurVoisin = etat) :
			return etat
		etat = meilleurVoisin
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
	4. __Taille de l'espace de recherche__ : L'espace de recherche contient $N^{N}$ états possibles, car chaque reine peut être placée dans $N$ positions dans chaque colonne.
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
	for col in range(N) :
		for lign in range(N) :
			if (etat[col] != ligne):
				voisin = etat.copy()
				voisin[col] = ligne
				voisins.append(voisin)
	return voisins


def valeur(etat) :
	N = len(etat)
	conflits = 0
	for i in range(N):
		for j in range(N):
			if(etat[i] == etat[j]):
				conflits += 1
			if (abs(etat[i] - etat[j]) == abs(i * j)):
				conflits += 1
	return conflits
```

# Exercice 3

Soit le tableau suivant : 

|   Algo   |           $n = 8$            |             $n = 16$             |             $n = 32$             |
| :------: | :--------------------------: | :------------------------------: | :------------------------------: |
|  $A^*$   | temps élevé, succès $100\%$  | temps plus élevé, succès $100\%$ | temps très élevé, succès $100\%$ |
| Escalade | temps faible, succès $100\%$ |   temps faible, succès $85\%$    |   temps faible, succès $60\%$    |
1. .
2. .
3. .
4. .

# Exercice 4

1. .
2. .
3. .
4. .
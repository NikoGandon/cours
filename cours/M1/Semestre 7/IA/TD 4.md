# Exercice 1

1. .
2. .

# Exercice 2

1. Soit $6$ allumettes au départ, nous avons en espace des mouvements possibles :
```mermaid
flowchart TB
4a[4]
4b[4]
5a[5]
3b2(3)
1d2(1)
2d2(2)
3b2(3)
0c(0)
1c(1)
1c2(1)
1c3(1)
2c2(2)
3c2(3)
0d1(0)
1d1(1)
1d2(1)
2d2(2)
2c1(2)
1d3(1)
0e5(0)
0d5(0)
0d6(0)
0d7(0)
2b(2)
3b(3)
0e0(0)
1d6(1)
0d9(0)
0d8(0)
0f1(0)
0e1(0)
1e1(1)
2c3(2)
0f(0)

6 --> 4a
6 --> 5a
4a --> 2b
4a --> 3b
5a --> 3b2
5a --> 4b
2b --> 0c
2b --> 1c
1c --> 0d5
3b --> 1c2
1c2 --> 0d6
3b --> 2c1
2c1 --> 0d7
2c1 --> 1d3
1d3 --> 0e5
3b2 --> 1c3
3b2 --> 2c2
1c3 --> 0d8
2c2 --> 0d9
2c2 --> 1d6
1d6 --> 0e0
4b --> 2c3
4b --> 3c2
2c3 --> 0d1
2c3 --> 1d1
3c2 --> 1d2
3c2 --> 2d2
2d2 --> 0e1
2d2 --> 1e1
1e1 --> 0f
1d2 --> 0f1
```
2. Chacun son tour
3. Voir photo


# Exercice 4

```python
def valeur_max_ab(etat, a, b):
	return {etat, XXX}

def valeur_min_ab(etat, a, b):
	return

def rech_ab(etat):
	# On utilise valeur_max_ab ?
	return

def demarrer(): 
```


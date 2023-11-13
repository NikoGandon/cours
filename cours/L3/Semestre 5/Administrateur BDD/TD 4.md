# Exercice 1

Soit **T1** : READ(A,t); t = t + 2; WRITE(A,t); READ(B,t); t = t + 3; WRITE(B,t)
Soit **T2** : READ(B,s); s = s * 2; WRITE(B,s); READ(A,s); s = s + 3; WRITE(A,s)

1) En partant d'un état arbitraire,
	$A=5, B=10$
	$T_{1}:A=7,B=13$
	$T_{2}=10,B=26$

| Opération 1 | Opération 2 | A   | B   | t OR S |
| ----------- | ----------- | --- | --- | ------ |
| READ(A,t)   |             | 5   | 10  | 5      |
| t = t + 2   |             |     | 10  | 7      |
| WRITE(A,s)  |             | 7   | 10  | 7      |
| READ(B,t)   |             | 7   | 10  | 10     |
| t = t + 3   |             | 7   | 10  | 13     |
| WRITE(B,t)  |             | 7   | 13  | 13     |
|             | READ(B,s)   | 7   | 13  | 13     |
|             | s = s * 2   | 7   | 13  | 26     |
|             | WRITE(B,s)  | 7   | 26  | 26     |
|             | READ(A,s)   | 7   | 26  | 7      |
|             | s = s + 3   | 7   | 26  | 10     |
|             | WRITE(A,s)  | 10  | 26  | 10     |
2) 

| Opération 1 | Opération 2 | A   | B   | t OR S |
| ----------- | ----------- | --- | --- | ------ |
|             | READ(A,s)   | 5   | 10  | 5      |
|             | s = s + 3   | 5   | 10  | 8      |
|             | WRITE(A,s)  | 8   | 10  | 8      |
|             | READ(B,s)   | 8   | 10  | 10     |
|             | s = s * 2   | 8   | 10  | 20     |
|             | WRITE(B,s)  | 8   | 20  | 20     |
| READ(A,t)   |             | 8   | 20  | 8      |
| t = t + 2   |             | 8   | 20  | 16     |
| WRITE(A,s)  |             | 16  | 20  | 16     |
| READ(B,t)   |             | 16  | 20  | 20     |
| t = t + 3   |             | 16  | 20  | 23     |
| WRITE(B,t)  |             | 16  | 23  | 23     |



3) Il peut exister 2 séries possibles.
4) Un ordonnancement est sérialisable s'il existe un ordonnance S' (ayant le même ensemble d'action), à partir de la même base, les exécutions de S et S' auront les mêmes résultats.
	Donc, $2 \times C\binom{3}{6}=2 \times \frac{n!}{k!(n-k)!}= 2 \times 20 = 40$
# Exercice 2
1) .
	1) $T_{3}\to T_{2}\to T_{1}$
	2) Pas de cycle donc conflit sérialisable
	   Equivalent : $\dots$ 
1) .
	1) .
	2) .
2) .
	1) .
	2) .
3) .
	1) .
	2) .
4) .
	1) .
	2) .

# Exercice 3

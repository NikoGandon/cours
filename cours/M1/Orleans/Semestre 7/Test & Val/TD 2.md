# Exercice 1

Soit 
#### $(Y < 0) \lor (X-Y>0) \lor (2 \times X - 3 \times Y + 4 < 0)$

Disjonction 
1) un cas où tous les prédicats sont "Justes" -> Faux
2) Pour chaque prédicat, un cas où le prédicat est "Juste" -> Vrai

Avec $c_{1} \lor c_{2} \lor c_{3}$, on peut avoir $c_{1}$ vrai et $c_{2}, c_{3}$ faux.
1. $Y=0, X=0$
2. 
	1. $X = 1, Y = 0$
	2. $X = -1, Y = -1$
	3. $X = -1, Y = 1$

#### $(Y < 0) \land (X-Y>0) \land (3 \times X + 2 \times Y - 10 < 0)$

Conjonction 
1) un cas où tous les prédicats sont "Justes" -> Vrai
2) Pour chaque prédicat, un cas où le prédicat est "Juste" -> Faux

Avec $c_{1} \land c_{2} \land c_{3}$, on peut qu'avoir $c_{1}, c_{2}, c_{3}$ de vrai
1. $X=2, Y=1$
2. 
	1. $X=1, Y=0 \implies Y < 0$
	2. $X = -1, Y = -1 \implies X - Y < 0$
	5. $X = 4, Y = -1 \implies 3X + 2Y - 10 < 0$

# Exercice 2

$A_{1}$ Changement d'année et positionnement au 1er jour de l'année 
$A_{2}$ Changement de mois et positionnement au 1er jour du mois
$A_{3}$ Changement de jour et maintient du mois et de l'année
$A_{4}$ Date incorrect


$Y_{1}$ année bissextile
$Y$ année non bissextile

$J_{1}: \text{jour} \in [1 .. 27]$, $M_{1} : \text{ Le mois a 31 jours}$
$J_{2}: \text{jour} = 28$ , $M_{2} : \text{ Le mois a 30 jours}$
$J_{3}: \text{jour} = 29$,  $M_{3} : \text{mois} = \text{février}$
$J_{4}: \text{jour} = 30$,  $M_{4} : \text{mois} = \text{décembre}$
$J_{5}: \text{jour} = 31$

| .                   | 1       | 2       | 3       | 4       | 5       | 6       | 7       | 8       | 9       | 10      |
| :------------------ | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- |
| Année               | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ |
| Jour                | $J_{1}$ | $J_{1}$ | $J_{2}$ | $J_{2}$ | $J_{3}$ | $J_{3}$ | $J_{4}$ | $J_{4}$ | $J_{5}$ | $J_{5}$ |
| Mois                | $M_{1}$ | $M_{1}$ | $M_{1}$ | $M_{1}$ | $M_{1}$ | $M_{1}$ | $M_{1}$ | $M_{1}$ | $M_{1}$ | $M_{1}$ |
| $A_{1}$ : année + 1 |         |         |         |         |         |         |         |         |         |         |
| $A_{2}$ : mois  + 1 |         |         |         |         |         |         |         |         | x       | x       |
| $A_{3}$ : jour + 1  | x       | x       | x       | x       | x       | x       | x       | x       |         |         |
| $A_{4}$ : incorrect |         |         |         |         |         |         |         |         |         |         |

| .                   | 11      | 12      | 13      | 14      | 15      | 16      | 17      | 18      | 19      | 20      |
| :------------------ | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- |
| Année               | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ |
| Jour                | $J_{1}$ | $J_{1}$ | $J_{2}$ | $J_{2}$ | $J_{3}$ | $J_{3}$ | $J_{4}$ | $J_{4}$ | $J_{5}$ | $J_{5}$ |
| Mois                | $M_{2}$ | $M_{2}$ | $M_{2}$ | $M_{2}$ | $M_{2}$ | $M_{2}$ | $M_{2}$ | $M_{2}$ | $M_{2}$ | $M_{2}$ |
| $A_{1}$ : année + 1 |         |         |         |         |         |         |         |         |         |         |
| $A_{2}$ : mois  + 1 |         |         |         |         |         |         | x       | x       |         |         |
| $A_{3}$ : jour + 1  | x       | x       | x       | x       | x       | x       |         |         |         |         |
| $A_{4}$ : incorrect |         |         |         |         |         |         |         |         | x       | x       |


| .                   | 21      | 22      | 23      | 24      | 25      | 26      | 27      | 28      | 29      | 30      |
| :------------------ | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- |
| Année               | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ |
| Jour                | $J_{1}$ | $J_{1}$ | $J_{2}$ | $J_{2}$ | $J_{3}$ | $J_{3}$ | $J_{4}$ | $J_{4}$ | $J_{5}$ | $J_{5}$ |
| Mois                | $M_{3}$ | $M_{3}$ | $M_{3}$ | $M_{3}$ | $M_{3}$ | $M_{3}$ | $M_{3}$ | $M_{3}$ | $M_{3}$ | $M_{3}$ |
| $A_{1}$ : année + 1 |         |         |         |         |         |         |         |         |         |         |
| $A_{2}$ : mois  + 1 |         |         |         | x       | x       |         |         |         |         |         |
| $A_{3}$ : jour + 1  | x       | x       | x       |         |         |         |         |         |         |         |
| $A_{4}$ : incorrect |         |         |         |         |         | x       | x       | x       | x       | x       |


| .                   | 31      | 32      | 33      | 34      | 35      | 36      | 37      | 38      | 39      | 40      |
| :------------------ | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- | ------- |
| Année               | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ | $Y_{1}$ | $Y_{2}$ |
| Jour                | $J_{1}$ | $J_{1}$ | $J_{2}$ | $J_{2}$ | $J_{3}$ | $J_{3}$ | $J_{4}$ | $J_{4}$ | $J_{5}$ | $J_{5}$ |
| Mois                | $M_{4}$ | $M_{4}$ | $M_{4}$ | $M_{4}$ | $M_{4}$ | $M_{4}$ | $M_{4}$ | $M_{4}$ | $M_{4}$ | $M_{4}$ |
| $A_{1}$ : année + 1 |         |         |         |         |         |         |         |         | x       | x       |
| $A_{2}$ : mois  + 1 |         |         |         |         |         |         |         |         |         |         |
| $A_{3}$ : jour + 1  | x       | x       | x       | x       | x       | x       | x       | x       |         |         |
| $A_{4}$ : incorrect |         |         |         |         |         |         |         |         |         |         |

# Exercice 3

Pour un programme $P$

1. Soit $G$ représentant $P$ : ![[Drawing 2024-10-04 09.32.00.excalidraw]]
2. Les chemins de contrôle de $G$ sont les suivants :
	- $EI_{1}C_{1}S$
	- $EI_{1}C_{1}I_{2}C_{2}S$
	- $EI_{1}C_{1}I_{2}C_{2}I_{3}C_{3}I_{4}C_{4}I_{5}S$
3. On peut définir l'expression par `E((I[1-6])(C[1-6]))+S`.
4. Soit $DT_{1} = \{b = 1, c = 2, x = 2\}$: $EI_{1}C_{1}I_{2}C_{2}I_{3}C_{3}S$.
5. Soit les $DT_{2} = \{ b = 1, c = 2, x = 0 \}$ et $DT_{3} = \{ b = 5, c = 2, x = 0 \}$ sont des chemins menant aux instructions d'écriture
6. Soit $EI_{1}C_{1}I_{2}C_{2}I_{3}C_{3}I_{4}C_{4}I_{6}S$ le chemin de contrôle non exécutable par $G$

# Exercice 4
   
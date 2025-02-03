1. Soit $X_{1},\dots,X_{m}$ sont des attributs d'entrée catégoriels et $Y$ est un attribut de sortie catégorique. Supposons que nous prévoyons d'apprendre un arbre de décision sans élagage en utilisant l'algorithme standard, est-ce que la profondeur maximale de l'arbre de décision doit être inférieur à $m+1$ : Oui car les attributs sont catégoriques et chacun ne peuvent être split qu'une fois
2. .
	1. ``A && !B``
	   	   
|  A  |  B  | ``A and not B``/classe |
| :-: | :-: | :--------------------- |
|  0  |  0  | $\emptyset$            |
|  0  |  1  | $\emptyset$            |
|  1  |  0  | 1                      |
|  1  |  1  | $\emptyset$            |
![[Drawing 2025-02-03 14.01.38.excalidraw]]
	2. ``A xor B``
	   	   
|      A      |      B      | ``A and not B``/classe |
| :---------: | :---------: | :--------------------- |
| $\emptyset$ | $\emptyset$ | $\emptyset$            |
|      0      |      1      | 1                      |
|      1      |      0      | 1                      |
|      1      |      1      | $\emptyset$            |

![[Drawing 2025-02-03 14.03.33.excalidraw]]
	1. ``A or (B and C)``
	   	   
|  A  |  B  | C   | ``A and not B``/classe |
| :-: | :-: | --- | :--------------------- |
|  0  |  0  | 0   | $\emptyset$            |
|  0  |  0  | 1   | $\emptyset$            |
|  0  |  1  | 0   | $\emptyset$            |
|  0  |  1  | 1   | 1                      |
|  1  |  0  | 0   | 1                      |
|  1  |  0  | 1   | 1                      |
|  1  |  1  | 0   | 1                      |
|  1  |  1  | 1   | 1                      |

![[Drawing 2025-02-03 14.09.02.excalidraw]]

# Exercice 3

$P(\text{yes})=\frac{4}{6}$
$P(\text{no})=\frac{2}{6}$
$E(S)=-\frac{4}{6}\log_{2} \frac{4}{6}- \frac{2}{6} \log \frac{2}{6}=0.93$

| chest | +   | -           | =   |
| :---: | --- | ----------- | --- |
|  yes  | $3$ | $\emptyset$ | $3$ |
|  no   | $1$ | $2$         | $3$ |
$E(\text{chest}) + : \frac{3}{6} \left[ -\frac{3}{3} \log \frac{3}{3} - \frac{0}{3} \log \frac{0}{3}\right]$
$E(\text{chest}) - : \frac{3}{6}\left[ -\frac{1}{3}\log_{2} \frac{1}{3} - \frac{2}{3}\log \frac{2}{3}\right]$
$=0 + 0.47 = 0.47$

| male | +   | -           | =   |
| :--: | --- | ----------- | --- |
| yes  | $2$ | $2$         | $4$ |
|  no  | $2$ | $\emptyset$ | $2$ |
$E(\text{male}) + : \frac{4}{6} \left[ -\frac{2}{4} \log_{2} \frac{2}{4} - \frac{2}{4} \log_{2} \frac{2}{4}\right]$
$E(\text{male}) - : \frac{2}{6}\left[ -\frac{2}{2}\log \frac{2}{2} - \frac{0}{2}\log_{2} \frac{0}{2}\right]$
$=0.667 + \emptyset = 0.667$

| smoke | +   | -   | =   |
| :---: | --- | --- | --- |
|  yes  | $3$ | $1$ | $4$ |
|  no   | $1$ | $1$ | $2$ |
$E(\text{smoke}) + : \frac{4}{6} \left[ -\frac{3}{4} \log_{2} \frac{3}{4} - \frac{1}{4} \log_{2} \frac{1}{4}\right]$
$E(\text{smoke}) - : \frac{2}{6}\left[ -\frac{1}{2}\log_{2} \frac{1}{2} - \frac{1}{2}\log_{2} \frac{1}{4}\right]$
$=0.53 + 0.33 = 0.86$

![[Drawing 2025-02-03 14.50.58.excalidraw]]

$\text{chest} = \text{no}$
$P(\text{yes}) = \frac{1}{3}$
$P(\text{no}) = \frac{2}{3}$
$E(S)=--\frac{1}{3}\log_{2} \frac{1}{3} -\frac{2}{3} \log_{2} \frac{2}{3}=0.93$

| male | +           | -           | =   |
| :--: | ----------- | ----------- | --- |
| yes  | $\emptyset$ | $2$         | $2$ |
|  no  | $2$         | $\emptyset$ | $2$ |


![[Drawing 2025-02-03 15.00.43.excalidraw]]

```
IF chest_pain = yes THEN heart_attack = yes
IF chest_pain = n AND 
```
# Exercice 4


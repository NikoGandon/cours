# Exercice 1

$K,20$
$C=\{17,18,3\}$

1. | 17 | 18 | 3 | -> | 17 + 3 | 18 |
2. Le problème est NP-complet (on ne connait pas d'algo polynomial pour calculer la meilleure solution), montrons que l'algo calcule une 2-approx
   $\frac{\text{Algo}(I)}{\text{Optimum(I)}}\leq 2$, où $\text{Algo}$ est le nombre de wagon utilisé par l'algo et $\text{Optimum}$ est le nombre optimal :
   - Soit $K$ le poids max chargeable sur un wagon
   - Soit $w_{1},w_{2},\dots,w_{n}$ le poids des conteneurs
   - Soit $W=\sum^{n}_{i=1}w_{i}$
   - Soit $A$ le nombre de wagon utilisé par l'algo
   - Soit $O$ le nombre de wagon utilisé par la solution optimale
   Nous devons montrer que $A\leq O \times 2 \Leftrightarrow \frac{A}{O}\leq 2$, en sachant que $O \leq A$
   
   __Montrons que $O$ ne peut pas être trop petit et que $A$ ne peut pas être trop grand__
   
   ___Observation 1___ : $O$ n'est pas trop petit
	 - On a $O\geq \frac{W}{K}$
	   où chaque conteneur est transporté par un wagon et chaque wagon ne peut transporter qu'au plus un poids $K$
	
	___Observation 2 :___ $A$ n'est pas trop grand
	 - Chaque conteneur doit être chargé sur un wagon, on peut supporter que $w_{i}\leq K ~~~~~~ \forall i, 1 \leq i \leq n$, donc $A \leq n$
	   On va s'appuyer sur ce que fait notre algo pour établir une borne plus précise
	
	__Proposition : chaque paire de 2 wagons consécutifs transporte un poids supérieur à $K$.__
	- Preuve par contradiction, si cette charge est inférieure à $K$, alors l'algorithme mettrait la charge sur un seul wagon

# Exercice 2
   
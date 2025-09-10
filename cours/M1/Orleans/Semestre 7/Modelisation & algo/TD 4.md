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
	- Preuve par contradiction, si cette charge est inférieure à $K$, alors l'algorithme mettrait la charge sur un seul wagon. De plus, chacun des conteneurs est chargé sur l'un des wagons du convoi.
	  Donc $W\geq \frac{A}{2}\times K \Leftrightarrow \frac{W}{K}\geq \frac{A}{2}$
	  Ainsi, $O\geq \frac{W}{K} \geq \frac{A}{2} \Leftrightarrow A \leq 2 \times O$

# Exercice 2

Commençons par montrer que l'algorithme est 2-approx.
Notons $\text{OPT}$ la charge de travail optimale, c'est à dire que l'on obtient avec la meilleure répartition possible sur les $10$ machines : $\text{OPT}\geq \frac{1}{10}\sum_{i=1}^{n}t_{i}$ et $\text{OPT}\geq \max_{1\leq i\leq n}t_{i}$.

Notons $M_{j}$ la machine qui termine en dernier. Notons $t_{\lambda}$ la dernière tâche affectée à $M_j$.

A cause du choix glouton de l'algo, on sait que toutes les autres machines terminent après $T_{j}-T_{\lambda}$ où $T_{j}$ est la date à laquelle $M_{j}$ termine : $T_{i} \geq T_{j}-T_{\lambda}$, $\forall 1 \leq i \leq 10$
Puisque chaque tâche est affectée à l'une des machines :

$$\sum^{10}_{i=1}\geq 10 \times (t_{j}-t_{\lambda}) \Leftrightarrow \frac{\sum^{10}_{i=1}}{10} \geq t_{j}-t_{\lambda}$$
$$\Leftrightarrow \text{OPT} > t_{j} -t_{\lambda}$$
$$\Leftrightarrow \text{OPT} + t_{\lambda} \geq t_{j}$$
$$\Leftrightarrow \text{OPT} + \text{OPT} > t_{j}$$
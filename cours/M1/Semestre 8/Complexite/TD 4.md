# Exercice 1
1. On peut parler de numérotations des $\text{MT}$ ???????

2. Le code de $M_{1}$ est décrit par le mot $<M_{1}>$ sur l'alphabet $\sum_{M}$
	$i \leftrightarrow <M_{1}>\in\sum_{M}$
	$$M_{u}
	\begin{cases}
\text{prend en entrée } <M, u> \\
\text{sur le } M \text{ sur } u \\
\text{s'arrête sur } M \text{ s'arrête sur } u \\
\text{renvoie le résultat de } M \text{ sur } u
\end{cases}$$
	Il existe une machine $\text{MT}$ universelle $M_{u}$ (cf cours)
	Il existe une $\text{MT}$ qui sur l'entrée  >$ calcule $M_u$
	On construit la $\text{MT}$ que sur l'entrée $<n,m>$
	- Calcule $M_{n}$ et écrit $<M_{n},m>$ sur le ????
	- Sur le $M_{i}$ sur $<M_{n},m>$
	  
3. Est-ce que le problème est décidable ?
	- **Entrée** : un entier $i \in \mathbb{N}$
	- **Question** : Existe t il un entier $j$ compris entre $0$ et $i$ et tel que la $\text{MT}$ numéro $i$ s'arrête sur $j$ en moins de $i$ étapes ?
	- **Réponse** : On construit $M$ une $\text{MT}$ totale qui reconnait le langage associé
	  Sur l'entrée $<i>, M$:
		- $\forall 0 \leq j \leq i$
			- $M$ simule $i$ étapes de $M_{i}$ sur $<j>$
		- Si l'une des ??? s'est arrêté avant l'étape $i$, alors $M$ accepte. Sinon $M$ refuse.

4.  Est-ce que le problème est décidable ?
	- **Entrée** : une $\text{MT}$ $M$ et un mot $u \in \sum^*$
	- **Question** : Existe t il un entier $j$ compris entre $0$ et $i$ et tel que la $\text{MT}$ numéro $i$ s'arrête sur $j$ en moins de $i$ étapes ?
	- **Réponse** : 
	  $$L=\{ <M,u> \text{ la tête de } M \text{ sont des cases sur l'entrée} <x> ~~~~| ?? \}$$
	  On note $k=|u|$. Pour décrire la configuration et l'état de la $\text{MT}$ à 1 sommet donnée, il faut
		- L'état de la $\text{MT}$ 
		- Le mot écrit sur les $k$ ?? disponibles
		- Les positions de la tête à entre $0$ et le .
	On construit la $\text{MT}$ $M_{l}$ totale qui reconnait $L$
	- Place des délimiteurs ?? de l'entrée $u$ sur le ??
	- Simule $M$ sur $u$ en incrémentant son compteur à chaque étape de simulation
	- Si la tête de $M$ dépasse le délimiteur, donc $M_{l}$ accepte
	- Si la simulation de $M$ s'arrête, alors $M_{l}$ refuse
	- Si le compteur dépasse $|Q|\times|u|$, $M_{l}$ refuse
	$M_{l}$ est totale et reconnait $L$. En effet, dans le délimiteur, si le compteur dépasse $|Q|\times|u|$, $M_{l}$ est passé 2 fois par la même configuration avec le même état et la même position de la tête, donc $M_l$ boucle ????????????????
	$L=\{ <i> ~~~~i \in L(M_{i}) \}$
	r.e. en simulant $M_{i}$ sur $<i>$
	On veut montrer que $L$ n'est pas r.e. 
	- Supposons que $\overline{L}$ soit r.e. alors il existe une $\text{MT}$ qui reconnait $\overline{L}$, c'est-à-dire qu'il existe $i$ tel que $M_i$ reconnait $\overline{L}$. Donc $\overline{L}=L(M_{i})$
		- Si $<i> \in L(M_{i})$ alors $<i> \notin \overline{L}$
		- Si $<i> \notin L(M_{i})$ alors $<i> \in \overline{L}$-

5.  Est-ce que le problème est décidable ?
	- **Entrée** : une $\text{MT}$ $M$ et un mot $u \in \sum^*$
	- **Question** : Existe t il un entier $j$ compris entre $0$ et $i$ et tel que la $\text{MT}$ numéro $i$ s'arrête sur $j$ en moins de $i$ étapes ?
	- **Réponse** : 
	  
6.  Est-ce que le problème est décidable ?
	- **Entrée** : un entier $i \in \mathbb{N}$
	- **Question** : Existe t il un entier $j$ compris entre $0$ et $i$ et tel que la $\text{MT}$ numéro $i$ s'arrête sur $j$ en moins de $i$ étapes ?
	- **Réponse** : 


>[!info] 
>r.e. : récursivement énumérable

# Exercice 2

5. Le problème est-il décidable ?
	- **Entrée** : une $\text{MT } M \text{, un mot } u \in \sum^*\text{ et un état } q \in Q$
	- **Question** : lors de son calcul sur l'entrée $u$, la machine $M$ passe-t-elle par l'état $q$ ?
	- 
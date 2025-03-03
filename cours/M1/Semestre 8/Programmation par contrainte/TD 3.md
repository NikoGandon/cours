# Exercice 1

$X \leq Y \to Z \leq 3$
$D(X) = \{ 1, \dots, 4 \}$
$D(Y) = \{ 1, \dots, 3 \}$
$D(Z) = \{ 1, \dots, 5 \}$


1. Le domaine de ces variables quand le CSP devient arc-consistant :
	Pas de changement

2. Si $X$ est instancié à $1$, alors le domaine de chaque variable quand le CSP devient arc-consistant :
	   - $X \in \{ 1 \}$
	   - $Y \in \{ 1, \dots, 3 \}$
	   - $Z \in \{ 1, \dots, 3 \}$

3. Aux domaines initiaux, même question lorsque $Z$ est instancié à $1$ :
	   - $Z$ initialisé à $1$ :
		   - $X \in \{ 1, \dots, 4 \}$
		   - $Y \in \{ 1, \dots, 3 \}$
		   - $Z \in = \{ 1 \}$


# Exercice 3

Une association veut organiser la fête de fin d’année. Elle sait qu’elle peut compter sur 6 personnes pour l’organisation. Pour le bon fonctionnement de la fête, elle va répartir les personnes en 4 équipes : cuisine, animation, accueil et service. Chaque personne ne participe qu’a une seule équipe. Après une étude prévisionnelle, on décide le nombre minimal et le nombre maximal de membres pour chaque équipe comme suit :

| équipe    | min | max |
| :-------- | --- | --- |
| cuisine   | 2   | 2   |
| animation | 1   | 2   |
| accueil   | 1   | 1   |
| service   | 1   | 3   |

1. Donnez un modèle pour répartir les personnes en équipes :
   
   - Variables : $\text{A}, \dots, \text{F} ~~~~~~~~~~~~~\text{(personnes)}$
   - Domaines : $\in\{ 1, \dots, 4 \} ~~~~~\text{(équipes)}$
   - Contraintes : 
     - Chaque personne n'est que dans une seule équipe
     - On a 6 personnes $\text{A},\dots, \text{F}$
     - En cuisine, il y a 2 personnes
     - animation : $1\leq \text{count}([A,\dots,F], 2) \leq 2$
     - accueil : $1 \leq \text{count}([A, \dots, F], ?) \leq 1$
     - service : $1\leq \text{count}([A, \dots, F], 4) \leq 3$
2. On veut tenir compte le souhait de chaque personne. D'après le sondage, les préférences des personnes sont comme suit : 

| personne | souhait                     |
| :------- | --------------------------- |
| Alain    | cuisine                     |
| Bernard  | cuisine, animation          |
| Céline   | cuisine, animation          |
| Daniel   | animation                   |
| Emma     | animation, accueil, service |
| Fred     | accueil, service            |
![[Drawing 2025-02-26 09.44.45.excalidraw|1000]]

Les composantes fortement connexes sont $E 4 F 3 E$, $E 4 P 3 E$, $E 4 P 4 F 3 E$, $B 2 C 1 B$


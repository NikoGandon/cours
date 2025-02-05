# Exercice 1

Trouver les triangles dont tous les angles sont diviseurs 360 :

Variables : A, B, C les angles du triangle
Domaines : $1 .. 178, ~ ~0 .. 180$
Contraintes : $360 \% A = 0,~ ~ 360 \% B = 0,~ ~360 \% C = 0,~ ~ A+B+C=360$

# Exercice 2

Dans une rue, quatre voitures sont garés les unes derrières les autres : la Renault est noire, la Ferrari est rouge, la voiture blanche n'est pas à une extrémité, il y a au moins une voiture entre la Renault et la Peugeot, la Ferrari est devant la Volvo, la voiture jaune n'est pas entre la rouge et la noire, la Ferrari et la Renault sont à côté l'une l'autre. Quelle marque a quelle couleur ?

Variables : Renault, Ferrari, Volvo, Peugeot, Noire, Rouge, Blanche, Jaune
Domaines : $1..4$, position de chaque marque / couleur
Contraintes : $\text{Renault} = \text{noire}$, $\text{Ferrari} = \text{rouge}$, $| \text{Renault - Peugeot} | \geq 2$,$\text{Ferrari}<\text{Peugeot}$, $\text{Blanche} \neq 4$, $\text{Blanche} \neq 1$, $(\text{Jaune} < \text{Noire}) \lor (\text{Jaune} > \text{Peugeot} \land \text{Jaune} > \text{Noire})$ 

| Marque  | couleur |
| :------ | :------ |
| Renault | Noire   |
| Ferrari | Rouge   |
| Volvo   | Blanche |
| Peugeot | Jaune   |
# Exercice 3

Trois amis aiment différents types de musiques, à partir des indices, identifiez les, donner leur musique préférée et dire qui a 26 ans

Variables : 
Domaines : 
Contraintes : 

| Nom   | Musique préférée | A 26 ans |
| :---- | ---------------- | -------- |
| Rob   |                  |          |
| Queen | Classique        |          |
| Leon  |                  | Non      |
| Mark  |                  |          |

# Exercice 4

René affirme ce qui suit : 
1. Des trois proposition A, B et C, une seule est vraie
2. Des trois proposition B, C et D, une seule est vraie
3. Des deux proposition A et D, une seule est vraie
André affirme lui : 
1. De A, B et C, une seule est vraie
2. De B, C et D, une seule est vraie
3. De A, C et D, une seule est vraie
Un des deux personnages ment au moins une fois, quelles sont les propositions vraies ?

| Proposition | Vrai |
| :---------- | ---- |
| Rene 1      | ??   |
| Rene 2      | ??   |
| Rene 3      | ??   |
| André 1     | ??   |
| André 2     | ??   |
| André 3     | ??   |
Variables : A, B, C, D, R1, R2, R3, A1, A2, A3


# Exercice 7



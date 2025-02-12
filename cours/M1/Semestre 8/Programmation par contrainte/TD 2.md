# Exercice 1

- $c_{1}: y <z$
- $c_{2} : x+y=5$
- $c_{3}: x+z>6$
- $c_{4}: w<x$
- $c_{5}: w\leq y-1$

$x,y,z,w \in \{ 1,\dots,5 \}$

ordre de variables : $x,y,z,w$
ordre de valeur : croissant

<u>Backtracking</u>

![[Drawing 2025-02-12 08.23.02.excalidraw|2500px]]

<u>BT+FC</u>

![[Drawing 2025-02-12 08.42.19.excalidraw|1500px]]
>[!error] Correction trop longue


<u>AC 3</u>

$Q=c_{1}y_{3},~~c_{2}xy,~~c_{3}xz,~~c_{3}zx,~~c_{4}wx,~~c_{4}xw,~~c_{5}wy,~~c_{5}yw$

|    arc    | domaine                 | arc ajouté de $Q$                                 |
| :-------: | ----------------------- | ------------------------------------------------- |
| $c_{1}yz$ | $y \in \{ 1,..,4 \}$    | $c_{2}xy,~~c_{5}wy$ non ajouté car degré dans $Q$ |
| $c_{1}zy$ | $z \in \{ 2,\dots,5 \}$ | ---                                               |
| $c_{2}xy$ | $x \in \{ 1,\dots,4 \}$ | ---                                               |
| $c_{2}yx$ | $x \in \{ 1,\dots,4 \}$ | ---                                               |
| $c_{3}xz$ | $x \in \{ 2,\dots,4 \}$ | $c_{2}yx$                                         |
| $c_{3}zx$ | $x \in \{ 3,\dots,5 \}$ | $c_{1}yz$                                         |
| $c_{4}wx$ | $w \in 1$               |                                                   |
| $c_{4}xw$ | ---                     |                                                   |
| $c_{3}wy$ | ---                     |                                                   |
| $c_{5}yw$ | $y \in \{ 2,\dots,4 \}$ | $c_{1}zy,~~c_{2}xy$                               |
| $c_{2}yx$ | $y \in \{ 2,3 \}$       | $c_{5}wy$                                         |
| $c_{2}xy$ | ---                     |                                                   |
| $c_{5}wy$ | ---                     |                                                   |
| $c_{2}xy$ | $x \in \{ 2,3 \}$       | $c_{3}zx,~~c_{4}wx$                               |
| $c_{5}wy$ | $w \in \{ 1,2 \}$       | $c_{4}xw$                                         |
| $c_{3}zx$ | $z \in \{ 4,5 \}$       | $c_{1}yz$                                         |
| $c_{4}wx$ | ---                     | ---                                               |
| $c_{4}xw$ | ---                     | ---                                               |
| $c_{1}yz$ | ---                     | ---                                               |
$x,y,z \in \{ 1,\dots,5 \}$


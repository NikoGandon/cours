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
$x \in \{ 2,3 \}$
$y \in \{ 2,3 \}$
$z \in \{ 4,5 \}$
$w \in \{ 1,2 \}$

# Exercice 3 ?

1. $D(x)=\{ 0,\dots,20 \}$
   $D(Y)=\{ 0,\dots,17 \}$
   $X\geq 5$
   $Y=2X$
   
   Consistance d'arc :
	   - $D(x)=\{ 5, 6, 7, 8 \}$
	   - $D(Y)=\{ 0, 12, 14, 15 \}$
	   - $\mathcal{O}(d^2)$

   Consistance de borne :
	   - $D(X)=5..8$
	   - $D(Y)=10..16$
	   - $AC1 : \mathcal{O}(n^3 d^3)$
	   - $AC3 : \mathcal{O}(n^2 d^3)$
	   - $AC4 : \mathcal{O}(n^2 d^2)$

2. .
	  - $D(X)=12..20$
	  -  $D(Y)=2..10$
	  -  $D(Z)=5..10$
	  -  $X+Y=2Z$
	  -  $X=2Z-Y$
	  -  $Y=2Z-X$
	  -  $Z=\frac{1}{2}(X+Y)$
   
   Règles de propagation de consistance de borne :
	  -  $\text{min}~ X \leftarrow \text{maximum}(2\times\text{min}(Z)-\text{max}(Y), \text{min}(X))$
	   - $\text{max}~ X \leftarrow \text{minimum}(2\times\text{max}(Z)-\text{min}(Y), \text{max}(X))$
	   - $\text{min}~ Y \leftarrow \text{idem X}$
	   - $\text{max}~ Y \leftarrow \text{idem X}$
	   - $\text{min}~ Z \leftarrow \text{maximum}\left( \left\lceil\frac{\text{min}(X)+\text{min}(Y)}{2}\right\rceil, \text{min}(Z) \right)$
	   - $\text{max}~ Z \leftarrow \text{minimum}\left( \left\lfloor\frac{\text{min}(X)+\text{max}(Y)}{2}\right\rfloor, \text{max}(Z) \right)$
   
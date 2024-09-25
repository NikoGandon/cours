# Exercice 1

1.  ![[Drawing 2024-09-18 08.04.24.excalidraw]]
   Le $K_9$ contient $\frac{9 \times 8}{2} = 36$ arêtes.

2. Soit $G=(V,E)$, un graphe planaire et connexe
   ![[Drawing 2024-09-18 08.51.19.excalidraw]]
	1. Soit $\mathcal{T}$ un arbre couvrant de $G$, son nombre de sommets est égal au nombre $n$ de sommets de $G$. Si $\mathcal{T}$ est un arbre, on note $m_{t}$ sont nombre d'arêtes, alors ($n=m_{t} +1$).
	2. Soit $G^{*} = (V^{*}, E^{*})$ le graphe dural de $G$. Soit $\mathcal{T}^{*} \subseteq E^{*}$, les arêtes de $G^{*}$ correspondent aux arêtes de $E \backslash T$.
	   $\mathcal{T}^*$ est un arbre couvrant de $G^*$. En effet, les arêtes de $\mathcal{T}^*$ relient toutes les faces car $\mathcal{T}$ n'a pas de cycle. De plus $\mathcal{T}^*$ n'a pas de cycle, sinon ils séparent des sommets de $G$ à l'intérieur du cycle et $\mathcal{T}$ ne serait pas un arbre couvrant. Dont $\mathcal{T}^*$ est un arbre couvrant de $G^*$ 
	3. Puisque les sommets de $\mathcal{T}^*$ sont les faces de $G$ et que $\mathcal{T}^*$ est un arbre, on a $$f=m_{t^{*}}+1$$
	   où $m_{t^{*}}$ désigne le nombre d'arêtes de $T^{*}$
	   
	   4. En faisant $R_{1}+R_{2}$ :
	   $$n+f=m_{t}+m_{t^{*}}+2$$$$\Leftrightarrow n - m + f = 2$$
3. Montrons que le $K_5$ n'est pas planaire, c'est à dire qu'il ne peut pas être plongé sur le plan sans qu'il n'y ait d'arêtes qui se croisent. On démontre que $K_{5}$ ne respecte pas la formule d'Euler.
   Pour le$K_{5} : n=5$ et $m=10$
   Chaque sommet $\alpha$ apparait dans au plus $4$ faces : 
   ![[TD 2 - Exercice 1.3||200px]]
   Car dans le $K_{5}$, chaque sommet a au plus $4$ arêtes.
   De plus, chaque face est délimitée par au moins $3$ arêtes.
   Donc $f \leq \frac{n \times 4}{3} \Leftrightarrow \frac{5 \times 4}{3} < 7$.
   Ainsi, $n - m + f < 5 - 10 + 7 = 2$.
   Donc le $K_5$ ne respecte pas Euler ($n - m + f = 2$), et ici $n-m+f<2$
4. ![[Drawing 2024-09-18 09.35.56.excalidraw||1000px]]
   Le tore est une surface de genre $1$ 
   >[!info] 
   >Une surface de genre est le nombre d'anse (trou) d'une surface de l'objet étudié.
      
5. Soit $K_{n}$ le graphe complet à $n$ sommets. Il y a $n$ sommets et $\frac{n \times (n-1)}{2}$ arêtes.
   Donner une borne sur son nombre $f$ de face 
   $$f \leq \frac{n \times (n-1)}{3}$$
   Donc $$n-m+f \leq n- \frac{n \times (n-1)}{2} + \frac{n \times (n-1)}{3}$$
   $$\leq \frac{6n}{6}- \frac{3n \times (n-1)}{6} + \frac{2n \times (n-1)}{6}$$
   $$\leq \frac{6n-3n^2+3n+2n^2-2n}{6}$$
   $$\leq \frac{n \times (7-n)}{6}$$
   D'après la formule généraliste d'Euler : $n-m+f=2-2g$
   Donc $2-2g \leq \frac{n(7-n)}{6} \Leftrightarrow g > \frac{n \times (n-7)}{6}$
   

# Exercice 2

1. Soit $G, \alpha$ et $beta$ un graphe et deux couleurs. $G(\alpha, \beta)$ est le sous graphe de $G$ induit par les sommets des couleurs. $H(\alpha, \beta)$ une composante connexe de $G(\alpha, \beta)$.
   Montrons qu'on échange les couleurs dans $H(\alpha, \beta)$ on obtient toujours une coloration de $G$ : 
   ![[TD 2 - Exercice 2.1]]
   Soit $\alpha$ en rouge et $\beta$ en bleu.
   Pour toute arête à l'intérieur de $H(\alpha, \beta)$, les extrémités ont bien des couleurs différentes (sinon cela ne serait pas valide) . De plus, pour toute arête $\{u,v\}$ tel que $u \in H(\alpha, \beta)$ et $v \notin H(\alpha, \beta)$ nous savons que $v$ n'interfère ni la couleur $\alpha$ ni la couleur $\beta$. Donc, en changeant les couleurs, ce graphe reste valide.
2. Soit $G$ un graphe planaire et $x$ un sommet avec 5 voisins, chacun de couleur différentes:
   ![[TD 2 - Exercice 2.2]]
	1. On ne peut pas avoir à la fois les sommets $a$ et $c$ dans une même composante bi coloré de $G'(\alpha, \gamma )$ <u>et</u> dans le même temps les sommets $b$ et $d$ dans une même composantes bi colorée de $G'(\beta, \delta)$.
	   ![[TD 2 - Exercice 2.2.1||200px]]
	   Ce n'est pas possible d'avoir ces 2 propriétés simultanément car le chemin bi coloré $\alpha, \gamma$ en y ajoutant le sommet $x$ défini un cycle où le sommet $b$ se trouve à l'intérieur et le sommet $d$ à l'extérieur. Comme tous les sommets du chemin soit $\alpha$ ou $\gamma$, aucun d'entre eux ne peut être $beta$ ou $\delta$.
	2. Soit $G''$ ayant $a,b,c,d,e$ utilisent seulement 4 couleurs.
	   Soit $H(\beta, \delta)$ la composante bi coloré contenant $d$ (et donc pas $b$). On lui applique la question $1$. Ainsi, $d$ obtient la même couleur que $b'$.
	   Aussi, le voisinage de $x$ n'utilise que 4 couleurs et il devient possible de colorier $x$ avec la couleur inutilisée. 
	3. Dans notre graphe planaire : 
		- Si on a un sommet de degré $5$, on oublie le sommet et on colorie le reste du graphe
			- Si le voisinage de $x$ n'utilise que $4$ couleurs, alors on colorie $x$ avec la couleur manquante
			- Si le voisinage de $x$ utilise les $5$ couleurs, alors les questions précédentes nous assure qu'on peut recolorier (?) les autres sommets de sorte à libérer une couleur dans le voisinage de $x$
		- Si le sommet $x$ est de degré $\leq 4$, alors son voisinage n'utilise pas 5 couleurs différentes. Cela montre que tout graphe planaire de degré maximum $5$ est 5-colorable.
3. 
   __Cas de base__ : $n \leq 6$
	   Donc $\Delta(G)\leq 5$ et par la présence ??????
	   définition du graphe $G$ précédent, $G$ est 5-colorable
	__Initialisation__ : Soit $n > 6$
		Supposons que tout graphe planaire ayant au plus $n-1$ sommets est 5-colorable.
		Montrons que le graphe $G$ à $n$ sommets est lui aussi 5-colorables.
		Regardons le degré moyen des sommets de $G$ :
		$d(G)=\frac{\sum_{v \in V} d(v)}{n} = \frac{2 \times m}{n} \leq \frac{2(3n-6)}{n}=\frac{6n}{n}-\frac{12}{n}=6-\frac{12}{n}$. Le degré moyen est plus petit que $6$.
		Donc il existe des sommets de degré au plus $5$ dans le graphe de $G$.
		Soit $x$ l'un de ces sommets, $G \setminus x$ a $n-1$ sommet <u>et</u> il est planaire donc par hypothèse d'induction, $G \setminus x$ admet une 5-coloration.
		Puisque $d(x) \leq 5$ il est possible de trouver une ?coloration? n'utilisant qu'au plus 4 couleurs dans son voisinage. 
		On peut donc colorer $x$ et donc $G$.

```
si G n'est pas connexe alors :
	Pour chaque composante de connexe C de G:
		5-col(C)

Sinon :
	Si n >= 2 alors
		- Soit x au sommet de degré au plus 5
		5-col(G \ x)
		- Au besoin, on s'arrange pour n'utiliser que 4 couleurs de son voisinage
	Sinon :
		On colore l'unique sommet sommet avec une couleur quelconque
```
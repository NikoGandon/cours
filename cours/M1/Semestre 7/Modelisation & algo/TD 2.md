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
   ![[Drawing 2024-09-18 09.36.48.excalidraw||200px]]
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

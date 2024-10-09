>[!note] 
>__Entrée__ : un ensemble $\mathcal{N}$ de $n$ points dans le plan
>__Paramètre__ : $k$
>__Question__ : existe-t-il $k$ droites intersectant tous les points de $\mathcal{N}$

- L'ensemble des points $\mathcal{N}$ devient vide : instance positive !
- $k$ devient inférieur ou égal à $0$ : instance négative
- Sinon : Règle non applicable

Une instance positive ne peut avoir plus de $k^2$ points -> au plus $k$ points couvrent <u>chacune</u> au plus $k$ points.

>[!note] En résumé
>__Entrée__ une instance de notre problèùe
>__Sortie__ une instance <u>équivalente</u>
>  - Contenant au plus $k^2$ points
>  - Calculée en $\mathcal{O}(n^2)$



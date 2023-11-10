---
quickshare-date: 10-11-2023 02:15:15
quickshare-url: "https://noteshare.space/note/clorxek7e717601mwc1uifls1#Px3nEkYqQ4UnDXt22gkOlFBAvfGsxb1fXO+SbmuApZg"
---
>[!info] 
>Il est important de bien répertorier ses modifications dans des commits expliquant bien les modifications apportées
>Cependant, il peut avoir plusieurs modifications dans un fichier, et celles-ci ne sont pas forcément liées

> [!example] 
> Imaginons que nous ajoutons dans un fichier une fonction ``addition()`` et que - sans commit - nous modifions une autre fonction ``envoyerResultat()`` dans ce même fichier pour une meilleure performance.
> Comme vu dans le premier cours, nous avons ici 2 possibilités de message de commit :
> - ``feat: addition() .....``
> - ``perf: optimisation de envoyerResultat``

```
>$ git status
>$     modified : main.cpp
>$ git add .
```

Ces commits sont bons uniquement pour une partie du code, mais pas les deux.
On ne veut pas avoir un titre de commit trop long ou trop vague comme :
- ``feat & perf: ajout d'une fonction addition et amélioration de envoyerResultat()``
- ``feat & perf: ajout de fonction et amélioration d'une autre``

Mais Git nous permet de séparer les modifications apportées, par exemple en ligne de commande, on peut séparer en utilisant l'option ``-p`` suite à ``git add``.

> [!example] 
> ```
> >$ git status
> >$     modified : main.cpp
> >$ git add -p main.cpp
> >$ + template< typename T > addition(T& a, T& b){
> >$ + return a + b;
> >$ + }
> > (1/2) Stage this hunk [y, n, q, a, d, j, J, g, /, e, ?]?
> > y
> >$ + //Performance
> > (2/2) Stage this hunk [y, n, q, a, d, j, J, g, /, e, ?]?
> > n
> >$ git commit -m "feat: ajout d'une fonction pour additionner"
> >$ git add main.cpp
> >$ git commit -m "perf: optimisation d'envoyerResultat()"
> ```

>[!note] 
> ``y`` - Enregistrer cette partie
>``n`` - Ne pas enregistrer cette partie
>``q`` - Quitter; ne pas enregistrer cette partie ou n'importe laquelle des suivantes
>``a`` - Enregistrer cette partie et les autres parties du fichier
>``d`` - Ne pas enregistrer cette partie ou n'importe laquelle des suivantes
>``j`` - Laisser cette partie indécise, voir les autres parties indécises
> ``J`` - Laisser cette partie indécise, voir les autres parties
>``g`` - Sélectionner une partie à voir
>``/`` - Chercher une partie correspondant à ce REGEX
>``e`` - Editer manuellement cette partie
>``?`` : affiche l'aide

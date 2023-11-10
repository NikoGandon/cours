---
quickshare-date: 10-11-2023 03:45:31
quickshare-url: "https://noteshare.space/note/clos0mnk6739801mw28c9hhr9#KpAPlYrN5qhjAdAvgla15o+Edg0AehOofNU7aZbr9OY"
---
>[!info] Qu'est-ce qu'un conflit ?
>Un conflit sur git est une chose courante dans la fusion (que ce soit une branche locale comme distante). Cela se produit lorsque deux versions du même fichier ont été modifiées de manière incompatibles, et Git ne peut pas automatiquement fusionner ces modifications.

>[!info] Comment ça peut arriver ?
>Il existe plusieurs facteurs qui pourraient créer ces conflits, par exemple :
>- On travaille sur 2 PC A et B : on modifie et on push depuis A, on modifie le même fichier et on push depuis B sans avoir tiré les modifications au préalable --> conflit
>- On travaille en groupe, au moins 2 personnes A et B ont travaillé sur le même fichier, A l'envoie avant B, B reçoit une erreur --> conflit

>[!question] Comment on peut régler ça ?
>Si on utilise la ligne de commande, il faut régler ça manuellement en ouvrant le fichier depuis un éditeur de texte (VSCode, notepad, VIM, ...).
>Il existe des logiciels qui permettent de gérer les conflits de manière graphique, plus conviviale et limite les erreurs.

>[!note] En utilisant VSCode
>Si on utilise VSCode, nous pouvons avoir un moyen de gérer les conflits de manière plus simple, pour chaque ligne de conflit, on nous propose 3 choix :
>- Accepter les modifications entrantes : On abandonne les modifications apportées sur notre poste au profit de l'autre branche
>- Accepter les modifications locales : On force pour ne prendre que nos modifications au détriment de l'autre branche
>- Accepter les 2 modifications : On les fusionne

>[!note] En utilisant un éditeur de texte simple
>Si nous utilisons VIM, notepad ou autre éditeur de texte simple, nous auront des modifications sur les fichiers conflictuels

>[!example] 
>Nous avons un conflit sur le fichier main.cpp, voici comment se présente maintenant ce fichier :
>```
><<<<<<<< HEAD
> Modification locale
> =============
> Modification distante
> >>>>>>> db478556d
>```

> [!info] 
> ``HEAD`` représente les modifications locales que nous souhaitons envoyer.
> ``=`` : séparent les lignes de conflits
> ``db478556d`` : représente le hash du commit qui se met en conflit avec nos modifications

>[!info] Régler le conflit sur un éditeur de texte simple
>Une fois que nous savons ce qui apporte ce conflit, nous pouvons décider de fusionner, garder uniquement la modification locale ou l'effacer pour la modification distante
>Pour ça, on doit juste supprimer les lignes conflictuelles, les séparateurs et les flux des modifications entrantes ``>>>> db478556d`` et locales ``<<<<<< HEAD``

>[!example] Pour reprendre l'exemple
>Nous décidons de garder les 2 modifications, voici donc le contenu du fichier avant le push
>```
>Modification locale
>Modification distante
>```
>Nous pouvons maintenant enregistrer ça en commit, et on peut push

>[!note] 
>Nous pouvions aussi juste garder uniquement nos modifications :
>Voici le contenu avant le push
>```
>Modification locale
>```
>Comme uniquement les modifications entrantes :
>```
>Modification distante
>```

>[!note] 
 La communication dans l'équipe peut limiter les conflits, une bonne organisation permet d'éviter de perdre du temps.
 Il vaut mieux également de synchroniser souvent les modifications en les tirants (commande ``pull`` et ``fetch``)

> [!info] Synchronisation fréquente
> Il est essentiel de maintenir votre copie locale du référentiel à jour en récupérant régulièrement les dernières modifications de la branche distante. Pour cela, on peut utiliser la commande `git fetch`. Cette commande récupère les dernières modifications du dépôt distant sans les fusionner dans votre branche de travail actuelle.
> Après avoir effectué un `git fetch`, on peut examiner les modifications récupérées en utilisant des commandes telles que `git log origin/nom_de_la_branche` pour visualiser l'historique des commits de la branche distante. Si les modifications peuvent être intégrée, on peut utiliser la commande ``git merge``.


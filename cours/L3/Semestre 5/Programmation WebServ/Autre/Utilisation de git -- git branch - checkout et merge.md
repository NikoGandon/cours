---
quickshare-date: 10-11-2023 03:09:12
quickshare-url: "https://noteshare.space/note/clorzbydn726701mwn74ep9s2#DONsPUXYneg1jBcJEHchzrwMcHk1ozP+2Y5uG9x+vAs"
---
>[!note] Commandes
>On a vu au début qu'il existait 3 commandes de git pour gérer des branches:
>- ``branch`` : liste les branches et indique sur laquelle on travaille
>- ``checkout`` : change de branche de travail
>- ``merge < branch >`` : fusionne la branche sur laquelle on travaille avec celle demandée

Nous verrons que quelques commandes parmi celles-ci, mais on peut toujours voir toutes les options / commandes disponibles en faisant ``git < commande > -h``.
# Commande ``git branch`` :

>[!info] Les commandes simples
>- ``-a, --all`` : liste les branches locales et distantes
>- ``-d, --delete`` : supprime la branche si elle est fusionnée
>- ``-D`` : supprime une branche, même si celle-ci n'est pas fusionnée
>- ``-l, --list`` : liste les noms des branches

>[!example] Afficher les liste, et supprimer une branche
>```
>>$ git branch -l
>>$     * main
>>$        projet
>>$ git branch -a
>>$     * main
>>$        projet
>>$        remotes/origin/HEAD -> origin/main
>>$        remotes/origin/main
>>$        remotes/origin/projet
>>$ git branch -D projet
>>$ git branch -l
>>$     * main
>>$        projet
>```

Si nous voulons créer une branche, nous devons utiliser la commande ``checkout``

# Commande ``git checkout`` :

>[!info] Les commandes simples
>- ``-b < nom de branch >`` : Crée la branche et s'y met automatiquement dessus
>- ``-B`` : Crée la branche et s'y met automatiquement, si elle existe elle sera reset
>- ``< nom de branch >`` : se connecte à la branche spécifiée par son nom
>- ``< hash du commit >`` : revient à un état spécifique du répertoire suivant le hashage du commit

>[!example] Créer une branche
>```
>>$ git checkout -b nouvelleBranche
>>$ git branch -l
>>$     * nouvelleBranche
>>$        main
>>$        projet
>>$ git checkout main
>>$ git branch -l
>>$     * main
>>$        nouvelleBranche
>>$        projet
>```

Nous pouvons aussi utiliser la commande ``switch`` qui est plus simple et conviviale à utiliser :

>[!example] 
>```
>>$ git switch -c nouvelleBranche
>>$ git branch -l
>>$     * nouvelleBranche
>>$        main
>>$        projet
>>$ git switch main
>>$ git branch -l
>>$     * main
>>$        nouvelleBranche
>>$        projet
>```

Une fois que nous avons créée les branches nécessaire et que nous les utilisons, il nous faut maintenant les fusionner, en utilisant la commande ``merge``

# Commande ``git merge`` :

> [!info] Les commandes simples
> - ``< nomBranche >`` : Fusionne la branche spécifié dans la branche actuelle
> - ``< hashCommit >`` : Fusionne le commit spécifié dans la branche actuelle

>[!error] Les conflits
>Il peut arriver qu'il existe des conflits, cela peut dépendre de plusieurs facteurs, pour régler ces conflits, nous devons le faire manuellement (ou avoir un éditeur permettant de gérer les conflits - nous verrons ça plus tard)

>[!info] Après avoir réglé les conflits ?
>Il y a deux suites possibles après avoir réglé le conflit :
>- Utiliser la commande ``git merge --continue``
>- Utiliser la commande ``git commit -m 'message'``

>[!info] Si je veux annuler la fusion
>On peut annuler une fusion si elle est incomplète (par exemple nous n'avons pas réglé les conflits) en utilisant la commande ``git merge --abord``

>[!attention] 
>Quand on effectue une fusion, on doit être sûr de nous trouver sur la bonne branche.
>Pour rappel, on doit se situer dans la branche qui doit prendre les modifications, puis lancer la commande ``git merge < nomBranche >`` pour fusionner les modifications de ``< nomBranche >``.

>[!example] 
>Nous avons deux branches : ``main`` et ``dev``.
>Nous avons apportés des modifications dans ``dev`` et nous souhaitons les mettre dans ``main``.
>Pour faciliter l'exemple, il n'y aura pas de conflit.
>```
>>$ git branch
>>$     * dev
>>$        main
>>$ git switch main && git branch
>>$     * main
>>$        dev
>>$ git merge dev
>```


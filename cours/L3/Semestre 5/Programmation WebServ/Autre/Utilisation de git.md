>[!info] Qu'est-ce git
>Git est un système de gestion de version.
>L'utilité est d'avoir une possibilité de revenir à une version antérieur, de suivre l'historique de développement, de faire du développement en parallèle en utilisant différentes 'branches'.
>Ça facilite la collaboration, chaque personne peut travailler de son côté sur le projet sans avoir besoin de connexion à internet, le seul moment où il en aura besoin sera pour récupérer et pousser les modifications apportées.

> [!info] Comment l'utiliser ?
> En ligne de commande ou avec un logiciel comme Github Desktop (plus simple pour quelqu'un qui ne s'y connait pas), certaines commandes ne marchent que si nous travaillons avec un dépot distant (par exemple, github, gitlab, ...)

>[!info] Les commandes de base
>Pour l'utilisation en ligne de commande, chaque commande aura le préfix ``git``
>- ``status`` : donne l'état des fichiers/dossiers modifiés : ``deleted``, ``new file``, ``modified`` par exemple
>- ``add`` : ajoute dans un commit les fichiers/dossiers spécifié
>- ``commit`` : section des commits, pour le cas de pousser un commit, on utilise le préfixe ``-m`` pour ajouter un message (obligatoire) 
>- ``push`` : on "pousse" nos commits dans le dépôt distant
>- ``pull`` : on récupère et on fusionne depuis le dépôt distant
>- ``fetch`` : on récupère sans fusionner depuis le dépôt distant
>- ``branch`` : liste les branches et indique sur laquelle on travaille
>- ``checkout < branche >`` : change de branche de travail
>- ``merge < branche >`` : fusionne la branche sur laquelle on travaille avec celle demandée
>- ``diff`` : affiche les différences des fichiers non commits avec ceux commit
>- ``stash`` : met de côté les modifications pour les traiter plus tard
>- ``reset`` : annule les modifications
>- ``log`` : affiche l'historique des dépôts
>- ``clone < URL >`` : clone un dépôt git distant dans le répertoire local


>[!note] Pour les commits
>Il existe plusieurs suffixes pour ``commit``, mais voici les 2 plus importants :
>- ``-m "votre message"`` : Crée un commit avec les fichiers/dossiers ajoutés et y attribue une description
>- ``--amend`` : Permet de modifier la description du dernier commit, si celui-ci n'a pas été push
>  Si la description est vide, alors ce dernier commit sera annulé

>[!example] Exemple
>```
>$ git status
>$     modified : fichier1.txt
>$     modified : fichier2.txt
>$ git add .
>$ git commit -m "Initialisatio du dossier"                  // Faute
>$ git commit --amend -m "Initialisation du dossier"
>```

# Comment faire la description des commits

>[!info] 
>Pour plus de clarté, il vaut mieux suivre une norme de nommage des commits.
>Elle se comporte comme suit:
>< type > : < sujet >
>< corps >

> [!note] Qu'est-ce qu'un type ?
> Il nous informe du type de commit, on utilisera les suivants :
> - feat : pour les nouvelles fonctionnalités du site
> - fix : pour la correction de bug
> - perf : pour l'amélioration des performances
> - docs : pour l'ajout / modification de la documentation
> - test : pour l'ajout / modification de tests
> - style : pour tout ce qui est mise en forme, nom de variable, ...
> - refactor : modification qui n'apporte aucune nouveauté ni d'amélioration de performance

>[!note] Comment faire pour le sujet ?
>Le sujet doit être très concis, quelques mots uniquement (en général, pas plus de 50 caractères)
>Il doit présenter les changements effectués dans le commit.

>[!note] Pour le corps
>Ici on décrit les changements effectués. il suffit de faire 'entrée' avant la fin du message de commit.

> [!example] Exemple
> Prenons par exemple un fichier db.js que nous venons de créer, nous avons codé la partie qui gère la connexion à une base de donnée, voici un exemple des commandes utilisées :
> ```
> $ git status
> $     ...
> $     untracked files :
> $     db.js
> $ git add .
> $ git commit -m "feat: connexion BDD                        // Appuie sur 'entrée'
> Script permettant la connexion à une base de donnée"
> $ git push
> ```

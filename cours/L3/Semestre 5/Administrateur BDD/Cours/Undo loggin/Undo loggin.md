> [!summary] 
> Est une technique de journalisation dans la gestion de la base de donnée qui enregistre les modifications apporté aux données dans un journal 'log'
> Ce journal enregistre les anciennes valeurs des données avant leur modification, assure la durabilité des données en les écrivant dans un stockage, permettant d'annuler des transactions en cas de panne, pour assurer la cohérence des données.
> C'est essentiel pour maintenir l'intégrité de la BDD.


> [!info] 
> Un enregistrement $<T, X, v>$ indique que la transaction $T$ a modifié la valeur de $X$, $v$ étant son ancienne valeur

> [!info] 
> $<START\ T>$ indique que la transaction $T$ a commencé
> $<COMMIT\ T$ indique que la transaction $T$ est terminé, sans garanti qu'elle soit sur disque
> $<ABORT\ T>$ indique que la transaction $T$ n'a pas pu se terminer normalement

>[!info] 2 règles 
>..


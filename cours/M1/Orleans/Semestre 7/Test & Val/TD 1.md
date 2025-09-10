# Exercice 1

1. Il y a 60 entrées possibles ($3 \times 4 \times 5$)
2. On peut tester 20 ($5 \times 4$) tests.
3. 
   
| marque | année | couleur |
|:------:|:-----:|:-------:|
| Toyota | 2015  | marron  |
|  Ford  | 2016  | marron  |
| Honda  | 2017  | marron  |
| Toyota | 2018  | marron  |
| Honda  | 2015  |  bleu   |
|  Ford  | 2016  |  bleu   |
| Toyota | 2017  |  bleu   |
|  Ford  | 2018  |  bleu   |
| Honda  | 2015  |  rouge  |
| Toyota | 2016  |  rouge  |
| Honda  | 2017  |  rouge  |
| Toyota | 2018  |  rouge  |
| Toyota | 2015  |  verte  |
| Honda  | 2016  |  verte  |
| Toyota | 2017  |  verte  |
|  Ford  | 2018  |  verte  |
| Toyota | 2015  |  grise  |
| Honda  | 2016  |  grise  |
| Toyota | 2017  |  grise  |
| Toyota | 2018  |  grise  |
# Exercice 2

|          Condition d'entrée           |                CE valide                |          CE invalide           |
| :-----------------------------------: | :-------------------------------------: | :----------------------------: |
|     nbr de descripteur de tableau     |                $=1, >1$                 |             aucun              |
|            borne supérieur            | supérieur ou égale à la borne inférieur | inférieur à la borne inférieur |
|            nom symbolique             |        1 à 6 lettres ou chiffres        |            $0, >6$             |
|                  //                   |         commence par une lettre         |    commence par un chiffre     |
|           nbr de dimension            |                  $1-7$                  |            $0, >7$             |
|            borne inférieur            |                spécifié                 |             aucun              |
|                  //                   |              non spécifié               |             aucun              |
|          nom de var entière           |       comporte lettres & chiffres       |  comporte un caractère autre   |
| le nom de var commence par une lettre |                   oui                   |              non               |
|               constante               |          $\in [-65534..65535]$          |      $<-65534$, $>65534$       |

# Exercice 3

1. 
   
|             | Angle aigu | Angle obtus |          Angle droit          |
| :---------: | :--------: | :---------: | :---------------------------: |
|   Scalène   | $(6,5,3)$  | $(5,6,10)$  |           $(3,4,5)$           |
|   Isocèle   | $(6,1,6)$  |  $(7,4,4)$  | $(\sqrt{ 2 }, 2, \sqrt{ 2 })$ |
| Équilatéral | $(4,4,4)$  | impossible  |          impossible           |


# Exercice 4

| nombre de PJ | Taille totale PJ | Résultat |
| :----------: | :--------------: | :------: |
|      0       |        0         |    OK    |
|      1       |        20        |    OK    |
|      1       |        21        |    KO    |
|      10      |        20        |    OK    |
|      10      |        0         |    OK    |
|      11      |        0         |    KO    |
|      10      |        21        |    KO    |
|      11      |        20        |    KO    |

# Exercice 5

Soit un fichier de $100$ champs de 3 colonnes : nom de l'étudiants (20 caractères), son sexe (1 caractère) et ses notes dans 5 matières (entier $[0;20]$)

Le programme doit calculer la moyenne de chaque étudiants, la moyenne G. par sexe et par matière, et calculer le nombre d'étudiants qui ont réussi ($\text{moyenne} > 10$).

1. passage d'un fichier vide
2. passage d'un fichier à $1, ~ 2, ~ 99, ~ 100 \text{ et } 101$ champs
3. Étudiants dont le nom est à $0, ~19, ~ 20 \text{ et } ~ 21$ caractères
4. Étudiants dont le nom est composé d'un ou plus caractères non alphabétique
5. Avec aucune note
6. avec $4, ~ 5 \text{ et } 6$ notes
7. Avec un code sexe vide
8. Avec un code sexe avec 2 caractères
9. Avec un code sexe invalide ($\notin [M, F]$)
10. Avoir une note $> 20$ ou $< 0$
11. Avoir une note $\notin \mathbb{N}$


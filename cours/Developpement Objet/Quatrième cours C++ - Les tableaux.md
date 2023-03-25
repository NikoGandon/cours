Le langage C++ peut gérer des tableaux. Il en gère deux types :
- [[#Les tableaux statiques]]
- [[#Les tableaux dynamiques]]

# Les tableaux statiques

Les tableaux statiques sont des tableaux dont la taille est prédéfini.
Avec le C++ moderne, on peut en créer de deux façons différentes :
```cpp
#include<array> //Pour std::array<>
type nomTableau[tailleTableau];
std::array<type, tailletableau> nomTableau;
```

Les #types sont ce que vous voulez.

## Création de tableau avec []

La vieille méthode pour créer des tableaux, il suffit juste de mettre le type de variable que stockera le tableau, le nom de votre tableau suivi de sa taille entre-crochet
```cpp
int test[15];
```
On crée un tableau ``test`` qui comptera 15 éléments.

Par défaut, toutes ses valeurs sont égales à ``0``.
On peut initialiser un tableau :
```cpp
int test[10] = {1, 5, 3, 8, 6};
int test2[]  = {2, 5, 6, 7, 9, 6, 14, 6, 9, 74, 6, 3};
```

On les affiche : 
```cpp
1 5 3 8 6 0 0 0 0 0
2 5 6 7 9 6 14 6 9 74 6 3
```


Dans le premier cas, on indique explicitement que le tableau aura une taille de 10 éléments, on peut en initialiser en 0 et 10 et le reste sera à 0.
Dans le second cas, on peut initialiser avec autant d'élément qu'on veut.

Dans les deux cas, une fois passé leur ligne d'initialisation, impossible d'ajouter un élément, on peut juste les modifier.

## Création de tableau avec ``std::array``

Le C++ moderne apporte avec lui ``std::array<>`` dans sa bibliothèque ``array``.
Attention, la taille de ``std::array`` ne se définit pas lors du runtime, mais directement dans le code, donc impossible de faire : 
```cpp
#include <array>     //Pour inclure std::array
#include <iostream>

int taille;
std::cin >> taille;
std::array<type, taille> nomTableau; //Ne compilera pas
```

On doit forcément passer par une constante :
```cpp
const n = 15;
std::array<int, n> tab;
```



# Les tableaux dynamiques

Les tableaux dynamiques sont des tableaux sont la taille n'est pas définis à la compilation et l'éxécution, leur taille peut varier.
On utilise ``std::vector`` pour la création de tableau dynamique :
```cpp
#include <vector>     //Pour inclure std::vector
std::vector<type> nomTableau;
```

Pour ajouter du  contenu dans un tableau dynamique, on utilse la fonction ``push_back(valeur)`` qui ajoute un élément placé à la fin.
```cpp
nomTableau.push_back(10);
nomTableau.push_back(105);
nomTableau.push_back(3);

for(auto elem : nomTableau){
	std::cout << elem << "\n";
}
```

Ce qui nous donnera à l'éxécution 
```
10
105
3
```

# Avoir accès aux éléments du tableau
Que ce soit statique ou dynamique, vieux ou nouveau, on peut avoir accès aux éléments d'un tableau de la même manière en utilisant l'opérateur ``[]``.
```cpp
tableau[i];
```
Retournera l'élément à l'indice ``i`` du tableau.

**Attention : l'indice maximal d'un tableau est size() - 1**.

Mais pour ``array`` et ``vector``, il existe aussi la fonction ``at(i)``.
```cpp
std::array<int, 5> arr { {1, 2, 3, 5, 6} };
std::cout << arr.at(2);
```

La principale différence entre ``operator[]`` et ``at()`` est que ``at`` vérifie si l'indice dont on tente d'accéder existe et soulève une erreur ``std::out_of_range``.
si ce n'est pas le cas, alors que ``operator[]`` ne vérifie pas et que son comportement est indéfini.

Exemple d'erreur, ici on a un tableau de 5 éléments, on veut acceder au 6ème :
```
terminate called after throwing an instance of 'std::out_of_range'
  what():  array::at: __n (which is 5) >= _Nm (which is 5)
```

En général, nous utilisons rarement ``at()``.

# Modifier un élément d'un tableau

On veut modifier un élément d'un tableau, pour ce faire on accède à l'indice voulu et on lui assigne une nouvelle valeur.
```cpp
arr[2] = 10;
arr.at(2) = 10;     //Ne marche que pour std::vector et std::array
```



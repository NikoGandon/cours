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

Les #types sont ce que vous voulez

## Création de tableau avec []

La vieille méthode pour créer des tableaux

## Création de tableau avec ``std::array``

Le C++ moderne apporte avec lui ``std::array<>`` ...
Attention, la taille de ``std::array`` ne se définit pas lors du runtime, mais directement dans le code, donc impossible de faire : 
```cpp
int taille;
std::cin >> taille;
std::array<type, taille> nomTableau; //Ne compilera pas
```


# Les tableaux dynamiques

Les tableaux dynamiques sont des tableaux sont la taille n'est pas définis à la compilation et l'éxécution, leur taille peut varier.
On utilise ``std::vector`` pour la création de tableau dynamique :
```cpp
#include<vector>
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

Comme [[#Les tableaux statiques|les tableaux statiques]], on peut avoir un accès dans 
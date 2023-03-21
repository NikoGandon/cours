
```cpp
#include<iostream>

int main(){
	std::cout << "HW\n";
	return 0;
}
```

``std`` sert à préciser que ce qui suit vient de la bibliothèque standard.
`#include` est une indication de préprocesseur, elle sert à inclure des fichiers `header`.

Le schéma de création de fonction type est le suivant : 
```cpp
type nomFonction([Arg1, Arg2, ...]){
	//Code
	return ...; //type de retour étant le même que le type de fonction
}
```
``type`` pouvant être ``int, long, char, float, double, void, std::string, std::vector, std::array,...``
A savoir que `void` ne retourne rien.

Comme la plupart des langages qu'on a vu, il existe les conditions et les boucles
```cpp
if (condition){ //code
}
else if(){ ... }
else { ... }

//boucle
while(condition){ ... }
do { ... } while (condition);
for(initialisation; condition; opération sur l initialisation) { ... }
```

Il est important de parler également des #pointeurs et #références en C++:

Une variable est stocké dans une adresse mémoire, le pointeur pointe cette case mémoire et la référence est l'emplacement de la case mémoire.
Un pointeur est une variable qui stocke l'emplacement de la mémoire / la référence.
Exemple : 
```cpp
int a = 15;
int * ptr = &a;
std::cout << a << "\n" << &a << "\n" << ptr << "\n" << *ptr;
```
On a un entier `a` qui a pour valeur initiale $15$.
On crée ensuite une variable ``ptr`` avec un astérix devant, cet astérix sert à indiquer que c'est un pointeur. On initialise ce pointeur avec ``&a``, la référence de ``a``.

Si on appelle un pointeur comme tel : ``ptr``, il retourne la référence de `a`, soit `&a`. Cependant, en l'appelant ``*ptr`` on accède à la valeur de l'emplacement `a`.

Donc la 3ème ligne donne à l'éxécution:
```
15
0x15fg
0x15fg
15
```

Comme des variables, on peut passer des références et pointeurs sur des fonctions :
```cpp
void test(int a, int& b){
	...
}
```

Il y a deux types de variable en arguments : par copie et par référence.
Ici, `a` est un passage par copie, on copie uniquement sa valeur.
`b`, lui, est sur un passage par référence, on ne pas copie sa valeur mais son emplacement dans la mémoire. Donc la fonction modifie directement la variable b.
Par exemple : 
```cpp
void test(int a, int& b){
	a++;
	b++;
	std::cout << "test : " << a << " " << b;
}

int main(){
	int a = 15, b = 10;
	std::cout << "main : " << a << " " << b;
	test(a, b);
	std::cout << "main : " << a << " " << b;
}
```

On initialise 2 variables `a` et `b` ayant respectivement pour valeur 15 et 10.
Donc on va avoir pour première sortie : 
```
main : 15 10
```
Ensuite, on appelle la fonction ``test(int a, int& b)``, qui prend en copie a et en référence b.
On incrémente ``a`` et ``b``. 
``a++ = 16`` et ``b++ = 11``, donc si on obtient :
```
main : 15 10
test : 16 11
```

Or, la variable ``a`` n'est modifié que dans la fonction ``test()``, contrairement à ``b`` qui est directement modifié depuis sa case mémoire.
Donc, on obtient au final :
```
main : 15 10
test : 16 11
main : 15 11
```
Dans ``main``, ``b`` a sa valeur qui a été modifié, car on a pris en paramètre de fonction ``test`` son emplacement mémoire et pas sa valeur. ``a`` quant à lui, dans ``main`` n'a pas été modifié car ``test`` a juste copié sa valeur.


Maintenant, on peut voir les #classes.

Une classe en C++ est similaire à une classe en Java : on a un nom de classe, des attributs et méthodes publics, privés et protégés.
Cependant, on peut avoir plusieurs classes dans un même fichier, on peut aussi utiliser des opérateurs. D'ailleurs on peut écrire des classes de deux manières différentes : un fichier qui gère la classe en entier ou alors deux fichiers : un fichier header et un fichier cpp
Un exemple de classe : 
```cpp
//fichier testClasse.h

class test {
public :
	test();     //Constructeur de la classe
	~test();    //Destructeur de la classe
	int fonctionTest();
};

//fichier testClasse.cpp
#include "testClasse.h"

test::test(){
//Code pour le constructeur
}

test::~test(){
//Code pour le destructeur, généralement vide
}

int test::fonctionTest(){
	//Code
	return ...;
}

```
Ou alors en un seul fichier :
```cpp
//fichier testClasse.h
class test{
	test(){
		...
	}
	~test(){...}
	int fonctionTest(){...}
}
```

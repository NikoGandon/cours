Après avoir eu une brève [[Premier cours C++ - Introduction|introduction]], on va attaquer dans le vif du C++ : ses #classes.

Comme on a vu, les classes peuvent avoir des parties ``public``, ``private`` et ``protected`` comme en Java.

Petit rappel sur ce que ça change ;
- ``public`` : méthode et attribut disponible partout
- ``private`` : méthode et attribut disponible uniquement dans la classe - mode par défaut
- ``protected`` : méthode et attribue disponible dans la classe et ses enfants.

Par défaut, sans spécifier, une classe en C++ est en ``private``.

Enfant, oui car le C++ gère l'héritage (multiple), une classe mère ayant x classes filles ou une classe fille ayant y classes mères mais nous verrons ça après.

Par convention et facilité de lecture, il est préférable d'écrire ses classes dans des fichiers séparés.

On va imaginer une classe ``objet`` simple, elle aura son constructeur et destructeur, des attributs et des méthodes pour elle.

```cpp
//fichier objet.h
#pragme once

class Objet{
private :
	int a;
	int b;
public :
	Objet();    //Constructeur de la classe
	~Objet();   //Destructeur de la classe

	void test();
}
```
```cpp
//fichier objet.cpp
#include "objet.h"
#include <iostream>

Objet::Objet(){
	a = 15;
	b = 10;
}

Objet::~Objet(){}

void Objet::test(){
	std::cout << a << " " << b;
}
```

A la création de ``Objet``, on appelle son constructeur. Dans ce cas, les attributs privées ``a`` et ``b`` valent respectivements ``15`` et ``10``.

# Créer un objet 

Pour utiliser un objet, c'est simple : il suffit d'appeler la classe suivit de son nom. Il ne faut pas oublier d'inclure le fichier d'en-tête.
Une fois l'objet créée, on peut utiliser ses méthodes publiques.

```cpp
#include "Objet.h"

int main(){
	Objet obj;
	obj.test();
}
```

Ça affichera :
```
15 10
```

# L'héritage

L'héritage est un grand principe de la P.O.O.
On peut imaginer une classe mère et une classe fille, comme une classe mère ayant plusieurs filles ou même une fille qui a plusieurs mères (🏳️‍🌈).

Pour indiquer l'héritage en C++, on fait comme suit :
```cpp
class fille : public mere, public maman
{
public :
	fille();
	~fille();
};
```
Explication : on crée une classe ``fille`` dérivée de la classe ``mere`` et ``maman`` (on prends leurs méthodes et attributs publiques, pas privées).

Par exemple : 
```cpp
#include <iostream>

class Animal{
protected :

	float nourriture;
	float boisson;

public :

	Animal(){
		nourriture = 0;
		boisson = 0;
	}
	~Animal(){}

	void mange(){
		nourriture++;
	}
	void boit(){
		boisson++;
	}
	void afficherEtat(){
		std::cout << "L'animal a mangé " << nourriture << "x et a bu " << boisson << "x.";
	}
};


class Chien : public Animal{
public :
	Chien(){
		nourriture = 15;
	}
	~Chien(){}
	void aboie(){
		std::cout << "wouf";
	}
	void afficherEtat(){
		std::cout << "Le chien a mangé " << nourriture << "x et a bu " << boisson << "x.";
	}
	void donneLaPate(){
		std::string a {"Tiens Nikola je te donne 500€ je t'aime viens on fait des bébés"}; 
	}
};

int main(){
	Chien Maximilien;
	Maximilien.mange();
	Maximilien.boit();
	//Maximilien.donneLaPate();
	Maximilien.afficherEtat();
}
```

En executant, on obtient :
```
Le chien a mangé 16x et a bu 1x.
```

Si on n'avait pas recrée la fonction ``afficherEtat()`` dans la classe ``chien``, nous aurions obtenu  ```
```
L'animal a mangé 16x et a bu 1x.
```

La classe ``chien`` a obtenu les méthodes publiques de sa classe mère ``animal`` et a même recréée la fonction ``afficherEtat()``.
Dès sa construction, ``Chien`` va mettre la variable ``nourriture`` à 15 (``nourriture`` étant protégé, les classes filles peuvent y avoir accès).
On peut redéfinir une fonction de la classe mère dans une classe fille. Lorsque la classe fille appellera la fonction recréée, ce sera **sa définition** qui sera pris en compte.

# Le destructeur dans tout ça ? 

On a vu l'utilité du constructeur, mais pas du destructeur.
Pour créer des objets, on peut utiliser l'allocation dynamique avec ``new`` et ``delete``, cependant le plus gros défaut est le risque d'une fuite de mémoire si ce n'est pas bien controlé.
Cependant, le C++ moderne (version C++11 et ultérieur) utilise le principe d'*acquisition de ressources est initialisée*.
Ce principe garantit que les ressources allouées dynamiquements soient toujours libérées de manière fiable.

Le principe de destructeur est de libérer les ressources prise par l'objet lorsqu'il est détruit, pour libérer la mémoire.

Son utilisation est quelque chose d'assez complexe à faire comprendre pour ma part, on ne va pas s'attarder dessus pour l'instant.
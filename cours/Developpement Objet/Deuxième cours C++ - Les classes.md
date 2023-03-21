Après avoir eu une brève [[Premier cours C++ - Introduction|introduction]], on va attaquer dans le vif du C++ : ses #classes.

Comme on a vu, les classes peuvent avoir des parties ``public``, ``private`` et ``protected`` comme en Java.

Petit rappel sur ce que ça change ;
- ``public`` : méthode et attribut disponible partout
- ``private`` : méthode et attribut disponible uniquement dans la classe
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
Objet::Objet(){
	a = 15;
	b = 10;
}

Objet::~Objet(){}

void Objet::test(){

}
```

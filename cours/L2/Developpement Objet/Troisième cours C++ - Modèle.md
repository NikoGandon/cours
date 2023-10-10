---
quickshare-date: 06-10-2023 16:04:51
quickshare-url: "https://noteshare.space/note/clneohfkb1597301mwk3gi64th#4rfDjIlQBVhOp0AeHgT3IR1IJ0Do40pnmHGTba5jBKs"
---
Le langage C++ est un langage multi-paradigme, il a plusieurs philosophie d'écriture :
- Objet
- Procédurale
- Générique
On va parler du générique.

L'idée, pour simplifier, est de créer une fonction "générique", en gros disponible pour plusieurs types.

Par exemple, on va créer une fonction ``int addition(int a, int b)`` qui additionnera 2 entiers 
```cpp
int addition(int a, int b){
	return a + b;
}
```

Et ça marche bien, mais si on décide de vouloir additionner maintenant deux nombres flottants, il faudra recréer une autre fonction, ce qui donnera 
```cpp
int addition(int a, int b){
	return a + b;
}

float addition(float a, float b){
	return a + b; 
}
```

Maintenant, si on veut aussi additionner deux ``double``, faudra encore recréer une autre fonction similaire, la seule différence : le type des variables d'entrées et le type de retour.

On peut régler ce problème en utilisant ``template`` (un modèle) qui indique que la fonction sera générique.

On devra aussi indiquer à côté de template, entre chevrons, ce qui sera générique.
Par exemple, pour les types, nous utiliserons ``typename T``, pour la taille ``size_t S``.
``T`` peut être aussi ``U, A, D, ...``.
Pour revenir à la fonction ``addition()`` en utilisant les modèles, on écrit :
```cpp
template<typename T> T addition(T a, T b){
	return a + b;
}
```

**Remarque** : ``T`` est un type, il faut veiller que le retour de la fonction et que les paramètres **soient du même type que ``T``**.

On écrit une fonction ``main()`` pour tester la fonction :
```cpp
int main() {
	int a = 5, b = 10;
	float c = 2.55, d = 1.25;
	double e = 10.225, f = 236.112;

	std::cout << addition(a, b) << "\n"
		<< addition(c, d) << "\n"
		<< addition(e, f) << "\n"
		<< addition(a, e) //Celui-là ne marchera pas : deux types différents
}
```

Ce qui nous donnera (en enlevant l'erreur)
```cpp
15
3.8
246.337
```

Imaginons que nous avons une fonction générique, mais qui peut prendre au maximum deux  type de valeurs différents, on peut facilement le faire : il suffit d'ajouter un autre type de variable.
```cpp
template<typename T, typename U> void test(T a, U b){
	...
}
```
Ici, la variable ``a`` et ``b`` peuvent être de deux types différents, comme du même type.
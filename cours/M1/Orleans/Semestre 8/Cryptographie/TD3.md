# Exercice 1

1. Dessiner le schéma de calcul du code CBC-MAC d’un message M = M1 · · ·Mn avec une clé K et une fonction de chiffrement F : ![[Drawing 2025-03-06 14.39.49.excalidraw|350]]
2. L’utilisation d’un IV fixe est fondamental. Montrer que si l’IV est variable et communiqué avec le message chiffré alors un adversaire peut forger des codes CBC-MAC valides.

   >[!error] Je ne sais pas où je dois mettre ça
   
   
   - $T:\text{MAC du message}$
   - $M,T$
   - $\text{IV}', M', T$
   - $\text{IV}'=\text{IV} \oplus \Delta$
   - $M'=M_{1} \oplus \Delta, M_{2}, \dots, M_{n}$
   - $\text{IV}_{2}, (M_{1} \oplus \text{IV}_{1} \oplus \text{IV}_{2}, M_{2},\dots,M_{n}), T$
   - $\text{IV}_{2}, M', T$
   - $M=M_{1},\dots,M_{n}$
   - $M'=M'_{1},\dots,M'_{n}$
   - $M_{1},\dots,M_{n}, T_{1}$
   - $M'_{1},\dots,M'_{n}, T_{2}$
   - $M''=M''_{1},\dots,M''_{n+m})~~ T_{1}$


3. Lors du chiffrement de messages en mode CBC, l’utilisation d’IV non prédictibles est fondamental. Expliquer cette apparente contradiction avec la question précédente.
   
   
   
4. On dit de CBC-MAC qu’il n’est pas sûr pour le contrôle d’intégrité des messages de taille variable. Expliquer comment forger un code CBC-MAC valide pour un nouveau message à partir de deux messages accompagnés de leurs codes CBC-MAC.

5. Pétronille propose d’utiliser l’algorithme suivant pour transmettre de manière confidentielle, avec contrôle d’intégrité, un message M avec une clé secrète K. Un adversaire peut-il forger des messages recevables par le destinataire ?
   
```
def envoyer(M,K): 
	iv = Choisir un IV aléatoire 
	C = Chiffrer M avec AES-256 en mode CBC avec clé K et IV iv 
	I = Calculer le CBC-MAC AES-256 de M avec clé K 
	send(iv,C,I)
	
def recevoir(K): 
	R = receive() 
	(iv,C,I) = R 
	M = Déchiffrer C avec AES-256 en mode CBC avec clé K et IV iv 
	J = Calculer le CBC-MAC AES-256 de M avec clé K 
	si I == J alors 
		retourner M 
	sinon 
		lever une exception 
```

# Exercice 2

1. Écrire la formule de calcul du code HMAC d'un message $M$ avec une clé $K$ et une fonction de hachage $H$.
   
2. Térence propose d'utiliser l'algorithme suivant pour effectuer le contrôle d'intégrité. Qu'en pensez-vous ? Quelle différence avec $\text{HMAC-MD5}$. 
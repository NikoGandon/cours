# Exercice 1

1. On cherche à calculer $P(S=i) \text{ et } P(B=i) ~ ~\forall i \in [1,665]$

$S=i \Leftrightarrow \text{la porte }i \text{ mène au paradis } (\rightarrow \text{TD})$
$B=i \Leftrightarrow \text{Belzebuth choisit la porte } i$
$P(S=i)=\frac{1}{666} ~ ~ \forall i \in [1,666]$
$P(B=i)=\frac{1}{665} ~ ~ \forall i \in [1,665]$

2. On cherche à calculer $P(B=i|S=i) ~ ~\forall i \in [1,665]$ 

$P(B=i|S=i) \Leftrightarrow \text{Belzebuth prends la porte } i \text{ sachant que cette porte } \to \text{ TD}$
$P(B=i|S=i)=1$

3. On cherche à déduire $P(S=i|B=i) ~ ~\forall i \in [1,665]$

>[!info] Rappel
$P(A / B)=\frac{P(A \cap B)}{P(B)}$

$$P(B=i/S=i)=\frac{P(B=i\cap S=i)}{P(S=i)}$$
$$P(S=i / B=i)=\frac{P(S=i\cap B=i)}{P(B=i)}=\frac{P(B=i|S=i)\times P(S=i)}{P(B=i)}=\frac{1\times\frac{1}{666}}{\frac{1}{665}}=\frac{665}{666}$$


4. On prendra l'autre porte pour augmenter les probabilités.

# Exercice 2

1. 
$\mathcal{M}=\{ 0,1 \}^n$
$\text{Gen}=k \in \{  0,1 \}^n \text{ mais tel que } | k_{|1} | > \frac{n}{4}$

$m=1111 1111, m'=0000 0000, c=0001 0000, k=1110 1111, k'=0001 0000$

2. Non, car ce n'est pas indistinguable
3. ?
# Exercice 3

>[!error] Pas de correction sur le tableau

1. Un algorithme de chiffrement par flot est un schéma dans lequel, à partir d’une clé initiale, on génère une séquence (ou un flot) de bits que l’on XOR avec le message pour obtenir le ciphertext. Dans ce cas, l’algorithme s’appuie sur un état interne de taille fixe. 
2. 
![[Drawing 2025-02-06 15.00.18.excalidraw]]
??

3. ??

# Exercice 4

4. 
```
RC4 init(k):
	for i = 0 to 7:
		S[i]=i
	
	n = longeur(k)
	j = 0
	
	for i = 0 to 7:
		j = (j + S[i] + K[i % n]) % 8
		echanger(S[i], S[j])
	
	i = 0
	j = 0
	
	return (S, i, j)		
```


5. 
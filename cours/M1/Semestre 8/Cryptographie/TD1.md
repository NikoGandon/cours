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


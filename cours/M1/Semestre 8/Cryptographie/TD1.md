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
3. Soit deux messages $m_{0}, m_{1} \in M$ et $c$

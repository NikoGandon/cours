# Exercice 1

Dans cet exercice, les messages sont constitués d'une suite d'entiers codés sur 4 bits et noté en hexadécimal. Chaque caractère est codé en ASCII par deux entiers successifs. Ainsi le mot ``CAKE`` est ``43414B45``. Les tables en annexe permettent d'adapter l'algo Mini AES vu en cours à la notation hexadécimal.

1. Chiffrer le message ``Ok`` avec la clé ``cafe``
	- $\text{O} \to \text{4F}$
	- $\text{k} \to \text{6B}$
	- Donc le message est $\text{4F6B}$

	```mermaid
	flowchart TB
	K --> K0
	K --> K1
	K --> K2
	```

	$$K_{0}=\left(\begin{matrix}
    k_{0} & c & k_{2} \\
    k_{1} & \alpha & k_{3}
    \end{matrix}\right)$$
	$$K_{1} = \left(\begin{matrix}
    k_{4} & k_{6} \\
    k_{5} & k_{7}
    \end{matrix}\right)$$
	$$K_{2}=\left(\begin{matrix}
    k_{8} & k_{10}\\
    k_{9} & k_{11}
    \end{matrix}\right)$$
	$$K_{1}=\left(\begin{matrix}
    k_{4}=\upvarphi(k_{5}\oplus k_{?}\oplus 1) & k_{6}=k_{2}\oplus k_{5} \\
    k_{5}=k_{1} \oplus k_{4} & k_{7}=k_{3}\oplus k_{6}
    \end{matrix}\right)=\left(\begin{matrix}
    o \oplus c \oplus 1 = \alpha & f \oplus 7 = 8 \\
    a \oplus d = 7 & e \oplus 8 = 6
    \end{matrix}\right) = \left(\begin{matrix}
    \alpha & 8 \\
    7  &  6
    \end{matrix}\right)$$
	$$K_{2}=\left(\begin{matrix}
    k_{8}=\upvarphi(k_{2}) \oplus k_{4} \oplus 2 & k_{10}=k_{6} \oplus k_{?} \\
    k_{?}=k_{5} \oplus k_{8} & k_{11}=k_{7}\oplus k_{10}
    \end{matrix}\right)=\left(\begin{matrix}
    b \oplus d \oplus 2=4 & 8 \oplus 3 = b \\
    7 \oplus 4 = 3 & 6 \oplus b = d
    \end{matrix}\right)=\left(\begin{matrix}
    4 & b \\
    3 & d
    \end{matrix}\right)$$
    $$\text{M}=\text{Ok}=\text{4F6B}=\left(\begin{matrix}
    4 & 6 \\
    f & b
    \end{matrix}\right)$$
2. Déchiffrer le message $\text{3140}$ avec la clé $\text{1664}$
	$$K_{0}=\left(\begin{matrix}
    c & f \\
    a & ??
    \end{matrix}\right)$$    $$K_{1}=\left(\begin{matrix}
    1 & 8 \\
    7 & 6
    \end{matrix}\right)$$
    $$K_{2}=\left(\begin{matrix}
    4 & b \\
    3 & ??
    \end{matrix}\right)$$
	$$C_{1}=M\oplus K_{0}= \left(\begin{matrix}
    4 & 6 \\
    f & b
    \end{matrix}\right) \oplus \left(\begin{matrix}
    c & f \\
    a & e
    \end{matrix}\right)=\left(\begin{matrix}
    4 \oplus c & 6 \oplus f \\
    f \oplus a & b \oplus e
    \end{matrix}\right)=\left(\begin{matrix}
    8 & 9 \\
    5 & 5
    \end{matrix}\right)$$
    $$C_{2}=\upvarphi(C_{1})=\left(\begin{matrix}
    \upvarphi(8) & \upvarphi(9) \\
    \upvarphi(5) & \upvarphi(5)
    \end{matrix}\right)=\left(\begin{matrix}
    3 & a \\
    f & f
    \end{matrix}\right)$$
	$$C_{3}=\text{Skyflow}(C_{2})=\left(\begin{matrix}
    3 & a  \\
    f & f
    \end{matrix}\right)$$
	$$C_{4}=\left(\begin{matrix}
    3 & 2 \\
    2 & 3 
    \end{matrix}\right)=\left(\begin{matrix}
    3 \upvarphi 3 \oplus 2 \oplus f & 3 \oplus a \oplus 2 \oplus f \\
    2 \oplus 3 \oplus 3 \oplus f & 2 \oplus \alpha \oplus 3 \oplus f
    \end{matrix}\right) = \left(\begin{matrix}
    5 \oplus d & d \oplus d \\
    6 \oplus 2 & 7 \oplus 8
    \end{matrix}\right)=\left(\begin{matrix}
    8 & 0 \\
    4 & 5
    \end{matrix}\right)$$
    $$C_{5}=\left(\begin{matrix}
    5 & 8 \\
    3 & 3
    \end{matrix}\right)$$
	$$C_{6}=\left(\begin{matrix}
    f & 3 \\
    1 & 1
    \end{matrix}\right)$$
    $$C_{7}=\left(\begin{matrix}
    f & 3 \\
    1 & 1
    \end{matrix}\right)$$
    $$C_{8}=\left(\begin{matrix}
    b & 8 \\
    2 & c
    \end{matrix}\right)$$
    $$K_{0}= \left(\begin{matrix}
    1 & 6 \\
    6 & 4
    \end{matrix}\right) ~~~~~~~~ K_{1}=\left(\begin{matrix}
    2 & 2 \\
    4 & 6 
    \end{matrix}\right) ~~~~~~~~ K_{2}=\left(\begin{matrix}
    b & d \\
    f & b
    \end{matrix}\right) ~~~~~~~~ M=\left(\begin{matrix}
    7 & 6 \\
    9 & f
    \end{matrix}\right) = y_{0}$$

| $M_{1}$ | "B," |
| :-----: | :--: |
| $M_{2}$ | " A" |
| $M_{3}$ | ", " |
| $M_{4}$ | "BA" |
| $M_{5}$ | ", " |
| $M_{6}$ | "Co" |
| $M_{7}$ | "mp" |
| $M_{8}$ | "ri" |
| $M_{9}$ | "s." |
Donc BA,BA, compris
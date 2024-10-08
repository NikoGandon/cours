# Exercice 1

Soit $A = \{0,1\}$
1.  $\{(0,0),(1,0), (0,1),(1,1)\}$, 
2. Les fonctions de $A$ dans $A$ :
	1. $f_1=\{(0, 0), (1,1)\}$  totale
	2. $f_1=\{(0,1), (1,0)\}$  totale
	3. $f_1=\{(0, 0)\}$
	4. $f_1=\{(0, 1)\}$
	5. $f_1=\{(1,0)\}$
	6. $f_1=\{(1,1)\}$

# Exercice 2

Soit $A=\{0,1\}$ et $E = \{a,b,c\}$
1. $\mathcal{P}(E)=8$
   $\emptyset,\{a\},\{b\},\{c\},\{a,b\},\{a,c\},\{b,c\}, \{a,b,c\}$
2. Un élément de l'ensemble $\mathbb{N}^2\times A^{*} \times \mathcal{P}(E)$ peut être $(((2,17),100),\{b,c\})$
# Exercice 3

1. $\mathcal{R}=\{(x,y) \in \mathbb{R}^2 ~ | ~ |y| + x = 0\}$, relation non déterministe
2.  $\mathcal{R}=\{(x,y) \in \mathbb{R}^2 ~ | ~ xy = 1\}$, relation déterministe, fonction partielle non définie en $0$
3.  $\mathcal{R}=\{(x,y) \in \mathbb{R}^2 ~ | ~ y - x + 2= 0\}$, relation déterministe, fonction totale

# Exercice 4

1. .
	1. $a,b \in L_{p}$
	2. $v \in L_{p}$ alors $ava \in L_p$ et $bvb \in L_p$
2. Soit $\mathcal{G}=(\{0, \dots, 9\}, \{F,D,N\}, F, R)$ où 
$$\begin{matrix}
D \to 0  & N \to N ~ D\\
\vdots & N \to D\\
\vdots & F \to N.N \\
D \to 9 & F \to N
\end{matrix}$$
$F \implies N.N \implies ND.N \implies NDD.N \implies DDD.N \implies 2DD.N \implies 22D.N$
$\implies 225.N \implies 225.ND \implies 225.DD \implies 225.3D \implies 225.32$

# Exercice 5

- Soient $L, R$ deux programmes dans $P''$
- Si $p_{1}$ et $p_2$ sont des programmes, $p_{1}p_{2}$ est un programme
- Si $p$ est un programme, alors $(p)$ est un programme
- Seuls les programmes dérivables à partir de ces règles sont des programmes
>[!error] 
>Le 1. n'est pas complet
1. La syntaxe de $P''$ comme système d'inférence :
	1. $\dfrac{p_{1} \in P^* ~~ p_{2 \in P''}}{p_{1}p_{2} in P^*}$
	2. $\dfrac{p \in P''}{(p) \in P''}$
	3. $\dfrac{}{R \in P''}$
	4.  $\dfrac{}{L \in P''}$
	5. $\dfrac{R \in P'' ~~ L \in P''}{}$
	6. $\dfrac{RL \in P''}{}$
	7. $\dfrac{(RL) \in P'' ~~ L \in P''}{(RL)L \in P''}$

2. La syntaxe de $P''$ par une grammaire non contextuelle :
	1. $P \to L$
	2. $P \to R$
	3. 
3. La syntaxe de $P''$ en utilisant la notation BNF
```
programme :=   "R"
			 | "L"
			 | <programme1> <programme2>
			 | "(" + <programme> + ")"
```

# Exercice 6

Soit $T = \{a,b,c\}$
- le mot $c$ est un bon mot
- si $u$ est un bon mot, alors $au$ est un bon mot
- si $u$ est un bon mot, alors $ub$ est un bon mot
1. ``REGEX BLABLABLA``.
2. .
3. Le mot $aacb$ est un bon mot car XX 

# Exercice 7

1. Soit $S(3)$ et $S(5)$, soit $\forall x, y, S(x) \land S(y)\implies S(x+y)$
   Donc $(S(3) \land S(3)) \land S(5) = S(11)$
2. 
	1. $S(1)$ par $(S(5) \land S(5)) \land (S(3) \land S(3) \land S(3)) \implies S(10) \land S(9) \Leftrightarrow S(10-9) = S(1)$
	2. $S(-1)$ par $(S(3) \land S(3)) \land S(5) \implies S(6) \land S(5) \Leftrightarrow S(6-5) = S(-1)$ 
# Exercice 8

Un robot se déplace soit 6 pas devant soit 4 pas en arrière, soit $x \in \mathbb{Z}$ sa position, initialement à $0$.

1. 

|         inférence         | action               |
| :-----------------------: | :------------------- |
| $\frac{}{\text{pos}(0)}$  | axiome de départ     |
| $\frac{pos(x)}{pos(x+6)}$ | mouvement en avant   |
| $\frac{pos(x)}{pos(x-4)}$ | mouvement en arrière |
2. 
      $pos(0) \to \frac{pos(0)}{pos(6)} \text{ avancer}\to \frac{pos(6)}{pos(12)} \text{ avancer} \to \frac{pos(12)}{pos(8)} \text{ reculer}\to \frac{pos(8)}{pos(4)} \text{ reculer}$
3. Soit $\text{pos}$ auquel on peut donner ce principe d'induction : 
   - __base__ : $pos(0)$
   - __induction__ : si $\text{pos}(x)$ où $x \in \mathbb{Z}$ est vrai, alors $\text{pos}(x+6)$ et $\text{pos}(x-4)$ sont vrais
4. Pour prouver ce principe de parité, nous pouvons poser une hypothèse se basant sur la récurrence : 
   __Initialisation__ : Soit $x \in \mathbb{Z}$, $0 \overset{*}{\implies} x$, alors $x$ est pair
	1. Le robot avance
	   $0 \overset{*}{\implies} x \implies x+6$
	   par hypothèse, $x=2 \times k \implies x+6 = 2 \times k + 2 \times 3 = 2 (k + 3) \implies x + 6 \text{ est pair}$
	2. Le rebot recule
	   $0 \overset{*}{\implies} x \implies x -$ 
	   par hypothèse, $x=2 \times k \implies x-4 = 2 \times k - 2 \times 2 = 2 (k - 2) \implies x - 4 \text{ est pair}$
5. Si $\text{pos}(x)$ est vrai, alors :
	- $\text{pos}(x+2)$ est vrai, car nous pouvons faire $\text{pos}(6-4)$ (avancer et reculer)
	- $\text{pos}(x-2)$ est vrai car nous pouvons faire $\text{pos}(-4-4+6)$ (reculer, reculer et avancer)

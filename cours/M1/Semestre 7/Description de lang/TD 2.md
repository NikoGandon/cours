# Exercice 1

Soit la grammaire $\text{Exercice}_{1}$ suivante : $NT = \{L, A, B\}$ et $T = \{s, t, u, v\}$
__Attribues synthétisés__ :
- $z$, avec $L,A$
- $x, y$ avec $B$
__Attribues hérités__ :
- $c$ avec $A$
- $a, b$ avec $B$

|     .      | .                                     |
| :--------: | ------------------------------------- |
| $L \to A$  | $\{L.z = A.z, A.c = 0\}$              |
| $A \to sB$ | $\{B.a = B.y, B.b = A.c, A.z = B.x\}$ |
| $A \to tB$ | $\{B.a = A.c, B.b = B.x, A.z = B.y\}$ |
| $B \to u$  | $\{B.x = B.a, B.y = B.b\}$            |
| $B \to v$  | $\{B.x = B.a, B.y = 0\}$              |

1. 
```mermaid
flowchart TB
z0(z)
z1(z)
L --> A
z0 --> z1
```

```mermaid
flowchart BT
x --> z
```

```mermaid
flowchart TB
A --> s & B
c --> b
x --> z
y --> a
```

```mermaid
flowchart TB
A --> t
A --> B
x --> b
c --> a
y --> x
```

```mermaid
flowchart TB
a --> x
b --> y
B --> u
```

```mermaid
flowchart TB
a --> x
B --> v
b
y
```
2. ![[Drawing 2024-09-20 11.36.08.excalidraw||1500px]]
3. $A.c=0$
   $B.b = A.c = 0$
   $B.a = B.y$
   $B.x = B.a$

# Exercice 2

$$N \to BIN.BIN'$$
$$BIN \to BIN ~ BIT \{BIN_{0}~v = 2 \times BIN_{1}~v+BIT.v\}$$
$$BIN \to \epsilon \{BIN.v=0\}$$$$BIN'\to BIT ~ BIN' ~~~ \{BIN'_{0}~v=\frac{BIT.v+BIN'_{1}.v}{2}\}$$
$$BIN'\to BIT~~\{BIT.v=0\}$$
$$BIT \to 0 ~~ \{BIT.v=0\}$$$$BIT \to 1 ~~ \{BIT.v=1\}$$
$v$ : attribut synthétisé, associé à $N, BIN, BIN', BIT$
$v \in \mathbb{R}$

```mermaid
flowchart TB
BIN5(BIN 5)
BIN1(BIN 1)
BIN2(BIN 2)
BIT1a(BIT 1)
BIT0(BIT 0)
BIT1b(BIT 1)
BIT0c(BIT 0)
1a{1}
1b{1}
1c{1}
0a{0}
0b{0}
0c{0}
BIN0(BIN 0)
BIT1c(BIT 1)

N --> BIN5
N --> BIN'
BIN5 --> BIN2
BIN5 --> BIT1a
BIT1a --> 1a
BIN2 --> BIN1
BIN2 --> BIT0
BIT0 --> 0a
BIN1 --> BIN0
BIN1 --> BIT1b
BIN0 --> 0b
BIT1b --> 1b

BIN' --> BIT0c
BIT0c --> 0c
BIN' --> BIN'1
BIN'1 -->BIT1c
BIT1c --> 1c
```

# Exercice 3 

Soit la grammaire suivante : 

$$
\begin{cases}
S \to E \\
E \to E := E ~ | ~ E+E ~ | ~ (E) ~ | ~ id
\end{cases}
$$

Vrai :
```mermaid 
flowchart TB
Er(E)
Er1(E)
AFF1(:=)
PARG("(")
E2(E)
PARD(")")
E0(E)
ADD1(+)
E1(E)
E3(E)
AFF2(:=)
E4(E)

Er --> Er1
Er1 --> a
Er --> AFF1
Er --> E0


E0 --> E1
E0 --> ADD1
E0 --> E
E1 --> PARG
E1 --> E2
E1 --> PARD
E2 --> E3
E2 --> AFF2
E2 --> E4
E3 --> c
E4 --> d
```
Faux :

```mermaid
flowchart TB
Er(E)
E0a(E)
AFF(:=)
E0b(E)

PARD("(")
E1a(E)
PARG(")")

E2a(E)
E2b(E)
ADD(+)

Er --> E0a
Er --> AFF
Er --> E0b

E0a --> PARG
E0a --> E1a
E0a --> PARD
E1a --> E2a
E1a --> ADD
E1a --> E2b
E2a --> a
E2b --> b

E0b --> c
```


>[!info]
>côté: attribut hérité $\in \{gauche, droite, \bot\}$ associé à $E$
>bf : attribut synthétisé $\in \{true, false\}$  associé à $S,E$


$$S \to
\{cote(E)= \bot \} ~~ E$$
$$E \to \{ cote(E_{1}) = cote(E), cote(E_{2}) = cote(E) \}$$
$$E_{1} + E_{2}$$
$$\begin{cases}
\text{Si } cote(E) = \text{ gauche alors} \\
bf(E)= \text{ false} \\
\text{Sinon } bf(E) = bf(E_{1}) ~ \& ~ bf(E_{2})
\end{cases}$$
$$E \to \{cote(E_{1}) = \text{ gauche}, cote(E_{2}) = \text{ droite}\}$$
$$E_{1} := E_{2} \{bf(E) = bf(E_{1}) ~\& ~ bf(E_{1}) \}$$
$$E \to \{cote(E_{1}), cote(E)\}(E_{1})\{E ~ bf = (E \text{ cote } \neq \text{gauche}) \}$$
$$E \to id ~ \{E.bf= tau\}$$


# Exercice 4

1. 
```mermaid
flowchart TB
ADD1(+)
ADD2(+)
MUL1(*)
MUL2(*)

Er(E)
E0(E)
E1(E)
F4(F)
E5(E)
E6(E)
E8(E)
T0(T)
T2(T)
T3(T)
T6(T)
T7(T)

F1(F)
F3(F)
F7(F)
E4b(E)
F6b(F)
T5b(T)
T6b(T)
T7b(T)

PG("(")
PG1("(")
PG4b("(")
PD(")")
PD1(")")
PD4b(")")

Er --> E0
Er --> ADD1
Er --> T0
E0 --> PG
E0 --> E1
E0 --> PD
E1 --> T2
T2 --> T3
T2 --> MUL1
T2 --> F3
T3 --> F4
F4 --> PG1
F4 --> E5
F4 --> PD1
E5 --> E6
E5 --> ADD2
E5 --> T6
E6 --> T7
T7 --> E8
E8 --> 1
T6 --> F7
F7 --> 2

F3 --> PG4b
F3 --> E4b
F3 --> PD4b
E4b --> T5b
T5b --> T6b
T5b --> MUL2
T6b --> T7b
T7b --> 3
T5b --> F6b
F6b --> 4

T0 --> F1
F1 --> 5
```



2. Soit le texte $(((1+2) * (3 * 4)) + 5)$
   $(((1+2)*(3*4)) + 5) \to (1+2)* ~~~~ 3 * 4 ~~~~ +5$
   $E \to E_{1}+T$
   $\{E.poids=1, E.\exp = E_{1}.\exp \land '+' \land T.\exp\}$
$E\to E_{1}-T$
$\{ E.poids = 1, \text{ si } T.poids=1 \text{ alors } E_{1}.\exp \land '-' \land '(' \land T.\exp ')'$
$\text{sinon } E.\exp = E_{1}.\exp \land '-' \land T.\exp \}$

$E\to T \{ E.poids = T.poids ; E.\exp = T.\exp \}$
$T \to T_{1} \times F \{ T.poids = 2,$
$T.\exp = \text{ si } T_{1}.poids=1 \text{ alors } '(' \land T_{1}.\exp \land ')' \text{ sinon } T_{1}.\exp f \text{ FIN DU si }$ 
$\land '*'$
$\land \text{ si } F.poids = 1 \text{ alors } '(' \land F.\exp \land ')' \text{ sinon } F.\exp \text{ FIN DU si}$

# Exemple 15

Le langage $L_{eq}=\{a^ib^i|i>0\}$ n'est pas régulier
1) Supposons par l'absurde que $L$ est régulier
2) Soit $n$ la constante d'itération, on choisit le mot $w=a^nb^n$
3) Par le lemme, il existe un mot $w=xyz$ vérifiant les conditions du lemme $| xy |\leq n$, en utilisant la variante énoncée, $x$ et $y$ sont composés uniquement de lettre $a$
4) Posons $k=|y|$, on a $k>0$, alors $xy^mz=a^{n+(m-1)k}b^n$ pour tout entier $m\geq 0$
5) La structure des mots $a^ib^i$ impose $n+(m-1)k=n$ pour tout entier $m\geq 0$, donc $k=|y|=0$ ce qui est en contradiction avec l'hypothèse
6) Donc $L$ n'est pas régulier
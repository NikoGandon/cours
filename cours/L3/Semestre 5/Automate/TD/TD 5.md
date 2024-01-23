# Exercice 1

1. $B$ est inutile car il ne produit que des variables et ne peux pas générer de mot terminal
2.   $S \to CA$
    $A \to a$
    $C \to b$
# Exercice 3

3.    $S \to 0A0 \ | \ 1B1 \ | \ BB$
     $B \to 0A0 \ |\ 1B1 \ | \ BB \ | \ BC$
     $A \to BC \ \ | \ 0A0 \ | \ 1B1 \ |\ BB$
     $C \to 0A0 \ | \ 1B1 \ |\ BB$

# Exercice 4

1. .
2. .
3.   $S \to AAA \ | \ b \ | \ bBB \ | \ bB \ | \ AA \ | \ a \ | \ ab$
    $A \to a \ | \ aA \ | \ b \ | \ bBB \ | \ bB$
    $B \to b \ | \ bBB \ | \ bB$

# Exemple tableau

(a+b)*  a  (a + b)* (c + d)*

$S \to B A B C$
$A \to a$
$B \to \epsilon | a | b | BB$
$C \to \epsilon | c | d | CC$

$S \to BABC | BAB | BAC | ABC | AB | BA | AC | A$
$A \to a$

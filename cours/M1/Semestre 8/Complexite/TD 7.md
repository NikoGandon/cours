>[!info] La classe P
>Cette classe contient tous les problèmes de décision que l'on peut résoudre en temps polynomial sur une machine de Turing déterministe. On a $P=\cup_{c>1}\text{DTIME}(n^c)$

# Exercice 1

Montrez que la classe $P$ est close par l'union et par intersection. Qu'en est-il pour la complémentation ?

**P close par l'union**:

Soit $L_{1}\text{ et }L_{2}$ deux langages de $P$ reconnus par les machines déterministes $M_1$ et $M_2$ respectivement en temps $p_1(m)$ et $p_2(m)$ tels que $p_{1}(n),p_{2}(n) \in n$ ($n$ un certains polynôme).

Pour reconnaitre $L_{1} \cup L_{2}$, on simule l'exécution de ces deux machines. Si l'une d'elle accepte, alors le mot est accepté. Le temps d'exécution est $\mathcal{O}(p_{1}(n)+p_{2}(n))$ qui est bien polynômial.

**P close par l'intersection**

Pour reconnaître $\overline{L_{1}}$, le langage complémentaire de $L_{1}$, on exécute $M_{1}$ sur le mot.
- Si $M_{1}$ rejette --> on accepte
- Si $M_1$ accepte --> on rejette
Le temps d'exécution est celui de $M_{1}$


P est donc close par $\cap,\cup,\text{complémentaire}$
# Exercice 2

Soit une machine de Turing déterministe $M$ reconnaissant un langage $A$ en temps $2^{\mathcal{O}(n)}$. Notons $A'$ le langage $\{ <x,O^{2^{|x|}}> \}$ où $O$ est un symbole n'appartenant pas à l'alphabet des mots de $A$. Montrez que $A'$ appartient à $P$.

>[!info] Par exemple
>si $x=1122$ est un mot de $A$
>si $x=11220000000000000000$ est un mot de $A'$

Puisque $M$ est une machine de Turing déterministe qui reconnaît $A$ en temps $2^{\mathcal{O}(n)}$, cela signifie qu'il existe $k$ tel que $M$ reconnaît en temps $2^{k\times n}$
On peut construire une MTD $M'$ qui reconnaît $A'$ de la façon suivante : 
Elle vérifie que sur un mot $<x,O^m>$:
- Il y a précisément $2^{|x|}$ symbole $O$ à la fin du mot $<x,O^n>$
- Si c'est le cas, elle vérifie que $x$ est bien un mot de $A$. Pour cela, elle simule la machine $M$ sur le mot $x$. Pour cela, elle simule la machine $M$ sur le mot $x$.

Le temps d'exécution de $M'$ est $\mathcal{O}(2^{|x|}+2^{k\times |x|})$

Or la taille $n$ de l'entrée (c'est-à-dire du mot $<x,O^n>$ doit décider l'appartenance à $A'$ est $n=|<x,O^m>| \approx 2^{|x|}$
Donc  $\mathcal{O}(2^{|x|})+2^{|x|^{k}}=\mathcal{O}(n^k)$

___

>[!info] La classe NP
>Cette classe contient tous les problèmes de décision que l'on peut résoudre en temps polynômial sur une machine de Turing non déterministe. On a $\text{NP}=\cup_{c>1}\text{NTIME}(n^c)$

# Exercice 3

## Partie 1
Montrez que la classe NP est close par union et par intersection

**NP close par union** :

Pour reconnaitre $L_{1}\text{ et }L_{2}$ on simule $M_1$ (la machine non déterministe qui reconnaît $L_1$) et si $M_{1}$ arrive dans un état acceptant, alors on accepte le mot; sinon on simule $M_{2}$ (la MTND qui reconnaît $L_2$) et si $M_2$ accepte, alors le mot est accepté

Le temps en exécution est $\mathcal{O}(p_{1}(n)+p_{2}(n))$
Donc polynômial sur une MTND

**NP close par intersection** :

Pour reconnaître $L_{1} \cap L_{2}$, on construit une MTND $M$ qui étant donné un mot $w$ :
- exécute $M_{1}$ sur $w$
- exécute $M_{2}$ sur $w$
- accepte si et seulement si les deux machines $M_1$ et $M_2$ 

Le temps d'exécution est poly

## Partie 2
Montrez que $\text{P} \subseteq \text{NP}$  :

Soit $X \in P$. Donc il existe un algo $A$ qui





# Exercice 4

- $\text{NP}$ est la classe des langages qui admettent un certificateur polynomial
- Un certificateur pour un langage $A$ est un algorithme $V$ où
	- $A=\{ w \text{ tel que } V \text{ accepte } <w,c> \text{ pour un certifiant } x \}$
- 
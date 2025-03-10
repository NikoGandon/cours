# Exercice 1

Soit la BDD $D$ défini par $I=\{ A,B,C,D \}$ et $T=\{ t_{1},t_{2},t_{3},t_{4},t_{5},t_{6},t_{7},t_{8} \}$ avec :

|   -   | A   | B   | C   | D   |
| :---: | --- | --- | --- | --- |
| $t_1$ | X   | X   | X   | X   |
| $t_2$ | X   | X   | X   | X   |
| $t_3$ | X   | X   | X   | X   |
| $t_4$ | X   |     | X   |     |
| $t_5$ |     | X   | X   |     |
| $t_6$ |     |     | X   |     |
| $t_7$ | X   |     | X   | X   |
| $t_8$ | X   | X   |     | X   |

1. Soit $\text{Min\_Sup\_Abs}=4~~~~(\text{Min\_Sup}=50\%)$, en utilisant l'algorithme `APriori` les itemsets fréquentes.
   
   En utilisant l'algorithme `APriori`: 
   
| Règle 1 | Occurence | Règle 2 | Occurence | Règle 3        | Occurence |
| :-----: | --------- | ------- | --------- | -------------- | --------- |
|    A    | 6         | AB      | 4         | ABD            | 4         |
|    B    | 5         | AC      | 5         | ACD            | 4         |
|    C    | 7         | AD      | 5         | $\cancel{ABC}$ | 2         |
|    D    | 5         | BC      | 4         | $\cancel{BCD}$ | 3         |
|         |           | BD      | 4         |                |           |
|         |           | CD      | 4         |                |           |


2. En supposant $\text{Min\_Conf}=80\%$, donnez les règles d'associations solides
   
   
|            $A$            | Confiance     | $AB$                        | Confiance     | $ABD$                       | Confiance     |
| :-----------------------: | ------------- | --------------------------- | ------------- | --------------------------- | ------------- |
| $\cancel{\emptyset\to A}$ | $\frac{6}{8}$ | $\cancel{\emptyset \to AB}$ | $\frac{4}{8}$ | $\cancel{\emptyset\to ABD}$ | $\frac{4}{8}$ |
|                           |               | $\cancel{A \to B}$          | $\frac{4}{6}$ | $\cancel{A\to BD}$          | $\frac{4}{6}$ |
|                           |               | $B \to A$                   | $\frac{4}{5}$ | $B \to AD$                  | $\frac{4}{5}$ |
|                           |               |                             |               | $D \to AB$                  | $\frac{4}{5}$ |
|                           |               |                             |               | $AB\to D$                   | $\frac{4}{4}$ |
|                           |               |                             |               | $BD \to A$                  | $\frac{4}{5}$ |
|                           |               |                             |               | $AD \to B$                  | $\frac{4}{4}$ |

$\text{conf}(A\to BD) \leq \text{conf}(AB\to D)$

   3. On veut utiliser l'algorithme `Partition` pour rechercher les itemsets fréquents. A ces fins, on partage la BDD en 2 parties égales, l'une contient les 4 premières transactions l'autre contient les transactions restantes. Trouvez à l'aide de `Partition` les itemsets fréquents de la BDD ci dessus
      
>[!info] Rappel
      >Soit $X$ un sous-ensemble de $I$ et $U$ un sous-ensemble de $T$, on définit comme suit les fonctions $i$ et $t$ :
      >$t(X)=\{ tr \in T |X \subseteq tr \}$ et $i(U)=\{ x \in I | \forall tr \in U, x \in tr \}$
      >On définit la fermeture de $X$ par $f(x)=i(t(X))$ et $X$ est dit fermé si et seulement si $i(t(X))=X$. On définit une relation, notée $\simeq$ entre 2 itemsets $X$ et $Y$ : $X \simeq Y$ si et seulement si $f(X)=f(Y)$
      >Si $X$ et $Y$ sont deux itemsets, on note $X \subset Y$ si $X$ est strictement inclus dans $Y$ au sens large
      
Divisons la BDD en ces deux parties : 
- $P_{1}:\{ t_{1},t_{2},t_{3},t_{4} \}$
- $P_{2}:\{ t_{5},t_{6},t_{7},t_{8} \}$

Itemsets présent dans $P_{1}$:

| Itemset | Occurence |
| :-----: | --------- |
|    A    | 4         |
|    B    | 3         |
|    C    | 4         |
|    D    | 3         |
|   AB    | 3         |
|   AC    | 4         |
|   AD    | 3         |
|   BC    | 3         |
|   BD    | 3         |
|   CD    | 3         |
|   ABC   | 3         |
|   ABD   | 3         |
|   ACD   | 3         |
|   BCD   | 3         |
|  ABCD   | 3         |

Itemsets présent dans $P_{2}$:

| Itemset | Occurence |
| :-----: | --------- |
|    A    | 2         |
|    B    | 2         |
|    C    | 3         |
|    D    | 2         |
|   AB    | 1         |
|   AC    | 1         |
|   AD    | 2         |
|   BC    | 1         |
|   BD    | 1         |
|   CD    | 1         |

Donc l'union des itemsets les plus fréquents de $P_{1}$ et $P_{2}$ :
$\{ A, B, C, D, AB, AC, AD, BC, BD, CD, ABC, ABD, ACD, BCD, ABCD \}$


4. Dessiner le treillis des itemsets avec leur support absolu (i.e. le nombre de transactions qui contiennent cet itemset)
   ![[Drawing 2025-03-10 17.10.37.excalidraw|600]]
   
5. Calculez $t(\{ A \}),~t(\{ B \}),~t(\{ AB \}),~t(\{ AC \}),~t(\{ ABC \})$. Que peut-on dire sur le cardinal ?
   
   - $t(A)=\{ t_{1},t_{2},t_{3},t_{4},t_{7},t_{8} \}$
   - $t(B)=\{ t_{1},t_{2},t_{3},t_{5},t_{8} \}$
   - $t(AB)=\{ t_{1},t_{2},t_{3},t_{8} \}$
   - $t(AB)=t(A)\cap t(B)$
   - $i(t(A))=A$, donc $A$ est fermé (il caractérise les transactions)
   
6. Calculez $i(\{ t_{1} \}),~i(\{ t_{1},t_{2} \}),~i(\{ t_{1},t_{4} \}),~i(\{ t_{1},t_{4},t_{6} \}),~$. Que remarque t'on ?
   - $i(\{ t_{1} \}) \leq ABCD$
   - $i(\{ t_{1},t_{4} \}) = AC$
   - $i(t(CD))=ACD$
   - $i(t(ACD))=ACD$

7. On définit la fermeture de $X$ par $f(X)=i(t(X))$. Calculez $f(\{ A \}),~f(\{ AB \}),~f(\{ ABC \})$.
   
8. Montrez que $\simeq$ est une relation d'équivalence
   
   
9. Donnez les classes d'équivalence de la relation $\simeq$
10. On note qu'un itemset $X$ est fermé si et seulement si $X$ est un élément maximal de sa classe d'équivalence. Donnez les itemsets fermés de la base $D$
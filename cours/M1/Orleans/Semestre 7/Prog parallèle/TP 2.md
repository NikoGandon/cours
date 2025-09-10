L'objectif de ce TP est d'implémenter l'algorithme de Cannon pour la multiplication de matrices paralléle.

## 1. Description de l'algorithme de Cannon

L'algorithme de Cannon réalise le produit de deux matrices $C=A\times B$ en supposant qu'on travaille à partir d'une grille 2D régulière de processeurs $p\times p$. Les deux matrices sont de taille $n\times n$ et l'algorithme de Cannon est basé sur un découpage des matrices $A$ et $B$ en blocs $A_{ij}$ (respectivement $B_{ij}$) de taille $\frac{n}{p}\times\frac{n}{p}$ (on supposera que $n$ est divisible par $p$).

Les deux étapes de l'agorithme sont les suivantes

### 1.1 Phase initiale

Les matrices sont réparties sur les processeurs tel que le bloc
  $A_{ij}$ (respectivement $B_{ij}$) soit sur le processeur identifié
  par le couple $(i,j)$ sur la grille de processeurs. La première
  étape consiste à redistribuer la matrice de façon à effectuer un
  décalage circulaire des blocs $A_{ij}$ de $i$ positions à gauche et
  des blocs $B_{ij}$ de $j$ positions vers le haut.

  Par exemple on doit obtenir cette redistribution pour les matrices $A$ et $B$ découpées en $4\times 4$ blocs : 

$$\left(
\begin{array}{llll}
A_{00} &A_{01} &A_{02} &A_{03}\\
A_{10} &A_{11} &A_{12} &A_{13} \\
A_{20} &A_{21} &A_{22} &A_{23}\\
A_{30} &A_{31} &A_{32} &A_{33} \\
\end{array}
\right) \longrightarrow\left(
\begin{array}{llll}
A_{00} &A_{01} &A_{02} &A_{03}\\
A_{11} &A_{12} &A_{13} &A_{10} \\
A_{22} &A_{23} &A_{20} &A_{21}\\
A_{33} &A_{30} &A_{31} &A_{32} \\
\end{array}
\right) $$

$$\left(
\begin{array}{llll}
B_{00} &B_{01} &B_{02} &B_{03}\\
B_{10} &B_{11} &B_{12} &B_{13} \\
B_{20} &B_{21} &B_{22} &B_{23}\\
B_{30} &B_{31} &B_{32} &B_{33} \\
\end{array}
\right)\longrightarrow\left(
\begin{array}{llll}
B_{00} &B_{11} &B_{22} &B_{33}\\
B_{10} &B_{21} &B_{32} &B_{03} \\
B_{20} &B_{31} &B_{02} &B_{13}\\
B_{30} &B_{01} &B_{12} &B_{23} \\
\end{array}
\right)$$ 

A partir de cette répartition des blocs des deux matrices, chaque processeur crée un bloc $C_{ij}$ qui va permettre de calculer la matrice $C$ par la somme successive des produits des 2 blocs des matrices $A$ et $B$ stockées par chaque processeur.

### 1.2 Itérations suivantes

 Chaque processeur identifié par le couple $(i,j)$ sur la grille 2D effectue le produit des deux blocs de $A$ et $B$ qu'il a reçu et les transmet de la manière suivante
  
  - Les blocs de la matrice $A$ sont transmis selon un shift circulaire à gauche dans la grille de processeurs.
  - Les blocs de la matrice $B$ sont transmis selon un shift circulaire vers le haut dans la grille de processeurs.
  
  Au final chaque processeur $(i,j)$  contient le bloc $C_{ij}=\sum_{l=0}^{p-1} A_{il}B_{lj}$.
## 2. Réalisation
### 2.1 Principe général
On va supposer que $n$ est divisible par $p$ avec $p$ tel que le nombre de processus est égal à $p\times p$. Les étapes pour la mise en oeuvre sont les suivantes
- Création d'une topologie 2D des processus (MPI\_Dims\_create et MPI\_Cart\_create) pour être capable d'identifier un processus de rang mpi\_rank par un couple $(i,j)$ dans une grille 2D.

- Initialisation sur chaque processus de deux matrices locales $A_{local}$ et $B_{local}$ de taille $\frac{n}{p}\times \frac{n}{p}$ qui correspondent aux blocs $A_{ij}$ et $B_{ij}$ des matrices $A$ et $B$.
- Redistribution des blocs selon l'étape 1 de l'algorithme. Vous pourrez utiliser MPI\_Cart\_shift pour déterminer le rang des processeurs source et destination d'un bloc.
- Mise en place de la boucle à partir d'une fonction qui calcule $C_{local} = C_{local} + A_{local}\times B_{local}$
### 2.2 Trame initiale
Vous disposez de la trame initiale ci-dessous. Cette version initiale considère des matrices d'entiers non signés. Vous disposez des fonctions
- generation_mat pour construire une matrice de taille donnée en paramètre
- multiplication_elementaire qui effectue une multiplication de matrices classique en séquentiel.

Le programme principal est un squelette à compléter avec votre implémentation.

```cpp
int*  generation_mat(int taille)
{
  int* mat = new int[taille*taille];
  for (int i=0; i<taille*taille; i++)
    mat[i] = rand()%10;
  return mat;
}

// Produit C+=AxB
void multiplication_elementaire(int n, int* A, int* B, int* C)
{
  for (int i=0; i<n; i++) {
    for (int j=0; j<n; j++) {
      int ele = 0; 
      for (int k=0; k<n; k++)
	ele = ele + A[i*n+k]*B[k*n+j];
      C[i*n+j] = C[i*n+j] + ele;      
    }
  }  
}

int main ( int argc , char **argv )
{
  int pid, nprocs;  
  MPI_Init (&argc , &argv) ;
  MPI_Comm_rank(MPI_COMM_WORLD, &pid ) ;
  MPI_Comm_size (MPI_COMM_WORLD, &nprocs ) ;
  MPI_Comm Comm_grille; // Nouveau communicateur pour la topologie cartésienne.

  int n = atoi(argv[1]);
  
  srand(pid);
  int* A_local = generation_mat(n);
  int* B_local = generation_mat(n);
  int* C_local = new int[n*n];
  
  for (int i=0; i<n*n; i++)
    C_local[i] = 0;
  
  // à compléter ....
  
  delete[] A_local;
  delete[] B_local;
  delete[] C_local;
  
  MPI_Finalize() ;
  return 0 ;

```
### 2.3 Vérification 

Afin de vérifier le bon fonctionnement de votre implémentation vous allez 
- implémenter une fonction qui permet de reconstruire sur un unique processus les matrices $A$, $B$ et $C$.
- utiliser la fonction *multiplication_elementaire* sur le processus qui rassemble les 3 matrices pour calculer la multiplication que vous pourrez comparer au résultat précédent.

### 2.4 Distribution initiale 

La dernière étape consiste à travailler sur une matrice complète générée par un processus root ce qui est plus proche de la pratique. Pour cela vous allez
- implémenter une fonction qui permet de distribuer par bloc une matrice carrée de taille $n \times n$ en supposant toujours que $n$ est divisible par $p$ lorsque $nprocs = $\times p$.
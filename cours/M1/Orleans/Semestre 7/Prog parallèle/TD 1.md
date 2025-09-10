# Partie 1 : Architecture MPI

## Exercice 1

### Fonction CommAComprendre

Elle sert à envoyer la moitié droite de son tableau à son voisin de droite et la moitié gauche de son tableau à son voisin de gauche

|                   |       P0       |       P1       |        P2         |        P3         |
| :---------------: | :------------: | :------------: | :---------------: | :---------------: |
| tablocal taille 6 |  1,2,3,4,5,6   | 7,8,9,10,11,12 | 13,14,15,16,17,18 | 19,20,21,22,23,24 |
| tablores taille 6 | 22,23,24,7,8,9 | 4,5,6,13,14,15 | 10,11,12,19,20,21 |  16,17,18,1,2,3   |

### Fonction mystère

$P_{0} \to P_{1}$
$i=1$: $P0 \to P2$, $P_{1} \to P_{3}$
$i=2$ : $P_{0} \to P_{4}$, $P_{1} \to P_{5}$

## Exercice 2

```c
int fn_max(int n, int* tab){
	int max = tab[0];
	for (int i = 0; i < n, i++){
		if (tab[i] > max) max = tab[i];
	}
	return max
}

int calcul_max(int max_local, int root){
	int pid, nprocs;
	MPI_Comm_rank(..., &pid);
	MPI_Comm_size(..., &nprocs);
// Non opti

	if (pid == root)
		int * tab = new int[nprocs];
	MPI_Gather(&max_local, 1, MPI_INT, tab.max, root, MPI_COMM_WORLD);

	if (pid == root)
		max dans tab.max

// Opti ?
	MPI_Reduce(&max_local, &max, 1, MPI_INT, MPI_MAX, root, MPI_COMM_WORLD);
}

void calcul_max_et_position(int n, int* tab, int root, int* maxtab){
	int pid, nprocs;
	MPI_Comm_rank(..., &pid);
	MPI_Comm_size(..., &nprocs);

	
	
}

int main () {
	int pid, nprocs;
	MPI_Init (&argc, &argv);
	MPI_Comm_rank(MPI_COMM_WORLD, &pid);
	MPI_Comm_size(MPI_COMM_WORLD, &nprocs);

	int n = atoi(argv[1]);
	int root = atoi(argv[2]);

	int * tab;
	if (pid == root){
		tab = new int[n]
		srand(time(NULL));
		for (int i = 0; i < n; i++)
			tab[i] = rand() % 100;
	} 
	// COMPLETE

	calcul_max(, root);


	if(pid == root)
		std::cout << "max final = " << max << "\n";

	if (pid == root) delete[] tab
	
	MPI_Finalize();
	return 0;
}
```

# Partie 2 - Parallélisation

## Exercice 3

1. ...
2. ...
3. ...

## Exercice 4


1. Le sens de ``-np 4`` est la création de 4 threads
2. 
```cpp
#include <iostream>

#include <mpi.h>

  

using namespace std;

  

int main(int argc, char *argv[])

{

  int pid, nprocs;

  MPI_Init(&argc, &argv);

  MPI_Comm_rank(MPI_COMM_WORLD, &pid);

  MPI_Comm_size(MPI_COMM_WORLD, &nprocs);

  if (pid % 2 == 0)

    cout << "Bonjour ! Je suis le processus "
         << pid << " sur " << nprocs
         << " processus." << endl;
  MPI_Finalize();

  return 0;

}
```

3. 
```cpp
#include <iostream>

#include <mpi.h>

  

using namespace std;

  

int main(int argc, char *argv[])

{

  int pid, nprocs;

  MPI_Init(&argc, &argv);

  MPI_Comm_rank(MPI_COMM_WORLD, &pid);

  MPI_Comm_size(MPI_COMM_WORLD, &nprocs);

  if (pid % 2 == 0)

    cout << argv[1] << endl;

  MPI_Finalize();

  return 0;

}
```

# Exercice 2

```cpp
#include <iostream>

#include <mpi.h>

#include <math.h>

using namespace std;

int normVector(double *, int);

int main(int argc, char *argv[])
{

  int pid, nprocs;

  int n = 10;

  MPI_Init(&argc, &argv);

  MPI_Comm_rank(MPI_COMM_WORLD, &pid);

  MPI_Comm_size(MPI_COMM_WORLD, &nprocs);

  double *localVect = (double *)malloc(n * sizeof(double));

  double *globalVect;

  for (int i = 0; i < n; i++)
  {
    localVect[i] = pid + 1;
  }
  
  normVector(localVect, n);

  if (pid == 0)
  {
    globalVect = (double *)malloc(n * nprocs * sizeof(double));
  }

  MPI_Gather(localVect, n, MPI_DOUBLE, globalVect, n, MPI_DOUBLE, 0, MPI_COMM_WORLD);

  if (pid == 0)
  {
    printf("Vecteur normalisé rassemblé:\n");

    for (int i = 0; i < n * nprocs; i++)
    {
      printf("%f ", globalVect[i]);
    }

    printf("\n");
    free(globalVect);
  }

  free(localVect);

  MPI_Finalize();

  return 0;
}

  

int normVector(double *v, int n)
{
  double norm = 0.0;

  for (int i = 0; i < n; i++)
  {
    norm += v[i] * v[i];
  }
  
  norm = sqrt(norm);

  for (int i = 0; i < n; i++)
    v[i] /= norm;

}
```

# Exercice 3
5. Initialisation de `MPI`, `MPI_Comm_rank`, `MPI_Comm_size`, initialisation du tableau `E`, 
6. `MPI_Scatterv`, `MPI_Bcast` et `MPI_Gatherv`
7. 
```cpp
#include <mpi.h>
#include <stdio.h>
#include <stdlib.h>

void generation(int n, int *tab, int graine)
{
  srand(time(NULL) + graine);
  
  for (int i = 0; i < n; i++)
  {
    bool test = true;

    while (test)
    {
      test = false;
      tab[i] = rand() % 50;

      for (int j = 0; j < i; j++)
        if (tab[i] == tab[j])
          test = true;
    }
  }
}

int main(int argc, char **argv)
{
  int pid, nprocs;
  MPI_Init(&argc, &argv);
  MPI_Comm_rank(MPI_COMM_WORLD, &pid);
  MPI_Comm_size(MPI_COMM_WORLD, &nprocs);

  int n = atoi(argv[1]);
  int root = atoi(argv[2]);

  int *tab_global = new int[n];
  int *tab_local;

  int local_n = n / nprocs;

  if (pid == root)
  {
    generation(n, tab_global, pid);
  }
  
  MPI_Bcast(tab_global, n, MPI_INT, root, MPI_COMM_WORLD);

  tab_local = new int[local_n];

  MPI_Scatter(tab_global, local_n, MPI_INT, tab_local, local_n, MPI_INT, root, MPI_COMM_WORLD);
  
  int *posLocal = new int[local_n];

  for (int i = 0; i < local_n; i++)
  {
    int p = 1;
    
    for (int j = 0; j < n; j++)
    {
      int globalVal = tab_global[j];

      if (globalVal < tab_local[i])
      {
        p++;
      }
    }
    posLocal[i] = p;
  }

  int *posGlobal = NULL;

  if (pid == root)
  {
    posGlobal = new int[n];
  }  

  MPI_Gather(posLocal, local_n, MPI_INT, posGlobal, local_n, MPI_INT, root, MPI_COMM_WORLD);

  if (pid == root)
  {
    int *sortedTab = new int[n];

    for (int i = 0; i < n; i++)
    {
      sortedTab[posGlobal[i] - 1] = tab_global[i];
    }
    printf("Array: ");

    for (int i = 0; i < n; i++)
    {
      printf("%d ", sortedTab[i]);
    }
    printf("\n");

    delete[] sortedTab;
    delete[] posGlobal;
  }

  delete[] tab_local;
  delete[] tab_global;
  delete[] posLocal;

  MPI_Finalize();

  return 0;
}
```


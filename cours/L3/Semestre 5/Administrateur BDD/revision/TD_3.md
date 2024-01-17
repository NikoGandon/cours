# Exercice 1
1) Oui, si A et B sont positifs
2) Non
3) Oui, si A et B sont positifs

# Exercice 2


1) 

| Ligne | Operation            | tA  | tb  | Buffer - A | Buffer - B | Disque - A | Disque B |
| ----- | -------------------- | --- | --- | ---------- | ---------- | ---------- | -------- |
| 1     | READ A, BUFFER A, tA | 5   | -   | 5          | -          | 5          | 10       |
| 2     | READ B, BUFFER B, tB | 5   | 10  | 5          | 10         | 5          | 10       |
| 3     | tA = tB + 1          | 11  | 10  | 5          | 10         | 5          | 10       |
| 4     | WRITE A, tA          | 11  | 10  | 11         | 10         | 5          | 10       |
| 5     | tB = tA + 1          | 11  | 12  | 11         | 10         | 5          | 10       |
| 6     | WRITE B, t           | 11  | 12  | 11         | 12         | 5          | 10       |
| 7     | OUTPUT(A)            | 11  | 12  | 11         | 12         | 11         | 10       |
| 8     | OUTPUT(B)            | 11  | 12  | 11         | 12         | 11         | 12       |



2) 
   - Si Output(A) est déclaré avant Output(B), alors il peut y avoir un problème de consistance dans le cas d'une panne légère à la ligne .
   - Dans le cas inverse, ce sera à la ligne .
# Exercice 3

1) 
   
| Ligne | Instruction     |
| ----- | --------------- |
| 1     | <START T\>      |
| 2     | -               |
| 3     | -               |
| 4     | <T, A, 5>       |
| 5     | -               |
| 6     | <T, B, 10>      |
| 7     | -               |
| 8     | RU1 (FLUSH-LOG) |
| 9     | -               |
| 10    | -               |
| 11    | COMMIT<T\>      |
| 12    | RU2 (FLUSH-LOG) |

2) Pour qu'une reprise sur panne soit possible, il faut ... .

# Exercice 4

| cas | defaire | pas défaire | p-ê disque | disque    |
| --- | ------- | ----------- | ---------- | --------- |
| a   | T       | -           | A          | -         |
| b   | T       | U           | A,C        | B,D       |
| c   | T       | U           | A,C,E      | B,D       |
| d   | -       | T,U         | -          | A,B,C,D,E |

# Exercice 5

| ligne      | instruction                       |
| ---------- | --------------------------------- |
| 1          | START S                           |
| 2          | S, A, 60                          |
| a.0        | START CKPT S                      |
| 3          | COMMIT S                          |
| a.f        | END CKPT   S                      |
| 4          | START T                           |
| 5          | T, A, 10                          |
| b.0        | START CKPT T                      |
| 6          | START U                           |
| 7          | U, B, 20                          |
| c.0        | START CKPT T, U                   |
| 8          | T, C, 30                          |
| 9          | START V                           |
| 10         | U, D, 40                          |
| d.0        | START CKPT T, U, V                |
| 11         | V, F, 70                          |
| 12         | COMMIT U                          |
| 13         | T, E, 50                          |
| e.0        | START CKPT T, V                   |
| 14         | COMMIT T                          |
| b.f // c.f | END CKPT T // END CKPT T, U       | 
| 15         | V, B, 80                          |
| 16         | COMMIT V                          |
| d.f // e.f | END CKPT T, U, V // END CKPT T, V |


1) <END CKPT\> peut être fermé à à la ligne a.f
	1) Si une panne intervient à la ligne 8, il faudra défaire toutes les transactions après le COMMIT S
	2) Si une panne intervient à la ligne 10, il faudra défaire toutes les transactions après le COMMIT S
	3) Si une panne intervient à la ligne 15, il faudra défaire toutes les transactions jusqu'à la ligne 14
	4) Si une panne intervient à la ligne 13, il faudra défaire toutes les transactions jusqu'à la ligne 
	5) Si une panne intervient à la ligne 16, pas besoin de défaire mais on remonte à la ligne a.f
2) <END CKPT\> peut être fermé à la ligne b.f
	1) Si une panne intervient à la ligne 8, il faudra défaire jusqu'à la ligne a.f
	2) Si une panne intervient à la ligne 10, il faudra défaire jusqu'à la ligne a.f
	3) Si une panne intervient à la ligne 15, il faudra défaire jusqu'à la ligne b.f
	4) Si une panne intervient à la ligne 13, il faudra défaire jusqu'à la ligne a.f
	5) Si une panne intervient à la ligne 16, pas besoin de défaire mais on remonte à la ligne ??
3) <END CKPT\> peut être fermé à la ligne c.f
	1) Si une panne intervient à la ligne 8, il faudra défaire jusqu'à la ligne a.f
	2) Si une panne intervient à la ligne 10, il faudra défaire jusqu'à la ligne a.f
	3) Si une panne intervient à la ligne 15, il faudra défaire jusqu'à la ligne c.f
	4) Si une panne intervient à la ligne 13, il faudra défaire jusqu'à la ligne a.f
	5) Si une panne intervient à la ligne 16, pas besoin de défaire ?
4) <END CKPT\> peut être fermé à la ligne d.f
	1) Si une panne intervient à la ligne 8, il faudra défaire jusqu'à la ligne a.f
	2) Si une panne intervient à la ligne 10, il faudra défaire jusqu'à la ligne a.f
	3) Si une panne intervient à la ligne 15, il faudra défaire jusqu'à la ligne c.f
	4) Si une panne intervient à la ligne 13, il faudra défaire jusqu'à la ligne a.f
	5) Si une panne intervient à la ligne 16, pas besoin de défaire ?
5) <END CKPT\> peut être fermé à la ligne e.f
	1) Si une panne intervient à la ligne 8, il faudra défaire jusqu'à la ligne a.f
	2) Si une panne intervient à la ligne 10, il faudra défaire jusqu'à la ligne a.f
	3) Si une panne intervient à la ligne 15, il faudra défaire jusqu'à la ligne c.f
	4) Si une panne intervient à la ligne 13, il faudra défaire jusqu'à la ligne a.f
	5) Si une panne intervient à la ligne 16, pas besoin de défaire ?




T, E, 50
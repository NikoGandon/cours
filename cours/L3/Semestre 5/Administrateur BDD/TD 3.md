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


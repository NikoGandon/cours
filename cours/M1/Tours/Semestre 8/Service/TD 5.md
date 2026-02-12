# Exercice 1

Soit un système à 5 processus

| P ID  | Temps quand "enter" | Temps entre "enter" et "exit" |
| ----- | ------------------- | ----------------------------- |
| $P_1$ | 250                 | 50                            |
| $P_2$ | 30                  | 50                            |
| $P_3$ | 100                 | 30                            |
| $P_4$ | 20                  | 60                            |
| $P_5$ | 15                  | 20                            |

1. En sachant que la communication entre processus est de 10ms (token req, token reach avant et après que le leader call exit séparément)
   pour chaque process voici quand ils vont commencer leur section critique.   
   ![[TD5.exo1-1]]
2.  En utilisant la stratégie ring pour l'exclusion mutuelle
   Dont la stratégie est la suivante : $P_{1}\to P_{2}\to P_{3}\to P_{4} \to P_{5} \to P_{1}$
   On commence à $P_{1}$ ($t=0$), le temps pour passer au successeur est de 10ms
   Voici quand chaque process débutera sa section critique :
   ![[TD5.exo1-2]]

| P ID    | Central server | Ring |
| ------- | -------------- | ---- |
| $P_{4}$ | 20             | 30   |
| $P_{5}$ | 90             | 150  |
| $P_{2}$ | 130            | 140  |
| $P_{3}$ | 200            | 200  |
| $P_{1}$ | 270            | 260  |
# Exercice 2



1. .
2. .
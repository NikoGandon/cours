
$$PERT=\frac{O+(4 \times ML)+P}{6}$$
Réseau PERT :

A : Commencement jour 3
C : Commencement jour 6
D : Commencement jour 17

B dépend de A
E dépend de C
F dépend de C
G dépend de D et F
H dépend de B et G (B et H ont un cooldown de 4 jours)
I dépend de H
J dépend de E et H (E et J ont un cooldown de 5 jours)

$DTO_A=$ date début projet
$DTO_{B}=FTO_{A}$

| 11  | 11   | 0   |
| --- | ---- | --- |
| 0   | 4.5  | 4.5 |
| A   | 15.5 |     |

| 11  | 15.5 | 15  |
| --- | ---- | --- |
| 4.5 | 6.5  | 11  |
| B   | 26   |     |


| 5   | 26  | 0   | 
| --- | --- | --- |
| 0   | 10  | 10  |
| C   | 15  |     |

| 0   | 0   | 0   |
| --- | --- | --- |
| 0   | 20  | 20  |
| D   | 20  |     |


| 7   | 17  | 3   |
| --- | --- | --- |
| 10  | 16  | 26  |
| E   | 33  |     |


| 5   | 15  | 5   |
| --- | --- | --- |
| 10  | 5   | 15  |
| F   | 26  |     |


| 0   | 20  | 0   |
| --- | --- | --- |
| 20  | 6   | 26  |
| G   | 26  |     |


| 0   | 26  | 0   |
| --- | --- | --- |
| 26  | 8   | 34  |
| H   | 34  |     |


| 0   | 34  | 0   |
| --- | --- | --- |
| 34  | 6   | 40  |
| I   | 40  |     |


| 4   | 38  | 4   |
| --- | --- | --- |
| 34  | 2   | 36  |
| J   | 40  |     |

La durée du projet est de 40 periodes (jours par exemple)


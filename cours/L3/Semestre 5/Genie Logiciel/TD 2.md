| Tâche | Durée en semaine | Préalable |
| ----- | ---------------- | --------- |
| A     | 3                | -         |
| B     | 5                | A         |
| C     | 7                | B,G       |
| D     | 4                |           |
| E     | 3                | D         |
| F     | 2                | E,G       |
| G     | 8                | A,D,H     |
| H     | 12               |           |
| I     | 15               | H         |
| J     | 4                | I         |
| K     | 7                | L,M       |
| L     | 5                | C,F       |
| M     | 9                | J,N       |
| N     | 2                | G,I       |

```mermaid
gantt
	title Les tâches
	dateFormat DD-MM-YYYY
	section Section 
		A task :a1, 2014-01-01, 30d
		Another task :after a1, 20d 
	section Another 
		Task in Another :2014-01-12, 12d another task :24d 
```


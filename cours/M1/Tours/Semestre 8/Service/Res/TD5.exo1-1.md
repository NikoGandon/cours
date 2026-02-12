### 1. Paramètres des Processus

| P ID  | Calcul du temps d'accès |
| :---: | :--- |
| $P_1$ | $250 + 10 = 260$ |
| $P_2$ | $30 + 10 = 40$   |
| $P_3$ | $100 + 10 = 110$ |
| $P_4$ | $20$             |
| $P_5$ | $15 + 10 = 25$   |

---

### 2. Déroulé chronologique (Trace)

| Temps ($t$) | Événement / État        | Détails / Calculs              |
| :---------- | :---------------------- | :----------------------------- |
| **20**      | $P_4$ accède à la SC    |                                |
| **80**      | Jeton libre             | Temps SC : $20 + 60 = 80$      |
| **90**      | $P_5$ accède à la SC    | Transfert : $80 + 10$          |
| **110**     | Jeton libre             | Temps SC : $90 + 20 = 110$     |
| **120**     | $P_4$ récupère le jeton | Transfert : $110 + 10$         |
| **130**     | $P_2$ accède à la SC    | Transfert : $120 + 10$         |
| **180**     | Jeton libre             | Temps SC : $130 + 50$          |
| **190**     | $P_4$ récupère le jeton | Transfert : $180 + 10$         |
| **200**     | $P_3$ accède à la SC    | Transfert : $190 + 10$         |
| **230**     | Jeton libre             | Temps SC : $200 + 30$          |
| **240**     | $P_4$ récupère le jeton | Transfert : $230 + 10$         |
| **240-260** | *Attente (Idle)*        | Jeton libre entre $[240, 260]$ |
| **260**     | $P_1$ accède à la SC    |                                |
| **320**     | Jeton libre (**Fin**)   | Temps SC : $270 + 50$          |

> **Temps total du traitement : $320$**
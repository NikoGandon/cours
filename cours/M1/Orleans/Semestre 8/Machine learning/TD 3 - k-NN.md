	# Exercice 1

En utilisant le k-NN avec $k=3$ et la distance euclidienne. Pour prendre une décision concernant la classe, on teste la règle de vote à la majorité et la règle de vote à la majorité pondérée

| ligne | Taille | Hanche | Sexe | Distance                             | $\frac{1}{\text{Distance}}$ |
| ----- | :----- | ------ | ---- | ------------------------------------ | --------------------------- |
| 1     | $28$   | $32$   | M    | $\sqrt{ (29-28)^2+(34-32)^2 }=2.236$ | $0.447$                     |
| 2     | $33$   | $35$   | M    | $4,123$                              | $0,243$                     |
| 3     | $27$   | $33$   | F    | $2,236$                              | $0,447$                     |
| 4     | $31$   | $36$   | F    | $2,828$                              | $0,354$                     |
Si on classe par la majorité, on ne prends que les 3 lignes les plus proches, donc les lignes 1, 3 et 4
Donc $MFF$, alors $F$

Si on classe par la majorité pondérée, alors on utilise $\frac{1}{\text{Distance}}$
Pour la classe $M:\text{poids}\approx 0.447$
Pour la classe $F:\text{poids}\approx 0.801$
Le vote par la majorité pondérée donne aussi $F$

Quel que soit la méthode utilisée, l'individu est classé $F$
# Exercice 4

>[!error] A vérifier

Un k-NN doit être utilisé pour prédire les prix des maisons - ensemble d'entraînement (apprentissage). La nouvelle observation est présentée au modèle. Le modèle k-NN détermine les deux observations les plus proches de l'ensemble de l'entraînement pour faire la prédiction. Quelle serait la valeur du prix de la maison prédite ?

| Chambre | Nbr salle de bain | Pieds carrés | Garage | Prix |
| :------ | ----------------- | ------------ | ------ | ---- |
| $2$     | $2$               | $1810$       | $0$    | ?    |

| Chambre | Nbr salle de bain | Pieds carrés | Garage | Prix     |
| :------ | ----------------- | ------------ | ------ | -------- |
| $2$     | $2$               | $1504$       | $0$    | $333000$ |
| $2$     | $2$               | $1690$       | $0$    | $352000$ |
| $2$     | $3$               | $1945$       | $0$    | $349000$ |
| $3$     | $2$               | $2146$       | $0$    | $356000$ |
| $3$     | $2$               | $1942$       | $0$    | $351000$ |


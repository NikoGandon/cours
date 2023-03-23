# Correction examen 1-A CBD 2021-2022

## Exercice 1 :
- idCarte->espece, genre, famille, ordre
- espece -> genre, famille, ordre
- genre -> famille
- famille -> ordre
- idCarte -> continent, poids, taille, habitat, type, nourriture
- habitat -> type

## Exercice 2 :
a) 
|Date|Heure|volontaire|zone|typeZone|espece|nbr|
| :---- | ----- | ----- | ---- | ------ | -------| -----: |
|24/02/23|14-16|25,26|41018002|parc|nb|3|
|24/02/23|14-16|04,38|41018002|parc|X|5|

b)
```sql
SELECT COUNT(*) as obs_nbr, COUNT(DISTINCT espece) as es_nbr FROM OBS WHERE Left(zone, 6) = "41018"
```

c)
```sql
INSERT INTO OBS (Date, heure, volontaire, zone, typeZone, espece, nbr) VALUES ('24/02/23', '14h-18h', '04,38,39,40', 410182003, "Jardin", "X", 5)
```

d)
|Date|HeureDebut|HeureFin|volontaire|zone|typeZone|espece|nbr|
| :---- | ----- | ----- | ----- | ---- | ------ | -------| -----: |
|24/02/23|14|16|25|41018002|parc|nb|3|
|24/02/23|14|16|26|41018002|parc|nb|3|
|24/02/23|14|16|04|41018002|parc|X|5|
|24/02/23|14|16|38|41018002|parc|X|5|


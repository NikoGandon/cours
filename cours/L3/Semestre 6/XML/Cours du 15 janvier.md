
# Exemple d'utilisation de XML

Soient M Dupond et Mme Martin deux prof d'info et Mme Duran prof de math.
Dupon a 130 élèves, Martin 180 et Duran 10 :

```xml
<?xml version="1.0" encoding="UTF-8"?>
<Enseignements>
    <Matiere>
        <Nom id="1">Informatique</Nom>
        <Nom id="2">Mathematique</Nom>
    </Matiere>
    <Enseignement id="1">
        <Nom>Mr. Dupont</Nom>
        <Matiere>1</Matiere>
    </Enseignement>
    <Enseignement id="2">
        <Nom>Mme Martin</Nom>
        <Matiere>1</Matiere>
    </Enseignement>
    <Enseignement id="3">
        <Nom>Mme Duran</Nom>
        <Matiere>2</Matiere>
    </Enseignement>
    <Cours>
        <Professeur>1</Professeur>
        <Matiere>1</Matiere>
        <NbrEtu>130</NbrEtu>
    </Cours>
    <Cours>
        <Professeur>1</Professeur>
        <Matiere>1</Matiere>
        <NbrEtu>180</NbrEtu>
    </Cours>
    <Cours>
        <Professeur>1</Professeur>
        <Matiere>1</Matiere>
        <NbrEtu>10</NbrEtu>
    </Cours>
</Enseignements>
```
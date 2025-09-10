---
share_link: https://share.note.sx/uqm3l8d1#jKDqz99X9QEs4z2kAd/pbN4ODmWvlQb0MXsL8qKKZeg
share_updated: 2024-10-23T12:46:08+02:00
---
# Exercice 1 : PEAS

__Performance__ :
- Le texte est intelligible
- L'interaction avec le patient est cohérente et structurée
- Les conclusions sont probables
- Les outils utilisés sont en accord avec les hypothèses
- Active les capteurs après avoir demandé l'autorisation

__Environnement__ :
- Dynamique (le patient change d'état indépendamment de la mallette)
- Simple agent
- Partiellement observable
- Non déterministe (le patient ne fait pas toujours ce qu'on lui demande)
- Séquentiel

__Actions__ :
- Prendre une mesure
- Envoie un mail au médecin
- Donner une instruction au patient
- Émettre une hypothèse

__Sensor__ :
- Thermomètre, tensiomètre, oxymètre, otoscope, dermatoscope, stéthoscope, (microphone/clavier ?), (capteur internet ?)

# Exercice 2 : Recherche (non) informée

## Modélisation de problème

1. 
   __Contenu d'un état__ : 
	-  Grille $8\times 8$ de booléens (true: blanc, false: noir)
   __État initiale__ : 
	-  Lettre de départ
   __État finale__ :
	- Lettre d'arrivée

2. La fonction successeur: soit $G$ l'ensemble de toutes les grilles $8\times8$,
    Soit $g \in G, E \in P(G) \leftarrow\text{parties de G}$, $f:G\to P(G)$, $g \mapsto\{\text{tous les changements d'un pixel de g}\}$.

3. Le facteur de branchement : nombre max de successeur d'un élément (1 successeur par pixel = $64$), donc profondeur max à $64$ (pire cas où on doit changer tout les pixels)   

4. On prendra l'approfondissement itératif si on en veut pas aller jusqu'à la profondeur max et on évite la grande complexité en espace.

## Implantation
>[!info] 
>On a skip jusqu'à l'exercice 3


1. .
2. .
3. .
4. .


# Exercice 3 : Recherche locale

1. C'est une recherche locale car l'exploration est limitée, \[Non terminé\]
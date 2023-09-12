Noms : GANDON, MONTIGNY, PONCET, TAILLEUR
Prénoms : Nikola, Morgan, Maximilien, Thomas

# Somaire
- [[#1ère manipulation|Manipuler 2 switchs]]
	- [[#Branchement]]
	- [[#Changement adresse IP|Adresse IP]]
	- [[#Configuration du routeur]]
	- [[#Fin de la manipulation : ping|Ping]]
- [[#2ème manipulation :|VLAN]]
	- [[#Branchement VLAN]]
	- [[#Commande]]
		- [[#Création et attribution du VLAN|Création des VLANs]]
	- [[#Ping avec les VLANs|Ping]]
		- [[#Ping avec la VLAN Premiere]]
		- [[#Ping avec la VLAN Deuxieme]]
- [[#Manipulation 3 : Serveur web|Serveur web]]
	- [[#Branchement serveur web]]
	- [[#Configuration|Configuration des machines]]
	- [[#Création de l'ACL|Création de l'ACL 101]]
- [[#Conclusion]]


# 1ère manipulation :
Dans cette première manipulation, nous devions relier deux ordinateurs à deux switchs différents reliés à un routeur. 
## Branchement
![[Pasted image 20230323132344.png]]
## Changement adresse IP

Les postes ont eu les adresses IP suivantes : ``192.168.0.31`` et ``10.0.0.1`` avec leur masque respectif ``255.255.255.0``, ``255.0.0.0``.

## Configuration du routeur

On active les ports du routeur où sont connectés les switchs :
```
routeur> en
routeur# conf term
routeur(config)# interface fastEthernet0
routeur(config-if)# no shutdown
routeur(config-if)# exit
routeur(config)# interface fastEthernet1
routeur(config-if)# no shutdown
```
Ensuite, nous allons donner la route des IPs :
```
routeur# conf term
routeur(config)# interface fastEthernet0
routeur(config-if)# ip address 192.168.0.254 255.255.255.0
routeur(config-if)# exit
routeur(config)# interface fastEthernet1
routeur(config-if)# ip address 10.0.0.254 255.0.0.0
routeur(config-if)# end
routeur>
```
Le port fastEthernet0 donne vers les réseaux en ``192.168.0.x`` et le port fastEthernet1vers les réseaux ``10.0.0.x``.
## Fin de la manipulation : ping
A la fin, les deux ordinateurs ont pu envoyer et recevoir un ping entre eux.

# 2ème manipulation : VLAN
Dans cette deuxième manipulation, nous devions connecter 4 ordinateurs à un switch et les séparer dans 2 VLAN différentes.

## Branchement VLAN

![[Pasted image 20230323132429.png]]

Les ports fastEthernet 1 à 4 seront utilisés par les PC 1 à 4.

## Commande
### Configuration du switch
```
Switch> en
Switch#
```
### Création et attribution du VLAN
```
Switch> sh vlan
```
Cette commande affiche les VLANs disponibles, par exemple :
```
Id  Nom           Interfaces
 1  default       Fa0/0  Fa0/1  Fa0/2  Fa0/3
 ­                 Fa0/4  Fa0/5  Fa0/6  Fa0/7
 2  marketing     
 3  Informatique  
```

On peut créer des VLANs en utilisant la commande suivante ``vlan id`` et ``name _nom_``. Nous allons créer 2 VLANs : Premiere et Deuxieme :
```
Switch> en
Switch# conf term
Switch(config)# vlan 4
Switch(config-vlan)# name Premiere
Switch(config-vlan)# exit
Switch(config)# vlan 5
Switch(config-vlan)# name Deuxieme
```

Une fois les VLANs créés, on peut maintenant attribuer des interfaces aux VLANs, on va donc attribuer au PC1 et PC4 la VLAN 4 et au PC2 et PC3 la VLAN 5.
```
Switch# conf term
Switch(config)# interface fastEthernet1
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 4
Switch(config-if)# exit
Switch(config)# interface fastEthernet2
Switch(config-if)# switchport mode access
Switch(config-if)# switchport access vlan 5
Switch(config-if)# end
```
Nous réaliserons les même commandes dans le même ordre pour ``fastEthernet4`` et ``fastEthernet3``.

Ensuite nous réutiliserons la commande ``sh vlan``.
```
Switch> sh VLAN
Id  Nom           Interfaces
 1  default       Fa0/0  Fa0/5  Fa0/6  Fa0/7
 2  marketing     
 3  Informatique  
 4  Premiere      Fa0/1  Fa0/4
 5  Deuxieme      Fa0/2  Fa0/3
```

## Ping avec les VLANs
Pour illustrer, nous utiliserons les adresses IP suivantes - respectivement les PC1 à PC4 :
``192.168.0.1``, ``192.168.0.2``, ``192.168.0.3``, ``192.168.0.4``

### Ping avec la VLAN Premiere
PC1 ping bien vers l'adresse IP ``192.168.1.4`` (Soit le PC4) mais pas avec les deux autres.
PC4 ping bien vers l'adresse IP ``192.168.1.1`` (soit le PC1) mais pas avec les deux autres.

### Ping avec la VLAN Deuxieme
PC2 ping bien vers l'adresse IP ``192.168.1.3`` (Soit le PC3) mais pas avec les deux autres.
PC3 ping bien vers l'adresse IP ``192.168.1.2`` (soit le PC2) mais pas avec les deux autres.

Les VLANs sont donc effectifs.

# Manipulation 3 : Serveur web

Nous n'avons maheureusement pas pu faire cette partie du TP.

## Branchement serveur web

Un réseau disposant de deux switchs, deux ordinateurs - dont un servant de serveur web - et d'un routeur :

![[Pasted image 20230323133835.png]]

## Configuration
Comme dans [[#Changement adresse IP|la première manipulation]], les ordinateurs avaient leur adresse IP (le serveur avait l'ip ``192.168.0.31``).

## Création de l'ACL

Pour créer l'access-list, nous utiliserons la commande suivante :
```
routeur(config)# access-list 101 deny tcp any eq 80 192.168.0.31 255.255.255.0
```

Cette commande créer une liste d'accès nommé ``101`` visant à empêcher les connexions TCP provenant de n'importe quelle source sur le port 80 (utilisé pour les connexions HTTP) vers l'adresse IP 192.168.0.31 et tous les hôtes sur son réseau local.

# Conclusion

La première manipulation consistait à relier deux ordinateurs à deux switchs différents reliés à un routeur, en changeant leurs adresses IP et en configurant le routeur pour donner la route des IPs. Les deux ordinateurs ont pu envoyer et recevoir un ping entre eux.

La deuxième manipulation consistait à connecter 4 ordinateurs à un switch et les séparer dans 2 VLAN différentes. On a créé deux VLANs, puis on a attribué les interfaces à des VLANs en fonction de l'adresse IP des ordinateurs. Les VLANs étaient effectifs, puisque chaque ordinateur pouvait seulement communiquer avec les ordinateurs de son propre VLAN.

La troisième manipulation n'a pas pu être réalisée. Elle impliquait un réseau disposant de deux switchs, deux ordinateurs - dont un servant de serveur web - et d'un routeur. Le but était de faire en sorte que l'ordinateur puisse accéder au serveur web via son navigateur.
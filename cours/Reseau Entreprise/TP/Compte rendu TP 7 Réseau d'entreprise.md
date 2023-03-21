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
- [[#Manipulation 3 : Serveur web|Serveur web]]
	- [[#Branchement serveur web]]
- [[#Conclusion]]


# 1ère manipulation :
Dans cette première manipulation, nous devions relier deux ordinateurs à deux switchs différents reliés à un routeur. 
## Branchement
![[Pasted image 20230320190540.png]]
## Changement adresse IP

Les postes ont eu les adresses IP suivantes : ``192.168.0.31`` et ``10.0.0.1`` avec leur masque respectif ``255.255.0.0``, ``255.0.0.0``.

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
routeur(config-if)# ip address 192.168.0.254 255.255.0.0
routeur(config-if)# exit
routeur(config)# interface fastEthernet1
routeur(config-if)# ip address 10.0.0.254 255.0.0.0
routeur(config-if)# end
routeur>
```
Le port fastEthernet0 donne vers les réseaux en 192.168.0.x et le port fastEthernet1vers les réseaux 10.0.0.x .
## Fin de la manipulation : ping
A la fin, les deux ordinateurs ont pu envoyer et recevoir un ping entre eux

# 2ème manipulation : VLAN
Dans cette deuxième manipulation, nous devions connecter 4 ordinateurs à un switch et les séparer dans 2 VLAN différentes.

## Branchement VLAN

![[Pasted image 20230320185541.png]]

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
                  Fa0/4  Fa0/5  Fa0/6  Fa0/7
 2  marketing     
 3  Informatique  
```

On peut créer des VLANs en utilisant la commande suivante :
```
Switch> en
Switch# ...
```



# Manipulation 3 : Serveur web
## Branchement serveur web

Un réseau disposant de deux switchs, deux ordinateurs - dont un servant de serveur web - et d'un routeur :

## Configuration
Comme dans [[#Changement adresse IP|la première manipulation]], les ordinateurs avaient leur adresse IP (le serveur avait l'ip ``192.168.0.31``).

# Conclusion


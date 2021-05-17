# Prise en main du robot Reachy 

**/!\ ATTENTION : cette documentation a était faite pour Reachy 2019 /!\**

Reachy est une plate-forme humanoïde open-source expressive programmable avec Python. Avec Reachy vous pourrez concevoir de multiple application autant dans la reconnaissance d'image que dans la manipulation d'objets. 

Cette documentation vous guidera pour les étapes suivantes : 
* mise en place du matériel 
* connexion au robot 
* premier programme de mouvement

## 1. Matériel et branchement  

Pour faire fonctionner votre robot, il vous faudra brancher l'alimentation qui vous est fournit au dos du robot (prise ronde) :

![Dos du robot](https://user-images.githubusercontent.com/44843527/118484348-674a8580-b717-11eb-84ac-d00f595aed0a.jpg)

Une fois branché, il vous faudra pousser les boutons ON/OFF à droite des prises. Ces boutons servent à allumer les moteurs et la Rasberry Pi du robot. 

## 2. Connexion au robot 

### Logiciel et installation 

Le robot est livré avec une Rasberry Pi qui permet de controller le robot. 
Pour programmer votre robot il vous faut : 
* un ordinateur (sous windows, linux ou Mac)
* la suite Anaconda installée avec Python 3.7 minimum ( à télécharger [ici](https://www.anaconda.com/products/individual))

Pour programmer Reachy, il faut télécharger l'API Reachy. Pour cela, il vous faudra ouvrir l'invite de commande et taper cette commande *pip install reachy-2019* :
![cmd](https://user-images.githubusercontent.com/44843527/118484332-631e6800-b717-11eb-952f-3faf2696c4cb.PNG)

Une fois l'API installé vous êtes prêt à commencer ! 


**Pour programmer Reachy il y a plusieurs façon de se connecter :** 

### Se connecter directement au robot 

Pour se connecter directement au robot il vous faudra : 
* un cable HDMI
* un HUB USB
* un clavier 
* une souris 
* un écran 

Il vous suffira de connecter tout ce matériel au dos du Reachy pour voir apparaitre l'interface graphique du Raspbian sur votre écran. 
A partir de la lancer un jupyter notebook avec la commande *jupyter notebook* sur l'invite de commande. 
Et voilà, à vos clavier !

### Se connecter au serveur en wifi

Pour pouvoir vous connecter à votre Reachy il vous faudra vous connecter au moins une fois directement (comme expliqué a la section preécédente) : 
1. Se connecter directement au robot 
2. Taper la commande *jupyter notebook --ip=0.0.0.0* dans l'invite de commande du Reachy 
3. Sur l'invite de commande il y aura alors plusieurs liens, il vous faudra copier le lien du type *http:/192.164.4.1:8888/=token?...*. 
4. Se connecter au hotspot Reachy-AP 
5. Coller le lien copier auparavant dans votre navigateur.  

Si vous souhaitez optimiser cette connexion vous pouvez changer le token (le mot de passe) en tapant sur l'invite de commande du Reachy la commande *jupyter notebook password*. Cette manip permet d'éviter de copier le lien donner par l'invite plus haut qui est relativement long et complexe.  
Maintenant il vous suffira juste d'entrer l'adresse *http:/adresseIpDuReachy:8888/* puis rentrer le mot de passe que vous avez choisit. 

Et voilà vous êtes connecté a votre Reachy ! 

## 3. Premier programme 

Une fois connecté a votre robot, vous pouvez commencer a communiquer avec Reachy. 
Lorsque que vous vous connectez au Reachy vous tomber sur l'arborescence du jupyter notebook. Ici vous pouvez créer un nouveau programme ou utiliser un déjà écrit. 
Dans le dossier *dev/reachy/software/notebooks* vous trouverez des programmes permettant de faire bouger les bras ou la tête. 

Regardons en détail : 

`from reachy import Reachy, parts
 reachy = Reachy'(
  head=parts.Head(io='/dev/ttyUSB*),
)`

Ici on spécifie quelle pièce du robot on utilise, c'est-à-dire la tête (head). 











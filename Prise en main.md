# Prise en main du robot Reachy 

**ATTENTION : cette documentation a était faite sur Reachy 2019**

Reachy est une plate-forme humanoïde open-source expressive programmable avec Python. Avec Reachy vous pourrez concevoir de multiple application autant dans la reconnaissance d'image que dans la manipulation d'objets. 

Cette documentation vous guidera pour les étapes suivantes : 
* mise en place du matériel 
* connexion au robot 
* premier programme de mouvement

## 1. Matériel et branchement  

Pour faire fonctionner votre robot, il vous faudra brancher l'alimentation qui vous est fournit au dos du robot (prise ronde) :

![Dos du robot](https://github.com/ta18/Reachy_Nautilus/images/reachy-back-fixation.jpg?raw=true)

Une fois branché, il vous faudra pousser les boutons ON/OFF à droite des prises. Ces boutons servent à allumer les moteurs et la Rasberry Pi du robot. 

## 2. Connexion au robot 

Le robot est livré avec une Rasberry Pi qui permet de controller le robot. 
Pour programmer votre robot il vous faut : 
* un ordinateur (sous windows, linux ou Mac)
* la suite Anaconda installée avec Python 3.7 minimum ( à télécharger [ici](https://www.anaconda.com/products/individual))

Pour commencer il vous faudra ouvrir l'invite de commande et installer l'API Reachy :




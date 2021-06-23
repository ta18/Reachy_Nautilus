---
title: "Connexion au robot"
menu:
  main:
    name: "Connexion au robot Reachy"
    weight: 2
    parent: "capsules"
---

| Classe de capsule  | &emsp; durée recommandée |
|:-------------------|:------------------|
| Setup  &emsp;  🛠️  |&emsp; 10 min      |


## 📗 Ressources

Plus d'informations sur le robot et sa mise en route avec ces liens :  
- [Doc Pollen Robotics](https://pollen-robotics.github.io/reachy-2019-docs/docs/getting-started/)  (en anglais)
- [Prise en main Reachy](https://github.com/ta18/Reachy_Nautilus/blob/main/Prise%20en%20main.md)

💻 : Procédure exécuter sur votre poste de travail    
🤖 : Procédure à exécuter sur le robot


## 1. Premiere mise en route 

1. Branche l'alimentation fournie sur la prise ronde au dos du robot.
2. Vérifier que l'HDMI de l'écran et le HUB USB sont bien brancher au dos du robot 
3. Appuie sur le bouton poussoir a gauche pour mettre sous tension le NUC et sur le bouton ON/OFF à droite pour mettre sous tension les moteurs.
4. Allumer l'écran du Reachy

![Dos du robot](img/back.png)

## 2. Connexion au robot

Le robot Reachy est livré avec une carte NUC (mini ordinateur) qui permet de contrôler les moteurs et les périphériques qui l'équipent.<br>
Pour programmer le robot il y a 2 solutions : 
* **En SSH :** Utiliser son ordinateur personnel et se connecter en SSH au robot 
* **En direct :** Se brancher directement sur le mini ordinateur NUC à l'aide d'un écran, d'un clavier et d'une souris. 

Dans les deux cas il n'y a aucun logiciel particulier à installer. 

### Connexion au robot via SSH 📶

1. 🤖 Ouvrir la session Reachy, mot de passe *reachy* (cf section 1.) 
2. 🤖 Connecte le robot au wifi (partage de connexion via smartphone ou wifi privé)
3. 💻 Connecte l'ordinateur avec lesquel tu veux commander Reachy au même wifi que le robot 
*Exemple* : je connecte le robot au wifi *Maison*. Je connecte mon ordinateur portable au wifi *Maison*.
4. 💻 Connecter son ordinateur au robot via SSH : 
`ssh reachy@adresseIP`
mot de passe : reachy 
5. 💻 Lancer jupyter notebook 

l'étape 1. et 2. est à faire une seule fois lors de la premiere connexion au robot en direct. Après tu auras juste à effectuer les étapes 3. 4. et 5.

**Si cela ne fonctionne pas...** 

✅ Vérifie que tu es bien connecté au robot en tapant dans un terminal ou une fenêtre de commande :

```bash
ping 192.168.4.1
```
s'il n'y a pas d'erreur c'est que tu es bien connecté au du robot.

✅ Fait attention à toujours bien rester connecté au même wifi que le robot. 

Et voilà tu es connecté au robot Reachy, bravo ! 🎉

**Trouver l'adresse IP**  
🤖 Pour trouver l'adresse IP de reachy tu peux taper la commande suivante sur un terminal du robot : `ifconfig`
![ip](img/ip.png)
l'adresse IP est encadré en vert sur l'image ci-dessus. 
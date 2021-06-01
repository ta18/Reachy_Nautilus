# Cahier des charges des capsules

## Introduction 

Ce projet consiste à mettre en route le robot Reachy de chez Pollen Robotics et à créer des séquences pédagogiques à l'intention des élèves de l'ENSAM mais également open source.
Le concept de capsules pédagogiques (initialement nugget) vient de l’Institut européen d'innovation et de technologie (EIT). Ce sont des petits objets d’apprentissage qui sont reliés entre eux via différents didacticiels qui permettent d’apprendre et de vérifier des compétences. Ces didacticiels sont appelés Chemin d’apprentissage (Learning Path). Le but de ce projet a donc été de créer différentes capsules, afin de pouvoir proposer des chemins d’apprentissage adaptés à chaque formation. 

## 1. Capsule chifoumi 

Cette capsule porte sur le jeu du chifoumi (pierre-feuille-ciseaux) qui se joue généralement en duel même s’il est possible de s’affronter à plusieurs. Pour commencer les joueurs comptent jusqu’à trois en mettant la main dans le dos. Une fois à trois les joueurs révèlent leur main (pierre, feuille ou ciseaux) en même temps. La plus forte des formes l’emporte et le joueur marque le point gagnant. Si les deux joueurs utilisent la même forme c’est un match nul.

**La pierre** : est représentée par un poing fermé.  
**La feuille** : est représentée par une main à plat, la paume en direction du sol.  
**Les ciseaux** : sont représentés par deux doigts formant un V.  
  
Force de chaque forme au Pierre – Feuille – Ciseaux :  
* La pierre écrase les ciseaux et gagne.  
* La feuille enveloppe la pierre et gagne.  
* Les ciseaux découpent la feuille et gagnent.  

Le but de cette capsule est de pouvoir jouer au chifoumi contre le robot. Pour cela nous allons entrer un réseau de neurones afin de reconnaitre les 3 formes de main. Ensuite une phase de programmation du robot devra être faite : mouvement du bras et de la pince et travaille sur les stratégies du chifoumi (ex : si mon adverse a fait pierre avant alors je vais faire ?). Il existe des statégies pour ce jeu notamment sur l'enchainement des forme (ex : Si votre adversaire joue 2 fois le même signe à la suite, le prochain est sans aucun doute un signe différent. Ripostez donc avec un signe approprié vous avez 1 chance sur 2 de remporter la main.) 

Le reachy dont nous disposons est composé de la main en pince, il faudra donc réfléchir aux 3 formes de mains qui ne sont pas les mêmes que sur une main humanoïde. 
Cette thématique "main" pourrait faire partie du projet : la capsule pourrait commencer par une partie hardware où les élèves auraient pour consigne de concevoir une main capable d'effectuer les formes pierre, feuille et ciseaux. 

## 2. Capsule Reachy expressif (jeu mémoriel)

### 2.1 Projet existant 

Les personnes atteintes d’autisme voient, entendent et perçoivent le monde de façon différente des autres, ce qui influence la manière dont ils interagissent avec eux. Cela rend les activités axées sur la communication assez difficiles pour les enfants atteints de troubles du spectre autistique (TSA). 

J'ai effectué plusieurs recherches sur internet au sujet des applications robotiques ou web à l'intention des enfants avec autisme :   
JEMIme est un projet de jeu éducatif sous forme de serious Game.    
Le projet JEMImE vise à concevoir de nouveaux algorithmes de reconnaissance multimodale d’émotions pour évaluer la qualité des émotions produites par des enfants. L’objectif est d’aider les enfants avec autisme à apprendre à imiter et à mimer des émotions faciales et vocales afin d’exprimer l’expression appropriée à un contexte donné.  
Ils ont centré le jeu sur 3 émotions : la colère, la tristesse et la joie.

L’équipe PIRoS a également créé un dispositif ludique et engageant pour stimuler les enfants en leur demandant d’imiter les postures et les gestes du robot. Après quelques minutes, les rôles s’inversent et le robot peut à son tour imiter, grâce à l’intelligence artificielle, les mouvements réalisés par l’enfant.

Les chercheurs d'EngageME qui travaillent sur le projet EngageME, financé par l’UE, viennent de créer un cadre d’apprentissage automatique personnalisé pour les robots utilisés lors du traitement de l’autisme (pendant les sessions de thérapie). Comme ils l’expliquent dans leur communiqué publié dans «Science Robotics», ce cadre aide les robots à percevoir automatiquement l’affect – comportement gestuel, vocal et facial – et à intéresser les enfants pendant qu’ils interagissent avec eux.

documentation : 

[Travaux de l'équipe PIRos](https://www.sorbonne-universite.fr/actualites/la-robotique-au-service-des-enfants-autistes)   
[JEMIme](http://www.innovation-alzheimer.fr/jemime/)   
[EngageME](https://cordis.europa.eu/article/id/123847-teaching-robots-how-to-interact-with-children-with-autism/fr)   

### 2.2 Proposition de capsule 

Ici nous aimerions profiter du coter très émotionnel de Reachy qui provient surement du mouvement de la tête et des antennes.  
En nous inspirant de ces projets, je propose de créer une capsule pédagogique de mise en situation :   
Un jeu mémoriel à l'intention des enfants avec autisme qui leur permettrait de mémoriser un certain nombre d'émotions.   
Déroulement du jeu mémoriel :   
1. Le robot produit des émotions par des expressions faciales et corporelles (posture/geste) et des expressions vocales. On peut commencer par 3/4 émotions. 
2. L'enfant doit retenir les émotions et le nom de l'émotion annoncée (on peut aussi associer l'émotion à une couleur mais il faut vérifier si ca ne biaise pas l'apprentissage + comment annoncer l'émotions ?). 
3. Le robot va refaire les émotions dans un ordre aléatoire et l'enfant devra les reconnaitre. 

Partie optionnelle a étudié :   
L'apprentissage du robot de nouvelles émotions qu'il ne connait pas déjà. 

## 3. Capsule Reachy kiné 

Le projet KERAAL, porté par IMT Atlantique, travaille à la conception d’un robot humanoïde capable d’accompagner les patients atteints de lombalgie lors des exercices de rééducation à domicile. Grâce à des algorithmes d’apprentissage supervisé, le robot peut montrer au patient le bon mouvement à effectuer et corriger ses erreurs en temps réel.
En 2014, les chercheurs avaient commencé des tests avec le robot Nao, développé par SoftBank Robotics. Aujourd'hui l'expérience est faite avec Poppy le grand frère de Reachy. 
Bien que les sujets aient beaucoup d’appréhension à l’idée de travailler avec un robot, Poppy a été perçu de manière très positive. Le robot a également motivé les patients à effectuer leurs exercices. 

Documentation : [projet KERAAL](https://imtech.wp.imt.fr/2018/01/24/robot-reeducation/)   

En nous inspirant de ce projet, je propose de créer une capsule pédagogique de mise en situation :   
Un réseau de neurones pré-entrainé permettra de détecter les poses et mouvements des patients en séances, si le robot connait ces mouvements il analysera s'ils sont bien exécutés. S'ils ne le sont pas il montrera comment les effectuer bien. 
Une base de données sera donc nécessaire. 
On peut imaginer commencer à 3 mouvements du haut du corps (bras et tête). Il faudra donc trouver les exercices faisables par Reachy. 



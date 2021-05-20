# Prise en main du robot Reachy 

⚠️ **ATTENTION : cette documentation a était faite pour Reachy 2019** ⚠️ 

Reachy est une plate-forme humanoïde open-source expressive programmable avec Python. Avec Reachy vous pourrez concevoir de multiple application autant dans la reconnaissance d'images que dans la manipulation d'objets. 

Cette documentation vous guidera pour les étapes suivantes : 
* mise en place du matériel 
* connexion au robot 
* premier programme de mouvement

## 1. Matériel et branchement  

Pour faire fonctionner votre robot, il vous faudra brancher l'alimentation qui vous est fournit, au dos du robot (prise ronde) :

![Dos du robot](https://user-images.githubusercontent.com/44843527/118484348-674a8580-b717-11eb-84ac-d00f595aed0a.jpg)

Une fois branché, il vous faudra pousser les boutons ON/OFF à droite des prises. Ces boutons servent à mettre sous tension les moteurs et la Raspberry Pi du robot. 

## 2. Connexion au robot 

### Logiciel et installation 

Le robot est livré avec une Rasberry Pi qui permet de le controller. 
Pour programmer le robot il vous faudra juste un ordinateur (sous Windows, Linux ou bien même un Mac) sans rien à installer de particulier.

**Pour programmer Reachy il y a plusieurs façon de se connecter :** 

### Se connecter directement au robot 

Il est possible de se connecter directement a la Raspberry Pi intégrée dans le robot afin de programmer le robot. Vous aurez accès à l'interface graphique de Raspbian où vous pourrez configurer tout ce dont vous avez besoin (WiFi, accès ssh, connexion, etc.). Veuillez consulter la documentation officielle de Raspberry-Pi pour plus d'informations.

Pour se connecter directement au robot il vous faudra : 
* un cable HDMI
* un HUB USB
* un clavier (USB)
* une souris (USB)
* un écran (HDMI)

Il vous suffira de connecter tout ce matériel au dos du Reachy pour voir apparaitre l'interface graphique du Raspbian sur votre écran. 
Lorsque tout est branché switcher les bouton ON/OFF des moteurs et de la Raspberry. Puis vous pourrez lancer jupyter notebook avec la commande *jupyter notebook* sur l'invite de commande.  

/!\ **La mise sous tension de la carte Raspberry Pi doit se faire après le branchement des différents élèments USB et HMDI.**

Et voilà, à vos claviers !

### Se connecter au serveur en wifi

Pour pouvoir vous connecter à votre Reachy il vous faudra vous connecter au moins une fois directement (comme expliqué a la section preécédente) : 
1. Se connecter directement au robot 
2. Taper la commande *jupyter notebook --ip=0.0.0.0* dans l'invite de commande du Reachy 
3. Sur l'invite de commande il y aura alors plusieurs liens, il vous faudra copier le lien du type *http:/adresseIpDuReachy:8888/=token?...*. 
4. Se connecter au hotspot Reachy-AP 
5. Coller le lien copier auparavant dans votre navigateur sur votre ordinateur.  

Pour connaitre l'adresse IP d'un appareil : 
* sous windows : clique droit sur le réseaux/proprietes/IpV4 
* sous linux : 
Si vous souhaitez optimiser cette connexion vous pouvez changer le token (le mot de passe) en tapant sur l'invite de commande du Reachy la commande *jupyter notebook password*. Cette manip permet d'éviter de copier le lien donner par l'invite plus haut qui est relativement long et complexe.  
Maintenant il vous suffira juste d'entrer l'adresse *http:/adresseIpDuReachy:8888/* puis rentrer le mot de passe que vous avez choisit. 

**Si la connexion ne fonctionne pas :** 
✅ Pour vérifier que vous etes bien connecté au hotspot du Reachy, vous pouvez pinger son adresse IP :
`ping 192.168.4.1` sur un terminal de commande. S'il n'y a pas d'erreur c'est que vous etes bien connecté au bon appareil.
Faites attention a toujours bien être connecté au hotspot Nemo. 

Et voilà vous êtes connecté a votre Reachy ! 🎉

## 3. Premier programme 

### 📗 Documentation

Si tu souhaites d'autres informations sur le robot et sa mis en route tu peux consulter ces liens :
[Doc Pollen Robotics](https://pollen-robotics.github.io/reachy-2019-docs/docs/program-your-robot/)
[Doc API Reachy](https://pollen-robotics.github.io/reachy-2019/index.html)


Une fois connecté a votre robot, vous pouvez commencer a communiquer avec Reachy. 
Lorsque que vous vous connectez au Reachy vous tomber sur l'arborescence du jupyter notebook. Ici vous pouvez créer un nouveau programme ou utiliser un déjà écrit. 
Dans le dossier *dev/reachy/software/notebooks* vous trouverez des programmes permettant de faire bouger les bras ou la tête. Vous pouvez également utiliser les notebooks présent ici [Notebook](https://github.com/ta18/Reachy_Nautilus/tree/main/notebook) qui sont créer spécialement pour cette notice. 

Regardons en détail le code :

`from reachy import Reachy, parts`
On renseigne l'API utilisée, ici c'est l'API Reachy.

On spécifie les pièces du robot sur lesquels on va travailler :
```
reachy = Reachy( 
    right_arm=parts.RightArm(io='/dev/ttyUSB*', hand='force_gripper'),
    head=parts.Head(io='/dev/ttyUSB*'), 
    )
```

Ici, nous spécifions que nous voulons ajouter une partie bras droit et une partie tête. Ces pièces doivent être trouvées sur des ports séries USB de type «/ dev / ttyUSB \*». C'est le nom standard du port série sur un système Linux (en effet la raspberry présente dans le robot est sous Linux).
Pour le bras, nous précisons quels types de main y est attachée. Dans notre cas, nous le définissons sur «force_gripper» (main en forme de pince).

On peut, si on le souhaite, spécifier une seule pièce par exemple la tête :
`reachy = Reachy'( head=parts.Head(io='/dev/ttyUSB*), )`

Si tu ne vois aucune erreur au lancement de ces lignes de code, bonne nouvelle, tu es maintenant connecté au Robot et toutes la pièce tête a bien était trouvée !

## Compliant ou pas ?

Les servomoteurs utilisés dans le bras de Reachy ont deux modes de fonctionnement:

- **compliant** : les moteurs sont doux et peuvent être tournés librement à la main. Il ne peut pas être contrôlé.
- **non compliant** : les moteurs sont durs et ne peuvent pas être déplacés à la main. Il peut être contrôlé en définissant une nouvelle position cible.

Pour que Reachy conserve sa position et te permette de contrôler ses moteurs, tu dois les rendre non compliant. Pour ce faire, tu peux utiliser la propriété compliant : 

Par exemple, pour rendre le bras non compliant, exécute le code suivant:
`reachy.right_arm.compliant = False`
Maintenant, le bras doit être dur, tu ne peux plus le bouger à la main.

Pour le remettre en compliant, exécute simplement:
`reachy.right_arm.compliant = True`

⚠️ **Attention** : il ne faut surtout pas forcer les moteurs lorsque le robot est en mode "non compliant" cela pourrait endommager les moteurs. 

## Bouger le bras ou la tête

Pour bouger des parties du robot, tu va utiliser les méthodes des classes Head() et Right_Arm() :
Documentation des classes et méthodes : [ici](https://pollen-robotics.github.io/reachy-2019/autoapi/reachy/index.html#)

#### Les méthodes sur les moteurs :

### goto(goal_position, duration, wait)

Pour faire bouger notre moteur, nous utiliserons la méthode goto. Nous définirons une position cible en degrés et une durée de déplacement en seconde.
Ici on défini une position pour chaque partie du bras et une durée de déplacement total :

```
reachy.goto({ 
    'right_arm.shoulder_pitch': 0, 
    'right_arm.shoulder_roll': 0, 'right_arm.arm_yaw': 0, 
    'right_arm.elbow_pitch': -90, 
    'right_arm.hand.forearm_yaw': 0, 
    'right_arm.hand.wrist_pitch': 0, 
    'right_arm.hand.wrist_roll': 0, 
    'right_arm.hand.gripper': 0, 
    }, 
    duration=3, 
    wait=True)
```

On peut utiliser cette méthode pour une seule partie du bras. Par exemple, pour le coude :
`reachy.right_arm.elbow_pitch.goto( goal_position=90, duration=2, wait=True, )`

### goto(thetas, duration, wait)

Pour la tête on utilise également la méthode goto() avec thetas la position cible en dégrés :
`reachy.head.neck.goto(thetas=(-10,-10,-10), duration=3, wait=True)`

**Attention à la durée d'atteinte des position : ne pas mettre des durée trop courte.**

### goal_position(soi même)

Ici on utilise une méthode inférieur à la méthode goto() pour contrôler le moteur.
Tu dois être prudent en utilisant cette méthode car le moteur essaiera d'atteindre cette nouvelle position d'objectif aussi vite que possible. Et c'est vraiment rapide (jusqu'à ~ 600-700 degrés par seconde)! Une solution de contournement consiste également à utiliser la propriété moving_speed pour définir la vitesse maximale que le moteur peut atteindre.

```
reachy.right_arm.elbow_pitch.moving_speed = 50 # in degrees per sec 
reachy.right_arm.elbow_pitch.goal_position = 110 # in degrees
```

#### Les méthodes sur la tête :

### look_at(x, y, z, duration, wait)

Cette méthode permet de faire en sorte que la tête regarde un point 3D dans l'espace :
`reachy.head.look_at(1, 0, 0, duration=1, wait=True)`

### Enregistrer une trajectoire et la reproduire

Jusqu'à présent, nous vous avons fait bouger le robot en utilisant goto et une position prédéfinie. Cela fonctionne bien pour un mouvement simple mais parfois, pour des mouvements complexes, il semble plus agréable de pouvoir enregistrer un mouvement et l'enregistrer.

Avec cette approche, tu vas effectuer des trajectoires entières avec Reachy en le déplaçant à la main (en utilisant le mode compliant) et enregistrer les positions des différents moteurs. Selon ce que vous voulez, vous pouvez enregistrer un seul moteur ou plusieurs à la fois. Un objet TrajectoryRecorder va rendre ce processus vraiment simple.

Pour enregistrer un mouvement sur le bras droit :
`from reachy.trajectory import TrajectoryRecorder, TrajectoryPlayer`

On créer une variable recorder :
`recorder = TrajectoryRecorder(reachy.right_arm.motors)`

Lorsque tu est pret effectuer shift + entrer sur la cellule :
`recorder.start()`

et Lorsqu'on veut stopper l'enregistrement :
`recorder.stop()`

Ensuite pour rejouer la trajectoire :
```
player = TrajectoryPlayer(reachy, recorder.trajectories) 
player.play(wait=True, fade_in_duration=3)
```











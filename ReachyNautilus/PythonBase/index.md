---
title: "Python : les bases"
menu:
  main:
    name: "Python : les bases"
    weight: 4
    parent: "nautilus"
---

### **<p style="text-align: right;">Capsule info ℹ️</p>**
### <p style="text-align: right;">Durée : 10min</p>

## 🎒 Prérequis

- Lycée et +

## 🎓 Acquis d'apprentissage visés
A l'issue de cette activité, l'apprenant saura : 
- Manipuler les variables, le calcul et les conditions sur variables  
- Manipuler mes listes et tupples 

## 📗 Documentation

Les informations de cette capsule sont tirées des liens suivants :
[Cours sur Python](https://courspython.com/bases-python.html)

Memento Python à toujours avoir à coter de soi : 
{{<pdf src="https://perso.limsi.fr/pointal/_media/python:cours:mementopython3.pdf" >}}

## Introduction 

Python est un langage de programmation interprété, qui ne nécessite donc pas d’être compilé pour fonctionner. Un programme ” interpréteur ” permet d’exécuter le code Python sur n’importe quel ordinateur. 
Il dispose de structures de données de haut niveau et permet une approche simple mais efficace de la programmation orientée objet.

Pour coder en Python vous pouvez utiliser de nombreux IDE. Voir [capsule prise en main de jupyter notebook](/ReachyNautilus/JupyterNotebook/index.md)  


## 1. Variables

Chaque information que vous souhaitez réutiliser plus tard s’appelle une variable. Nous pouvons voir une variable comme une étiquette que vous colleriez sur un objet pour vous souvenir de son nom. 
Pour définir une variable, nous allons taper son nom, un signe égal puis sa valeur. Par exemple :  
   
```
prenom = "nemo"
prenom
> nemo
```  
Pour afficher le contenu d'une variable il suffit d'entrer le nom de la variable ou d'effectuer un print().  

Si tu souhaites redéfinir cette variable il suffit de réécrire :   
`prenom = "dory"`

**Les différentes nature de variables :** 
* nombre (integer ou float) : les integer désigne les nombres entiers, et les float les nombres décimaux.  
* string : il s'agit d'une chaine de caractères (texte, nombre ...etc) qui doit être encadrée par des guillemets "". \n pour un retour à la ligne.    
* boolean : il s'agit d'une information vraie ou fausse (true ou false).   

## 2. Le calcul 

Les opérations de bases sont : 
*  <texte>+</texte> : l'addition 
* <texte>-</texte> : la soustraction 
* <texte>*</texte> : la multiplication 
* / : la division 
* ** : la puissance 
* // : la division entière
* % : le reste de la division 

Exemple :  
```
a = 2
b = 3 
c = a+b
c
>5 
```
## 3. Les boucles if 

Les conditions ont le même sens en informatique que dans le langage courant, elles permettent d'effectuer une action dans un cas précis. Si (événement), dans ce cas (action). 

Les différentes condtions possibles sont : 
* si *n* est égal à 0 : `if(n==0)`  
* si *n* est supérieur à 0 :`if(n>0)` 
* si *n* est différent de 10 : `if(n!=10)`
* si *n* est compris entre 0 et 10 : `if(n>0) and if(n<0)`  

Exemples : 
```
n = input("Entrer un nombre : ")
if n<0:
print("Le nombre est négatif")
elif n==0:
print("Le nombre est égal à zéro")
else:
print("Le nombre est positif")
```
## 4. Les listes et tupples

### Liste

Une liste est une collection d’éléments séparés par des virgules, l’ensemble étant enfermé dans des
crochets. Dans une liste on peut stocker des chiffres, des chaines de caractères, des boléens ... etc. 

`robotique = ['informatique', 'mécatronique', 'IA']`

Pour manipuler les listes plusieurs choses sont utiles :  
```
print(robotique[0])
>informatique
```
permet d'afficher la valeur du premier élèment de la liste 
```
print(len(robotique))
>3
```
permet de connaitre la taille de la liste 

```
robotique.append("math)
>print(robotique)
>['informatique', 'mécatronique', 'IA', 'math']
```
permet d'ajouter un élèment à la liste 

D'autres méthodes de l'objet liste : 
* **sort()** : trie les élèments dans l'ordre croissant  
* **reverse()** : inverse l'ordre des élèments  
* **index()** : retourne l'indexe d'un élèment
* **remove()** : enlève un élèment 

l'instruction range() créer une liste pré-remplie de n élèments : 
```
for i in range(6):
    print(i)
>1, 2, 3, 4, 5
```
On peut également définir où commencer, ou finir et le pas avec range(start, stop, step) : 
```
for i in range(1,10,2):
    print(i)
>1, 3, 5, 7, 9
```

Slicing :

```
nombres = [2, 45, -7, 19, 183]
print(nombres[1:3]) 
>[45, -7]
print(nombres[2:3])
>[-7]
print(nombres[2:])
>[-7, 19, 183]
print(nombres[:2])
>[2, 45]
```

### Tupples

Les tuples servent à créer des structures dont le nombre d'éléments ne bouge pas (on dit qu'ils sont immuables).
Elles commencent par une parenthèse ouvrante, un ensemble d’objets séparés par des virgules et une parenthèse fermante.

`courses = ('banane', 'oeufs', 'pain', 'sauce')`

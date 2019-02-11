# Une Introduction au design génératif

## I. Introduction
### Objectifs du workshop

1. Une première approche de la programmation.
 
   Qu'est-ce que Programmer ? : faire faire ce que l'on veut à un ordinateur pour résoudre des problèmes => lui parler dans une langue qu’il comprend

2. Découvrir un nouveau moyen d’expression ouvrant de nombreuses possibilités:
   - créations visuelles, sonores, 
   - interactions, 
   - web-art, 
   - portfolios, 
   - jeux
   - ...

### p5js vs processing.org
* Librairie javascript: 

   **Javascript** : = le langage de programmation du web. Est interprété par le navigateur (firefox, chrome…).

   **librairie** : ensemble de fonctionnalités mises à disposition par d’autres développeurs

* Page web:

   p5js a été conçu pour fonctionner au sein d’une page web, dans un élément html5 spécifique (canvas) qui peut afficher des éléments graphiques.
   
   p5js facilite l’utilisation de canvas, la création dynamique d’éléments html, l’interaction avec l’utilisateur, la manipulation de l’audio et de la vidéo.

## II. Concepts de base de la programmation

### Syntaxe


### Variables

Une variable est un emplacement de la mémoire de l’ordinateur dans lequel on peut stocker une valeur. Il nous est possible de nommer cet emplacement afin de pouvoir retrouver la valeur ultérieurement
Déclaration
Pour déclarer une variable, on utilisera le mot clé let suivi du nom que l’on veut donner à la variable. On veillera à respecter les conventions de nommage, à éviter de redéfinir des variables existantes ainsi qu’à éviter de faire commencer le nom des variables par un chiffre ou un caractère spécial. 

D’autre part, les caractères autres que _ et $ sont interdits dans les noms de variables (ils ont tous une autre signification dans le langage. Par exemple : -,+ etc, l’interpréteur javascript considérera ces caractères ciomme des opérateurs et tentera de les utiliser comme tels).

#### Exemples

**déclaration**

    let maVariable = 10;
 
**utilisation**

    maVariable * 2; // vaut 20


#### Tableaux (arrays)
Un array (tableau) est un ensemble d’éléments pouvant être stockés au sein d’une même variable. Les permettent de conserver un en semble de données au sein d'une même variable. Cette variable peut ensuite être parcourue par une [boucle](#boucles)


    let tableau = [46,4500,80];

crée un array nommé `tableau` qui contiendra 3 valeurs distinctes (46, 4500,80). Ces valeurs seront indexées et nous pourrons y accéder en faisant référence à leur index (ATTENTION: les index commencent à 0):
    
    tableau[0]; // vaut 46
    tableau[1]; // vaut 4500
    tableau[2]; // vaut 80

NB: Il est possible de créer des arrays à plusieurs dimensions (des arrays, d’arrays, si on veut).

### Structures de contrôle
- Conditions

   L’une des tâches les plus communes d’un programme informatique est de prendre une décision (changer de comportement) selon différents paramètres.
Les structures conditionnelles permettent de prendre ce genre de décisions en se basant sur des tests renvoyant une réponse vraie ou fausse (true/false). 

	- `if... (elseif...) else`
      
      ```javascript
      // exemple
      let result = 6+3;
      
      if(result > 10){
            // si le résultat est supérieur à 10
            // le code qui se trouve dans ce bloc est exécuté
      } else {
            // sinon (càd le résultat est inférieur à 10)
            // le code de ce block sera exécuté
      }
      ```
      	
	- `switch... case`
	
- Répétition (<a name="boucles" href="#boucles">boucles</a>)

   Les boucles sont des structures du langage qui permettent de répéter la même opération un nombre prédéterminé de fois. Elles sont notamment pratiques pour parcourir le contenu des arrays, ou répéter une forme

	- **for**

      ```javascript 
		for(var i = 0; i < 10; i++){
		    // instructions se répéteront 10 fois
		    // à chaque itération de la boucle, la variable i aura une valeur entre 0 et 9
		}
		```

   - **while**

      ```javascript
		while(condition){
		    // instructions se répéteront tant que 
		    // la condition renvoit true
		}
		``` 


   
### Fonctions
Une fonction est un bloc de code contenant un ensemble d’instructions pouvant être appelées en une seule fois.
Une fonction peut avoir un nom (il existe des fonctions anonymes), peut prendre un ensemble de paramètres et peut renvoyer une valeur.
Il existe un ensemble de fonctions fournies par le langage lui-même ou les bibliothèques, un ensemble de fonctions définies par le framework (`draw()`, `rect()`...). Il est également possible de définir nos propres fonctions. 

exemple: 

```javascript
function maFonction(param1, param2){
    // instructions
    // return *valeur* [optionnel] 
}
``` 

### Objets et classes
En programmation, les classes sont une structure de données particulière qui permet de stocker des valeurs (variables ou **propriétés** qui peuvent être des nombres, chaînes de caractères, tableaux, objets...), mais également des fonctions ou **méthodes**. 


### Bibliothèques (libraries)
Une bibliothèque est un ensemble de fonctions ou de classes écrites par d'autres développeurs résolvant un même problème ou fournissant une fonctionnalité supplémentaire qu'il est possible d'intégrer dans son code. 

**exemples**

- la bibliothèque [p5.sound](https://p5js.org/reference/#/libraries/p5.sound)
- la bibliothèque [p5.dom](https://p5js.org/reference/#/libraries/p5.dom)

## III. Découvrir p5js

### Premiers pas

   **`setup()` - `draw()`** : fonctions mises à disposition par la librairie (p5.js). Elles doivent être implémentées par l'utilisateur et permettent 1. de configurer le sketch (*setup*) 2. de définir définir le code qui sera exécuté dans la boucle d'animation (*draw*)
   
   **Le canvas** (la toile) : l’espace au sein de la page web dans lequel 

   **createCanvas(largeur,hauteur)**
les paramètres/arguments d’une fonction

   **Le système de coordonnées**
La grille : x = largeur; y = hauteur
origine (0,0)

   **dessiner un point** : `point(x,y);`


###Formes

####Primitives 2d
- `line(x1, y1, x2,y2)`

- `ellipse(x, y, l, h)`

- `rect(x, y, l, h)`

- `triangle(x1,y1, x2, y2, x3, y3)`

- `quad(x1,y1, x2, y2, x3, y3, x4, y4)`

#### Attributs de formes
- `strokeWeight(n)` 
    définit l’épaisseur du trait
- `rectMode(CENTER|CORNER)` permet de changer l’origine des coordonnées d’un rectangle (coin supérieur gauche ou centre)

### Couleurs

- `background(*couleur*)`
    
- `fill(*couleur*)` / `noFill()` : définit le remplissage de la forme
- `stroke(*couleur*)` / `noStroke()` : définit le trait de la forme
- `colorMode(*mode*)` : mode peut être RGB ou HSV

**couleur** : plusieurs notations possibles :

- 1 valeur de 0 à 255 : niveaux de gris
- 2 valeurs de 0 à 255 : niveaux de gris + opacité (transparence)
- 3 valeurs de 0 à 255: rouge, vert, bleu
- 4 valeurs de 0 à 255: rouge, vert, bleu + opacité
- la notation hexadécimale (web, de type “#070707”)

   il est possible d'utiliser des *variables* pour stocker la valeur d'une couleur. Exemple: `var rouge = color(255,0,0);`

### Variables mises à disposition par p5.js

    

### Animation
- la boucle draw
    Boucle infinie qui se répétera durant toute l’exécution du sketch.

- les frames

   Une frame est une image générée par la fonction draw. Par défaut, p5js essayera d’afficher 60 frames par secondes (on peut modifier ce comportement avec la fonction frameRate(/*nbreDeFrames*/); )

- Le background

   Redéfinir la couleur de fond à chaque frame permet de partir d’un canvas vierge => simuler le mouvement
   

### Interaction
mousePressed() / mouseReleased() : fonctions dont l'implémentation est confiée à  définir, au même titre que setup() ou draw()
keyPressed()
mouseIsPressed : variable au même titre que width ou height

### Créer et utiliser des éléments html 
p5.js met à notre disposition des librairies supplémentaires qu’il est possible d’inclure dans nos sketches. C’est le cas de p5.dom.js.
DOM (Document Object Model) est une représentation des éléments html d’une page


### Interaction avec un serveur distant

#### Utiliser des données provenant d’un autre site

#### le format JSON:
JSON, pour Javascript Object Notation, est un format qui permet de définir des données structurées sous forme de paire clé-valeur :

```json
{
	"ville": "Verviers",
	"temp": 27.5    
}
```

#### la fonction `preload()`
Utilisée au même niveau que setup() ou draw(), la fonction preload est appelée par p5js avant ces deux dernière. elle permet notamment de s’assurer que les fichiers média (image ou vidéo) seront chargés avant le début de l’exécution du sketch. On pourra également utiliser la fonction pour charger des données provenant de serveurs distants

#### la fonction `loadJson(url, callback, [errorCallback])`
Cette fonction permet de récupérer le contenu d’un fichier json (local ou distant (via une url) et d’en manipuler le contenu via une fonction de **callback** <sup>[1](#callback)</sup>

<a name="callback">1</a> Une fonction de callback...
   
## Le texte dans p5.js

## Ressources et documentation
- MDN

   Le portail de documentation de la fondation Mozilla (qui édite le navigateur Firefox)  https://developer.mozilla.org/fr/docs/Web/JavaScript 
- Dan Shiffman

   Cofondateur de la Processing Foundation, professeur à l’Université de New-York (ITP), auteur de plusieurs ouvrages sur processing et d’une longue série de tutoriels vidéos :
	- youtube : https://www.youtube.com/user/shiffman 
	- kadenze: https://www.kadenze.com/courses/the-nature-of-code/info (avancé)
	- github : https://github.com/CodingTrain/Rainbow-Code 
	- shiffman.net : http://shiffman.net/ 

- P5js.org

   La documentation officielle est le meilleur endroit pour trouver des infos sur la manière d’utiliser la librairie
	- http://p5js.org/reference 

- **Divers**
	- http://www.lyceelecorbusier.eu/p5js/ : un cours complet sur p5js (en français, s’il vous plait!)
	- https://github.com/processing/p5.js/wiki/Education les différentes ressouces concernant l’apprentissage de p5.js sur le wiki de p5 lui-même.
	- Getting started with p5js : PDF (en anglais, sur demande)
	- https://github.com/processing/p5.js/wiki/JavaScript-basics : les bases de javascript (en anglais)

    
## Template p5.js

https://editor.p5js.org/drskullster/sketches/Nd6XcUk6X

## Exemples et inspiration

- <http://www.lyceelecorbusier.eu/p5js/?page_id=2861>
- <https://www.openprocessing.org>
- <http://gregberger.github.io/>
- Designing Generative Systems ([playlist youtube](https://www.youtube.com/playlist?list=PLyRZnpOSgMj3K8AV2I6UldnvTj6d_Zrf))

-- 

- https://editor.p5js.org/drskullster/sketches/2nDv6Mafo
- https://editor.p5js.org/drskullster/sketches/48gTEeqgj
        
    

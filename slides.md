---
# try also 'default' to start simple
theme: seriph
# random image from a curated Unsplash collection by Anthony
# like them? see https://unsplash.com/collections/94734566/slidev
background: https://source.unsplash.com/collection/94734566/1920x1080
# apply any windi css classes to the current slide
class: 'text-center'
# https://sli.dev/custom/highlighters.html
highlighter: shiki
# show line numbers in code blocks
lineNumbers: false
# some information about the slides, markdown enabled
info: |
  ## Slidev Starter Template
  Presentation slides for developers.

  Learn more at [Sli.dev](https://sli.dev)
# persist drawings in exports and build
drawings:
  persist: false
---
# Introduction CSS

CSS est le langage que nous utilisons pour styliser une page Web

---
# Qu’est-ce que CSS ?

- CSS signifie Cascading Style Sheets (feuilles de style en cascade)
- CSS décrit comment les éléments HTML doivent être affichés à l’écran, sur papier ou dans d’autres médias
- CSS permet d’économiser beaucoup de travail. Il peut contrôler la mise en page de plusieurs pages Web à la fois
- Les feuilles de style externes sont stockées dans des fichiers CSS

---
# Pourquoi utiliser CSS ?

CSS est utilisé pour définir des styles pour vos pages Web, y compris la conception, la mise en page et les variations d’affichage pour différents appareils et tailles d’écran.

```css
body {
  background-color: lightblue;
}

h1 {
  color: white;
  text-align: center;
}

p {
  font-family: verdana;
  font-size: 20px;
}
```

---
# Syntaxe CSS

Une règle CSS se compose d’un sélecteur et d’un bloc de déclaration.

<img src="/selector.gif" class="my-10 m-auto" />

- Le sélecteur pointe vers l’élément HTML que vous souhaitez styliser.
- Le bloc de déclaration contient une ou plusieurs déclarations séparées par des points-virgules.
- Chaque déclaration inclut un nom de propriété CSS et une valeur, séparés par deux points.
- Plusieurs déclarations CSS sont séparées par des points-virgules et les blocs de déclaration sont entourés d’accolades.

---
# Syntaxe CSS
## Exemple

Dans cet exemple, tous les `<p>` éléments seront alignés au centre, avec une couleur de texte rouge

```css
p {
  color: red;
  text-align: center;
}
```

- `p` est un sélecteur en CSS (il pointe vers l’élément HTML que vous souhaitez styliser : `<p>`).
- `color` est une propriété et est sa valeur est `red`
- `text-align` est une propriété et est sa valeur est `center`

---
# Sélecteurs CSS

## Un sélecteur CSS sélectionne le ou les éléments HTML que vous souhaitez styliser.

Les sélecteurs CSS sont utilisés pour « trouver » (ou sélectionner) les éléments HTML que vous souhaitez styliser.

Nous pouvons diviser les sélecteurs CSS en cinq catégories
- Sélecteurs simples (sélectionner des éléments en fonction du nom, de l’id, de la classe)
- Sélecteurs combinateurs (sélectionner des éléments en fonction d’une relation spécifique entre eux)
- Sélecteurs de pseudo-classe (sélectionner des éléments en fonction d’un certain état)
- Sélecteurs de pseudo-éléments (sélectionner et styliser une partie d’un élément)
- Sélecteurs d’attributs (sélectionner des éléments en fonction d’un attribut ou d’une valeur d’attribut)

---
# Sélecteurs simples - Sélecteur d’éléments CSS

Le sélecteur d’éléments sélectionne les éléments HTML en fonction du nom de l’élément.

### Exemple
Ici, tous les éléments `<p>`  de la page seront alignés au centre, avec une couleur de texte rouge:
```css
p {
  text-align: center;
  color: red;
}

h1 {
  text-align: center;
  color: green;
}
```
---
layout: two-cols

---
# Sélecteurs simples - Sélecteur d’ID CSS

Le sélecteur id utilise l’attribut id d’un élément HTML pour sélectionner un élément spécifique.

L’ID d’un élément est unique dans une page, de sorte que le sélecteur d’ID est utilisé pour sélectionner un élément unique !

Pour sélectionner un élément avec un ID spécifique, écrivez un caractère de hachage (#), suivi de l’ID de l’élément.

La règle CSS à droite sera appliquée à l’élément HTML avec id="para1 »:

::right::

<div class="mt-10"></div>

```html
<!DOCTYPE html>
<html>
  <head>
  <title>Sélecteur d’ID CSS</title>

    <style>

        #para1 {
          text-align: center;
          color: red;
        }

    </style>

  </head>
  <body>

    <p id="para1">Hello World!</p>

    <p>This paragraph is not affected by the style.</p>

  </body>

</html>

```
---
layout: two-cols

---
# Sélecteurs simples - Sélecteur de classe CSS

Le sélecteur de classe sélectionne les éléments HTML avec un attribut de classe spécifique.
- Pour sélectionner des éléments avec une classe spécifique, écrivez un caractère de point (.), suivi du nom de la classe.

>Dans cet exemple, tous les éléments HTML avec class="center" seront rouges et alignés au centre :

```css
.center {
  text-align: center;
  color: red;
}
```

::right::

<div class="mt-38"></div>

- Vous pouvez également spécifier que seuls des éléments HTML spécifiques doivent être affectés par une classe.

>Dans cet exemple, seuls les éléments  `<p>` avec class="center" seront rouges et alignés au centre :


```css
  p.center {
      text-align: center;
      color: red;
  }
```
---

# Sélecteurs simples - Le sélecteur universel

Le sélecteur universel (*) sélectionne tous les éléments HTML de la page.

### Exemple
La règle CSS ci-dessous affectera chaque élément HTML de la page :
```css
* {
  text-align: center;
  color: blue;
}
```
---
layout: two-cols

---
# Sélecteurs simples - Sélecteur de regroupement

Le sélecteur de regroupement sélectionne tous les éléments HTML avec les mêmes définitions de style.

Regardez le code CSS suivant (les éléments h1, h2 et p ont les mêmes définitions de style) :

```css
h1 {
  text-align: center;
  color: red;
}

h2 {
  text-align: center;
  color: red;
}

p {
  text-align: center;
  color: red;
}
```

::right::

<div class="mt-38"></div>

Il sera préférable de regrouper les sélecteurs, afin de minimiser le code.

Pour regrouper les sélecteurs, séparez chaque sélecteur par une virgule.

```css
h1, h2, p {
  text-align: center;
  color: red;
}
```

---
layout: two-cols

---
# Commentaires CSS
Les commentaires CSS ne sont pas affichés dans le navigateur, mais ils peuvent aider à documenter votre code source.

Les commentaires sont utilisés pour expliquer le code et peuvent vous aider lorsque vous modifiez le code source à une date ultérieure.
Les commentaires sont ignorés par les navigateurs.
Un commentaire CSS est placé à l’intérieur de l’élément `<style>`, et commence par `/*` et se termine par `*/`

::right::
```css
/* This is a single-line comment */
p {
  color: red;
}

p {
  color: red;  /* Set text color to red */
}

/* This is
a multi-line
comment */

p {
  color: red;
}
```

---
layout: two-cols

---
# Couleurs CSS
Les couleurs sont spécifiées à l’aide de noms de couleurs prédéfinis ou de valeurs RGB, HEX, HSL, RGBA, HSLA.

## Noms de couleur CSS
En CSS, une couleur peut être spécifiée à l’aide d’un nom de couleur prédéfini :

::right::
<div class="w3-row w3-center" style="margin:0 -16px;line-height:80px;color:white;">
  <div class="w3-col l3 m6 w3-padding">
    <div style="background-color:tomato;" >Tomate</div>
  </div>
  <div class="w3-col l3 m6 w3-padding">
    <div style="background-color:orange;">Orange</div>
  </div>
  <div class="w3-col l3 m6 w3-padding">
    <div style="background-color:dodgerblue;">DodgerBlue</div>
  </div>
  <div class="w3-col l3 m6 w3-padding">
    <div style="background-color:mediumseagreen;">MediumSeaGreen</div>
  </div>
  <div class="w3-col l3 m6 w3-padding">
    <div style="background-color:gray;" >Gris</div>
  </div>
  <div class="w3-col l3 m6 w3-padding">
    <div style="background-color:slateblue;">Ardoise Bleue</div>
  </div>
</div>

---

# Couleurs CSS RGB
Une valeur de couleur RGB représente les sources lumineuses ROUGE, VERT et BLEU.

## Valeur RGB
En CSS, une couleur peut être spécifiée en tant que valeur RGB, à l’aide de la formule suivante :

> `rgb(rouge, vert, bleu)`

Chaque paramètre (rouge, vert et bleu) définit l’intensité de la couleur entre 0 et 255.

Par exemple, `rgb(255, 0, 0)` est affiché en rouge, car le rouge est défini sur sa valeur la plus élevée (255) et les autres sur 0.

Pour afficher le noir, définissez tous les paramètres de couleur sur 0, comme suit : `rgb(0, 0, 0)`.

Pour afficher le blanc, définissez tous les paramètres de couleur sur 255, comme ceci: `rgb(255, 255, 255)`.

---

# Couleurs CSS RGB (Exemples)
Une valeur de couleur RGB représente les sources lumineuses ROUGE, VERT et BLEU.

<h2 style="background-color:rgb(255, 0, 0); text-align:center; height:4rem; color:white">rgb(255, 0, 0)</h2>
<h2 style="background-color:rgb(0, 0, 255); text-align:center; height:4rem; color:white">rgb(0, 0, 255)</h2>
<h2 style="background-color:rgb(60, 179, 113); text-align:center; height:4rem; color:white">rgb(60, 179, 113)</h2>
<h2 style="background-color:rgb(238, 130, 238); text-align:center; height:4rem; color:white">rgb(238, 130, 238)</h2>
<h2 style="background-color:rgb(255, 165, 0); text-align:center; height:4rem; color:white">rgb(255, 165, 0)</h2>
<h2 style="background-color:rgb(106, 90, 205); text-align:center; height:4rem; color:white">rgb(106, 90, 205)</h2>

---

# Couleurs CSS RGB (Exemples)
Les nuances de gris sont souvent définies en utilisant des valeurs égales pour les 3 sources lumineuses :

<h2 style="background-color:rgb(60, 60, 60); text-align:center; height:4rem; color:white;">rgb(60, 60, 60)</h2>
<h2 style="background-color:rgb(90, 90, 90); text-align:center; height:4rem; color:white;">rgb(90, 90, 90)</h2>
<h2 style="background-color:rgb(120, 120, 120); text-align:center; height:4rem; color:white;">rgb(120, 120, 120)</h2>
<h2 style="background-color:rgb(180, 180, 180); text-align:center; height:4rem; color:white;">rgb(180, 180, 180)</h2>
<h2 style="background-color:rgb(210, 210, 210); text-align:center; height:4rem; color:white;">rgb(210, 210, 210)</h2>
<h2 style="background-color:rgb(240, 240, 240); text-align:center; height:4rem; color:white;">rgb(240, 240, 240)</h2>

---

# Valeur RGBA
Les valeurs de couleur RGBA sont une extension des valeurs de couleur RGB avec une couche alpha - qui spécifie l’opacité d’une couleur.

Une valeur de couleur RGBA est spécifiée avec : > `rgba(rouge, vert, bleu, alpha)`

Le paramètre alpha est un nombre compris entre 0,0 (entièrement transparent) et 1,0 (opaque) :

<h2 style="background-color:rgba(255, 99, 71, 0); text-align:center; height:3rem; color:black;">rgba(255, 99, 71, 0)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.2); text-align:center; height:3rem; color:black;">rgba(255, 99, 71, 0.2)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.4); text-align:center; height:3rem; color:black;">rgba(255, 99, 71, 0.4)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.6); text-align:center; height:3rem; color:black;">rgba(255, 99, 71, 0.6)</h2>
<h2 style="background-color:rgba(255, 99, 71, 0.8); text-align:center; height:3rem; color:black;">rgba(255, 99, 71, 0.8)</h2>
<h2 style="background-color:rgba(255, 99, 71, 1); text-align:center; height:3rem; color:black;">rgba(255, 99, 71, 1)</h2>


---

# Couleurs CSS HEX
En CSS, une couleur peut être spécifiée à l’aide d’une valeur hexadécimale sous la forme : #rrggbb

## Valeur HEX

`rr (rouge)`, `gg (vert)` et `bb (bleu)` sont des valeurs hexadécimales comprises entre 00 et ff (identiques à la décimale 0-255).

Par exemple,
- `#ff0000` est affiché en rouge, car le rouge est défini sur sa valeur la plus élevée `(ff)` et les autres sur la valeur la plus basse `(00)`.
- Pour afficher le noir, définissez toutes les valeurs sur `00`, comme ceci : `#000000`.
- Pour afficher le blanc, définissez toutes les valeurs sur `ff`, comme ceci : `#ffffff`.

---
layout: two-cols

---
# Couleurs CSS HEX (Exemples)


<h2 style="background-color:#ff0000; text-align:center; height:3rem; color:black;">#ff0000</h2>
<h2 style="background-color:#0000ff; text-align:center; height:3rem; color:black;">#0000ff</h2>
<h2 style="background-color:#3cb371; text-align:center; height:3rem; color:black;">#3cb371</h2>
<h2 style="background-color:#ee82ee; text-align:center; height:3rem; color:black;">#ee82ee</h2>
<h2 style="background-color:#ffa500; text-align:center; height:3rem; color:black;">#ffa500</h2>
<h2 style="background-color:#6a5acd; text-align:center; height:3rem; color:black;">#6a5acd</h2>

::right::
<br><br>
<h2 style="background-color:#3c3c3c; text-align:center; height:3rem; color:black;">#3c3c3c</h2>
<h2 style="background-color:#616161; text-align:center; height:3rem; color:black;">#616161</h2>
<h2 style="background-color:#787878; text-align:center; height:3rem; color:black;">#787878</h2>
<h2 style="background-color:#b4b4b4; text-align:center; height:3rem; color:black;">#b4b4b4</h2>
<h2 style="background-color:#f0f0f0; text-align:center; height:3rem; color:black;">#f0f0f0</h2>
<h2 style="background-color:#f9f9f9; text-align:center; height:3rem; color:black;">#f9f9f9</h2>

---
layout: two-cols

---
# Valeur HEXadécimale à 3 chiffres
Le code hexadécimal à 3 chiffres est un raccourci pour certains codes hexadécimaux à 6 chiffres.

Le code hexadécimal à 3 chiffres se présente sous la forme suivante : `#rvb`

où `r, g et b` représente les composants rouge, vert et bleu avec des valeurs comprises entre 0 et f.

Le code hexadécimal à 3 chiffres ne peut être utilisé que lorsque les deux valeurs (RR, GG et BB) sont les mêmes pour chaque composant.

Donc, si nous avons `#ff00cc`, cela peut être écrit comme ceci: `#f0c`.

::right::
<br> <br>
Exemple :

```css
  body {
    background-color: #fc9; /* same as #ffcc99 */
  }

  h1 {
    color: #f0f; /* same as #ff00ff */
  }

  p {
    color: #b58; /* same as #bb5588 */
  }
```
---
layout: image-right
image: https://source.unsplash.com/collection/94734566/1920x1080

---
# Arrière-plans CSS
Les propriétés d’arrière-plan CSS sont utilisées pour ajouter des effets d’arrière-plan pour les éléments HTML.

Dans ce chapitre, nous allons découvrir les propriétés d’arrière-plan CSS suivantes :

- background-color
- background-image
- background-repeat
- background-attachment
- background-position
- background (propriété abrégée)

::right::
- background-color
- background-image
- background-repeat
- background-attachment
- background-position
- background (propriété abrégée)

---
layout: two-cols

---
# Couleur d’arrière-plan CSS
La propriété `background-color` spécifie la couleur d’arrière-plan d’un élément.

une couleur est le plus souvent spécifiée par :

- un nom de couleur valide - comme `red`
- une valeur HEX - comme `#ff0000`
- une valeur RGB - comme `rgb(255,0,0)`

**Exemple :**

```css
body {
  background-color: lightblue;
}
```

::right::
<br> <br>
### Ici, les éléments `<h1>, <p> et <div>` auront des couleurs d’arrière-plan différentes :

```css
  h1 {
    background-color: green;
  }

  div {
    background-color: lightblue;
  }

  p {
    background-color: yellow;
  }
```
---
layout: two-cols

---
# Opacité / Transparence
<br />
La propriété `opacity` spécifie l’opacité/transparence d’un élément.
Il peut prendre une valeur de 0,0 à 1,0. Plus la valeur est faible, plus elle est transparente:

**Exemple :**

<div class="grid grid-cols-2">
  <div style="background-color:#4CAF50;opacity:1;padding:50px;color:black"><p _msthash="608907" _msttexthash="127374">opacité 1</p></div>
  <div style="background-color:#4CAF50;opacity:0.6;padding:50px;color:black"><p _msthash="609180" _msttexthash="147004">opacité 0,6</p></div>
  <div style="background-color:#4CAF50;opacity:0.3;padding:50px;color:black"><p _msthash="609453" _msttexthash="146380">opacité 0,3</p></div>
  <div style="background-color:#4CAF50;opacity:0.1;padding:50px;color:black"><p _msthash="609726" _msttexthash="145964">opacité 0,1</p></div>
</div>


::right::
<br> <br>

```css
  div {
  background-color: green;
  opacity: 0.3;
}
```

<br>

> Note: Lorsque vous utilisez la propriété `opacity` pour ajouter de la transparence à l’arrière-plan d’un élément, tous ses éléments enfants héritent de la même transparence.


> Cela peut rendre le texte à l’intérieur d’un élément entièrement transparent difficile à lire.
---
layout: two-cols

---
# Transparence à l’aide de RGBA
<br >

Si vous ne souhaitez pas appliquer d’opacité aux éléments enfants, utilisez des valeurs de couleur RGBA.

L’exemple suivant définit l’opacité de la couleur d’arrière-plan et non du texte :

```css
div {
  /* Green background with 30% opacity */
  background: rgba(0, 128, 0, 0.3)
}
```

<div class="grid grid-cols-4">
<div style="background:rgb(76, 175, 80);padding:20px;color:black"><p _msthash="611455" _msttexthash="183729">100% opacité</p></div>
<div style="background:rgba(76, 175, 80,0.6);padding:20px;color:black"><p _msthash="611728" _msttexthash="1377467">60 % d’opacité</p></div>
<div style="background:rgba(76, 175, 80,0.3);padding:20px;color:black"><p _msthash="612001" _msttexthash="1377194">30 % d’opacité</p></div>
<div style="background:rgba(76, 175, 80,0.1);padding:20px;color:black"><p _msthash="612274" _msttexthash="1377012">10 % d’opacité</p></div>
</div>


::right::
<br> <br>
<br> <br>
Nous avons appris de notre chapitre couleurs CSS que nous pouvons utiliser RGB comme valeur de couleur.

En plus de RGB, nous pouvons utiliser une valeur de couleur RGB avec une couche alpha (RGBA) - qui spécifie l’opacité d’une couleur.

> Une valeur de couleur RGBA est spécifiée avec : rgba(rouge, vert, bleu, alpha).
>>> Le paramètre alpha est un nombre compris entre 0,0 (entièrement transparent) et 1,0 (entièrement opaque).
---
layout: two-cols

---
# Image d’arrière-plan CSS
La propriété `background-image` spécifie une image à utiliser comme arrière-plan d’un élément.

Par défaut, l’image est répétée afin de couvrir l’ensemble de l’élément.

**Exemple :**

Image d’arrière-plan pour une page :

```css
body {
  background-image: url("paper.gif");
}
```

> Note: <br>
> Lorsque vous utilisez une image d’arrière-plan, utilisez une image qui ne perturbe pas le texte.

::right::
<br> <br>
### L’image d’arrière-plan peut également être définie pour des éléments spécifiques, tels que l’élément `<p>`:

```css
  p {
    background-image: url("paper.gif");
  }
```

---
layout: two-cols

---
# Répétition de l’image d’arrière-plan
Par défaut, la propriété `background-image` répète une image horizontalement et verticalement.

Par défaut, l’image est répétée afin de couvrir l’ensemble de l’élément.

**Exemple :**

```css
body {
  background-image: url("gradient_bg.png");
  background-repeat: repeat-x;
}
```

> Pour répéter une image verticalement, définissez `background-repeat: repeat-y`;


::right::
<br> <br>
## background-repeat: no-repeat

L’affichage de l’image d’arrière-plan une seule fois est également spécifié par la propriété `background-repeat`

```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
}
```
---
layout: two-cols

---
# CSS Background Attachment
La propriété `background-attachment` spécifie si l’image d’arrière-plan doit défiler ou rester fixe (ne défilera pas avec le reste de la page)

**Exemple :**

```css
body {
  background-image: url("img_tree.png");
  background-repeat: no-repeat;
  background-attachment: fixed;
}
```

::right::
<br> <br>
### Exemple
Pour spécifier que l’image d’arrière-plan doit défiler avec le reste de la page

```css
  body {
    background-image: url("img_tree.png");
    background-repeat: no-repeat;
    background-position: right top;
    background-attachment: scroll;
  }
```

---
layout: two-cols

---
# Bordures CSS
Les propriétés de bordure CSS permettent de spécifier le style, la largeur et la couleur de la bordure d’un élément.

## Style de bordure CSS
La propriété `border-style` spécifie le type de bordure à afficher.

Les valeurs suivantes sont autorisées :

- dotted - Définit une bordure pointillée
- dashed - Définit une bordure pointillée
- solid - Définit une bordure solide
- double - Définit une double bordure
- none - Ne définit aucune frontière
- hidden - Définit une bordure cachée

::right::
- groove, ridge, inset, outset : Définissent une bordure 3D. L’effet dépend de la valeur de couleur de bordure

La propriété `border-style` peut avoir de une à quatre valeurs (pour la bordure supérieure, la bordure droite, la bordure inférieure et la bordure gauche).

**Exemple :**

```css
.dotted {border-style: dotted;}
.dashed {border-style: dashed;}
.solid {border-style: solid;}
.double {border-style: double;}
.groove {border-style: groove;}
.ridge {border-style: ridge;}
.inset {border-style: inset;}
.outset {border-style: outset;}
.none {border-style: none;}
.hidden {border-style: hidden;}
.mix {border-style: dotted dashed solid double;}
```

---
layout: two-cols

---
# Largeur de bordure CSS
La propriété `border-width` spécifie la largeur des quatre bordures.

La largeur peut être définie comme une taille spécifique (en px, em, etc.) ou en utilisant l’une des trois valeurs prédéfinies :
thin (mince), medium (moyenne), or thick (épaisse).

<div class="w3-white w3-padding notranslate">
<div style="border:5px solid;padding:8px;margin-top:8px;margin-bottom:16px">5px border-width</div>
<div style="border:medium solid;padding:8px;margin-top:8px;margin-bottom:16px">medium border-width</div>
<div style="border:2px dotted;padding:8px;margin-top:8px;margin-bottom:16px">2px border-width</div>
<div style="border:thick dotted;padding:8px;margin-top:8px;margin-bottom:8px">thick border-width</div>

</div>

::right::

## Exemple
```css
p.one {
  border-style: solid;
  border-width: 5px;
}
p.two {
  border-style: solid;
  border-width: medium;
}
p.three {
  border-style: dotted;
  border-width: 2px;
}
p.four {
  border-style: dotted;
  border-width: thick;
}
```
---
layout: two-cols

---
# Largeurs latérales spécifiques
La propriété `border-width` peut avoir de une à quatre valeurs (pour la bordure supérieure, la bordure droite, la bordure inférieure et la bordure gauche) :

## Exemple

```css
p.one {
  border-style: solid;
  border-width: 5px 20px; /* 5px top and bottom, 20px on the sides */
}
p.two {
  border-style: solid;
  border-width: 20px 5px; /* 20px top and bottom, 5px on the sides */
}
p.three {
  border-style: solid;
  border-width: 25px 10px 4px 35px; /* 25px top, 10px right, 4px bottom and 35px left */
}
```
::right::

<p style="border-style: solid; border-width: 5px 20px;  border-color: red;">Some text.</p>
<p style="border-style: solid; border-width: 20px 5px; border-color: red;">Some text.</p>
<p style="border-style: solid; border-width: 25px 10px 4px 35px; border-color: red;">Some text.</p>
---
layout: two-cols

---
# Couleur de bordure CSS
La propriété `border-color` est utilisée pour définir la couleur des quatre bordures.

La couleur peut être définie par:
- name - spécifiez un nom de couleur, comme: red
- HEX - spécifiez une valeur HEX, comme: #ff0000
- RVB - spécifiez une valeur RVB, comme:nrgb(255,0,0)
- HSL - spécifiez une valeur HSL, comme: hsl(0, 100%, 50%)
- transparent


::right::
## Exemple
Démonstration des différentes couleurs de bordure :
```css
p.one {
  border-style: solid;
  border-color: red;
}
p.two {
  border-style: solid;
  border-color: green;
}
p.three {
  border-style: dotted;
  border-color: blue;
}
```
<div style="border-style: solid;border-color: red;padding:8px;margin-top:8px;margin-bottom:16px; border-width:4px;">Red border</div>
<div style="border-style: solid;border-color: green;padding:8px;margin-top:8px;margin-bottom:16px; border-width:4px;">Green border</div>
<div style="border-style: dotted;border-color: blue;padding:8px;margin-top:8px;margin-bottom:8px; border-width:4px;">Blue border</div>

---
layout: two-cols

---
# Bordure CSS
Alors, voici comment cela fonctionne:

Si la propriété `border-style`a quatre valeurs :

> `border-style: dotted solid double dashed;`
- la bordure supérieure est pointillée
- la bordure droite est solide
- la bordure inférieure est double
- la bordure gauche est pointillée

Si la propriété a trois valeurs :border-style

> `border-style: dotted solid double;`
- la bordure supérieure est pointillée
- les bordures droite et gauche sont solides
- la bordure inférieure est double

::right::

Si la propriété a deux valeurs :border-style
> `border-style: dotted solid;`
- les bordures supérieure et inférieure sont pointillées
- les bordures droite et gauche sont solides

Si la propriété a une valeur :border-style
> `border-style: dotted;`
- les quatre bordures sont en pointillés

---
layout: two-cols

---
# Bordure CSS - propriété abregée
Comme vous l’avez vu dans la page précédente, il existe de nombreuses propriétés à prendre en compte lorsqu’il s’agit des bordures.
Pour raccourcir le code, il est également possible de spécifier toutes les propriétés de bordure individuelles dans une seul epropriété.
La propriété `border` est une propriété abrégée pour les propriétés de bordure individuelles suivantes :

### Exemple
```css
p {
  border: 5px solid red;
}
```
<p style="border:5px solid red;padding:2px">Some text</p>

::right::

### Bordure gauche
```css
p {
  border-left: 6px solid red;
}
```
<p style="border-left:6px solid red;padding:5px 5px;">Some text</p>

### Bordure inférieure
```css
p {
  border-bottom: 6px solid red;
}
```
<p style="border-bottom:6px solid red;padding:5px 5px;">Some text</p>
---
layout: two-cols

---
# Bordures arrondies CSS
La propriété `border-radius` permet d’ajouter des bordures arrondies à un élément :


### Exemple
```css
.p1 {
  border: 2px solid red;
}
.p2 {
  border: 2px solid red;
  border-radius: 5px;
}
.p3 {
  border: 2px solid red;
  border-radius: 8px;
}
.p4 {
  border: 2px solid red;
  border-radius: 12px;
}
```

::right::

<p style="border: 2px solid red;padding:5px;">Bordure normale</p>
<p style="border: 2px solid red;border-radius: 5px;padding:5px;">Bordure ronde</p>
<p style="border: 2px solid red;border-radius: 8px;padding:5px;">Bordure plus arrondie</p>
<p style="border: 2px solid red;border-radius: 12px;padding:5px;">Bordure la plus arrondie</p>
---
layout: two-cols

---
# Marges CSS
Les marges sont utilisées pour créer de l’espace autour des éléments, en dehors des bordures définies.

Les propriétés CSS `margin` sont utilisées pour créer de l’espace autour des éléments, en dehors des bordures définies.

Avec CSS `margin`, nous avons un contrôle total sur les marges.

Il existe des propriétés permettant de définir la marge de chaque côté d’un élément (haut, droite, bas et gauche).
```css
p {
  margin-top: 100px;
  margin-bottom: 100px;
  margin-right: 150px;
  margin-left: 80px;
}
```

::right::

## Marge - Côtés individuels
CSS possède des propriétés permettant de spécifier la marge de chaque côté d’un élément :
```css
margin-top
margin-right
margin-bottom
margin-left
```
Toutes les propriétés de marge peuvent avoir les valeurs suivantes :

- auto : le navigateur calcule la marge
- valeur : spécifie une marge en px, pt, cm, etc.
- % : spécifie une marge en % de la largeur de l’élément contenant
- inherit : spécifie que la marge doit être héritée de l’élément parent

> NB: Les valeurs négatives sont autorisées.
---
layout: two-cols

---
# Propriété abregée
Pour raccourcir le code, il est possible de spécifier toutes les propriétés de marge dans une propriété.

La propriété `margin` est une propriété abrégée pour les propriétés de marge individuelles suivantes :

```css
p {
  margin: 25px 50px 75px 100px;
}
```

::right::
# La valeur automatique
Vous pouvez définir la propriété margin pour centrer horizontalement l’élément dans son conteneur.auto

L’élément occupera alors la largeur spécifiée et l’espace restant sera réparti également entre les marges gauche et droite.
```css
div {
  width: 300px;
  margin: auto;
  border: 1px solid red;
}
```
---
layout: two-cols

---
# La valeur héritée
<br>

Cet exemple montre comment hériter la marge gauche de l’élément `<p class="ex1">` de l’élément parent (`<div>`) :
::right::
```html
<div>
  <p class="ex1">
    Texte
  </p>
</div>
```

```css
div {
  border: 1px solid red;
  margin-left: 100px;
}

p.ex1 {
  margin-left: inherit;
}
```
---
layout: two-cols

---
# Réduction de la marge CSS
<br>

Parfois, deux marges s’effondrent en une seule marge.

Les marges supérieure et inférieure des éléments sont parfois réduites en une seule marge égale à la plus grande des deux marges.

Cela ne se produit pas sur les marges gauche et droite! Seulement les marges supérieures et inférieures!

<h1 style="margin: 0 0 50px 0;">Heading 1</h1>
<h2 style="margin: 20px 0 0 0;">Heading 2</h2>

::right::

Regardez l’exemple suivant :

```html
<h1>Heading 1</h1>
<h2>Heading 2</h2>
```

```css
h1 {
  margin: 0 0 50px 0;
}

h2 {
  margin: 20px 0 0 0;
}
```
---
layout: two-cols

---
# CSS Padding
Les propriétés CSS `padding` sont utilisées pour générer de l’espace autour du contenu d’un élément, à l’intérieur des bordures définies.

CSS padding possède des propriétés permettant de spécifier le padding pour chaque côté d’un élément :

- padding-top
- padding-right
- padding-bottom
- padding-left

::right::


Toutes les propriétés de padding peuvent avoir les valeurs suivantes :

- longueur: spécifie un rembourrage en px, pt, cm, etc.
- %: spécifie un rembourrage en % de la largeur de l’élément contenant
- inherit: spécifie que le remplissage doit être hérité de l’élément parent
> Note: Les valeurs négatives ne sont pas autorisées.
---
layout: two-cols

---
# Padding et largeur de l’élément
La propriété CSS `width` spécifie la largeur de la zone de contenu de l’élément.

La zone de contenu est la partie à l’intérieur du padding, de la bordure et de la marge d’un élément (Box model).

Ainsi, si un élément a une largeur spécifiée, le padding ajouté à cet élément sera ajouté à la largeur totale de l’élément.
> C’est souvent un résultat indésirable.

```css
div {
  width: 300px;
  padding: 25px;
  box-sizing: border-box;
}
````

::right::
# Exemple
<br>

```css
div {
  width: 300px;
  padding: 25px;
}
```
Ici, l’élément `<div>` a une largeur de `300px`. Cependant, la largeur réelle de l’élément `<div>` sera de `350px`

> `(300px + 25px de padding gauche + 25px de padding droit)`


Pour maintenir la largeur à 300px, quelle que soit le padding, on utilise la propriété `box-sizing`.

Cela permet à l’élément de conserver sa largeur réelle meme si on augmente le padding, l’espace de contenu disponible diminuera.




---
layout: two-cols
---
# Hauteur, Largeur et Largeur maximale
<br>

Les propriétés `height` et `width` sont utilisés pour définir la hauteur et la largeur d’un élément.

La propriété `max-width` permet de définir la largeur maximale d’un élément.

> Les propriétés de hauteur et de largeur n’incluent pas le padding, les bordures ou les marges.

Elles définissent la hauteur/largeur de la zone à l’intérieur du padding, de la bordure et de la marge de l’élément.

::right::
# Valeurs css de hauteur et de largeur
<br>

Les propriétés et peuvent avoir les valeurs suivantes :

- auto: Il s’agit de la valeur par défaut. Le navigateur calcule la hauteur et la largeur
- valeur: Définit la hauteur/largeur en px, em etc.
- %: Définit la hauteur/largeur en pourcentage du bloc contenant
- initial: Définit la hauteur/largeur sur sa valeur par défaut
- inherit: La hauteur/largeur sera héritée de sa valeur parente
---
layout: two-cols
---
# Exemple
```css
div {
  height: 100px;
  width: 50%;
  background-color: powderblue;
}
```

<div style="width:50%;height:100px;padding:10px;background-color:powderblue;color:black;">
 Cet élément a une hauteur de 100 pixels et une largeur de 50%
</div>

# Définition de la largeur maximale
La propriété `max-width` permet de définir la largeur maximale d’un élément.
::right::



Le `max-width` peut être spécifié dans des valeurs de longueur, telles que px, cm, etc., ou en pourcentage (%) du bloc contenant, ou défini sur `none` valeur par défaut. (Signifie qu’il n’y a pas de largeur maximale).

Le problème avec ce qui précède se produit lorsque la fenêtre du navigateur est plus petite que la largeur de l’élément `<div>` (500px). Le navigateur ajoute ensuite une barre de défilement horizontale à la page.

L’utilisation `max-width` à la place , dans cette situation, améliorera la gestion des petites fenêtres par le navigateur.

<div style="padding:10px;background-color:powderblue;color:black;height:100px; max-width:500px;">
‎Cet élément a une hauteur de 100 pixels et une largeur maximale de 500 pixels.‎</div>

---
layout: two-cols
---
# CSS Box Model
Tous les éléments HTML peuvent être considérés comme des boîtes.

En CSS, le terme « Box model » est utilisé lorsqu’on parle de conception et de mise en page.

Le box model est essentiellement une boîte qui entoure chaque élément HTML.

Il se compose de: marges, bordures, padding  et le contenu réel.

::right::
![alt text](box-model.png "Title")
---
layout: two-cols
---
# Largeur et hauteur d’un élément

Afin de définir correctement la largeur et la hauteur d’un élément dans tous les navigateurs, vous devez savoir comment fonctionne le box model.
> **Important**: Lorsqu'on definit les propriétés `width` et `height` d’un élément avec CSS, cela **definit la largeur et la hauteur de la zone de contenu**.
> Pour calculer la taille réelle d’un élément, on doit également ajouter le padding, les bordures et les marges.


Cet élément `<div>` aura une largeur totale de **350px** :

```css
div {
  width: 320px;
  padding: 10px;
  border: 5px solid gray;
  margin: 0;
}
```
::right::
Voici le calcul :
> - 320px (largeur)
> - +20px (padding gauche + droite)
> - +10px (bordure gauche + droite)
> - +0px (marge gauche + droite)
> - =350px

- La largeur totale d’un élément doit être calculée comme suit :

> Largeur totale de l’élément = largeur + padding gauche + padding droit + bordure gauche + bordure droite + marge gauche + marge droite

- La hauteur totale d’un élément doit être calculée comme suit :
> Hauteur totale de l’élément = hauteur + padding supérieur + padding inférieur + bordure supérieure + bordure inférieure + marge supérieure + marge inférieure

---
layout: two-cols
---
::right::

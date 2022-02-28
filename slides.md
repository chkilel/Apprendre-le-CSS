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

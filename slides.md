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

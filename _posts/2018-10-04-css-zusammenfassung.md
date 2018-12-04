---
layout: post
title: "CSS Cheatsheet"
comments: true
description: "CSS zusammenfassung"
keywords: "CSS, wt"
---

# CSS

## Structure

```css
/* this is a comment */
selector {
  property: value;
}
```

## using stylesheets

- Extern .css file

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
    <!-- including in head -->
    <link rel="stylesheet" href="style.css">
    <!-- more detail -->
    <link href="style.css" rel="stylesheet" type="text/css">
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>
```

- intern style

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
    <style>
      h1 {
        color: blue;
        background-color: yellow;
        border: 1px solid black;
      }

      p {
        color: red;
      }
    </style>
  </head>
  <body>
    <h1>Hello World!</h1>
    <p>This is my first CSS example</p>
  </body>
</html>
```

- with style atribute
  - [**style=""**] used to apply style to element

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8">
    <title>My CSS experiment</title>
  </head>
  <body>
    <h1 style="color: blue;background-color: yellow;border: 1px solid black;">Hello World!</h1>
    <p style="color:red;">This is my first CSS example</p>
  </body>
</html>
```

## @-rules

```css
/* this is a comment */
@import "custom.css";
```

```css
@media (min-width: 801px) {
  body {
    margin: 0 auto;
    width: 800px;
  }
}
```

## short

```css
background: red url(bg-graphic.png) 10px 10px repeat-x fixed;

/*is the same as*/
background-color: red;
background-image: url(bg-graphic.png);
background-position: 10px 10px;
background-repeat: repeat-x;
background-scroll: fixed;
```

## selectors

- selector list: `A, B` => A and or B
- descendant combinator `A B` => any B that is in A **or in somthing** that is in a A
- child combinator: `A > B` => any B that is a direct child of A
- Adjacent sibling combinator `A + B`: any B that folows a A
- General sibling combinator `A ~ B`: any B that is preceded by a A

  [->Example](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Combinators_and_multiple_selectors#Combinators_example)

### element selectors

```css
p {
  color: red;
}

div {
  color: blue;
}
```

***

### class selectors

```html
<ul>
  <li class="first done">Create an HTML document</li>
  <li class="second done">Create a CSS style sheet</li>
  <li class="third">Link them all together</li>
</ul>
```

```css
.first {
  font-weight: bold;
}

.done {
  text-decoration: line-through;
}
```

***

### id selectors

```html
<p id="polite"> — "Good morning."</p>
<p id="rude"> — "Go away!"</p>
```

```css
#polite {
  font-family: cursive;
}

#rude {
  font-family: monospace;
  text-transform: uppercase;
}
```

***

### universal selector `*`

```html
<div>
  <p>
    I think the containing box just needed
    a <strong>border</strong> or <em>something</em>,
    but this is getting <strong>out of hand</strong>!
  </p>
</div>
```

```css
* {
  padding: 5px;
  border: 1px solid black;
  background: rgba(255,0,0,0.25);
}
```

***

### [attribute selectors](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Attribute_selectors)

```html
Ingredients for my recipe: <i lang="fr-FR">Poulet basquaise</i>
<ul>
  <li data-quantity="1kg" data-vegetable>Tomatoes</li>
  <li data-quantity="3" data-vegetable>Onions</li>
  <li data-quantity="3" data-vegetable>Garlic</li>
  <li data-quantity="700g" data-vegetable="not spicy like chili">Red pepper</li>
  <li data-quantity="2kg" data-meat>Chicken</li>
  <li data-quantity="optional 150g" data-meat>Bacon bits</li>
  <li data-quantity="optional 10ml" data-vegetable="liquid">Olive oil</li>
  <li data-quantity="25cl" data-vegetable="liquid">White wine</li>
</ul>
```

```css
/* All elements with the attribute "data-vegetable"
   are given green text */
[data-vegetable] {
  color: green;
}

/* All elements with the attribute "data-vegetable"
   with the exact value "liquid" are given a golden
   background color */
[data-vegetable="liquid"] {
  background-color: goldenrod;
}

/* All elements with the attribute "data-vegetable",
   containing the value "spicy", even among others,
   are given a red text color */
[data-vegetable~="spicy"] {
  color: red;
}
```

_Extra:_

```css
/* Classic usage for language selection */
[lang|="fr"] {
  font-weight: bold;
}

/* All elements with the attribute "data-quantity", for which
   the value starts with "optional" */
[data-quantity^="optional"] {
  opacity: 0.5;
}

/* All elements with the attribute "data-quantity", for which
   the value ends with "kg" */
[data-quantity$="kg"] {
  font-weight: bold;
}

/* All elements with the attribute "data-vegetable" containing
   the substring "not spicy" are turned back to green */
[data-vegetable*="not spicy"] {
  color: green;
}
```

- [attr] -> select **attribute**
- [attr=val] -> select attribute **where val**
- [attr~=val] -> select all where attr and value **contains** val
- [attr^=val] -> select all where attr and value **starts with** val
- [attr$=val] -> select all where attr and value **ends with** val
- [attr*=val] -> select all where attr and value is **substring** val

***

## [Pseudo classes](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Pseudo-classes_and_pseudo-elements#Pseudo-classes)

- preceded by a colon (`:`)
- to style element only in certain state (:hover, :active, :visited, ...)
- `:hover` -> mouse, `:active` -> keyboard

```html
<a href="https://developer.mozilla.org/"
   target="_blank">
   Mozilla Developer Network
</a>
```

```css
/* These styles will style our link
   in all states */
a {
  color: blue;
  font-weight: bold;
}

/* We want visited links to be the same color
   as non visited links */
a:visited {
  color: blue;
}

/* We highlight the link when it is
   hovered (mouse), activated
   or focused (keyboard) */
a:hover,
a:active,
a:focus {
  color: darkred;
  text-decoration: none;
}
```

## [psudo elements](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Pseudo-classes_and_pseudo-elements#Pseudo-elements)

- precended by two columns (`::`)
- to select certain part of element (`::before`, `::after`, `::first-line`, `::first-letter`, ...)

```html
<ul>
  <li><a href="https://developer.mozilla.org/en-US/docs/Glossary/CSS">CSS</a> defined in the MDN glossary.</li>
  <li><a href="https://developer.mozilla.org/en-US/docs/Glossary/HTML">HTML</a> defined in the MDN glossary.</li>
</ul>
```

```css
/* All elements with an attribute "href" with values
   starting with "http" will have an arrow added after their
   content (to indicate they are external links) */
[href^=http]::after {
  content: '⤴';
}
```

### values and units

- absolute units: `px`, `q`, `mm`, `cm`, `in`
- relative units: `em` -> 1em == font-size of current element
- 0 is unitless
- line-height: 1.5 -> unitless

#### [percentages](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Values_and_units#Percentages)

- used to set a value relative to parent

```html
<div>
  <div class="boxes">Fixed width layout with pixels</div>
  <div class="boxes">Liquid layout with percentages</div>
</div>>
```

```css
div .boxes {
  margin: 10px;
  font-size: 200%;
  color: white;
  height: 150px;
  border: 2px solid black;
}

.boxes:nth-child(1) {
  background-color: red;
  width: 650px;
}

.boxes:nth-child(2) {
  background-color: blue;
  width: 75%;
}
```

## colors

### Keywords

- `red`, `blue`, `black` -> [full list](https://developer.mozilla.org/en-US/docs/Web/CSS/color_value#Color_keywords)

### hex values

- `#` symbol + 6 hex nums (0 - f) `#RRGGBB` => #ff0000 == `red`, #0000ff == `blue`, #00ff00 == `green`

### RGB

- is a function `rgb(x, x, x)` x is between 0 and 255

## specifity

  elemnt < id < type
1. id
2. class
3. element

- **note: you can use !important to win over higher selector**

## box model

<img src="https://mdn.mozillademos.org/files/13647/box-model-standard-small.png"
     width="200px" height="200px">

- properties:
  - **width:** and **heigth** -> content
  - **padding:** -> between content and border
  - **border:** -> between padding and margin
  - **margin:** -> between outside and border

- [**overflow:**](https://developer.mozilla.org/en-US/docs/Web/CSS/overflow)
  - `vivible;` `hidden;`, `scroll`, `auto`

- [**background-clip:**](https://developer.mozilla.org/en-US/docs/Learn/CSS/Introduction_to_CSS/Box_model#Background_clip)
  - `border-box;`, `padding-box;`, `content-box;`

### **display:**

- **block;** -> stacked boxes
- **inline;** -> flows with document text
- **inline-block;** -> flows with text but can be sized
- **flex;** -> makes all childs flex items

## styling

### fonts

```css
p {
  font-family: Helvetica, "Trebuchet MS", Verdana, sans-serif;
}
```

- **text-decoration:...;** (unerline, overline, line-trough, blink)

#### Web fonts

1.define where to download

  ```css
  @font-face {
    font-family: "myFont";
    src: url("myFont.ttf");
  }
  ```

2.use

  ```css
  html {
    font-family: "myFont", "Bitstream Vera Serif", serif;
  }
  ```

### lists

- `list-style-type: upper-roman;` (upper-roman, lower-roman, lower-aplha, upper-aplha, disc, decimal)
- `list-style-position: inside;`

### background

```css
background-image: url(myimage.png);
background-size: 16px 16px;
background-color: yellow;
background-repeat: no-repeat;
```

### borders

- `border-style:...;` (solid, dashed, dotted)
- `border-radius:...px;`

### animations

```css
.animated {
    width: 100px;
    height: 100px;
    position: relative;
    background-color: red;
    animation-name: example;
    animation-duration: 2s;
    animation-iteration-count: infinite;
}
@keyframes example {
    0%   {background-color: red; left:0px;}
    50%  {background-color: yellow; left:200px;}
    100% {background-color: red; left:0px;}
}
```
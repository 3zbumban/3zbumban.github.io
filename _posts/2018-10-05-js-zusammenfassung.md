---
layout: post
title: "JS Cheatsheet"
comments: true
description: "js zusammenfassung"
keywords: "js, wt"
---

# JS

## usage

in html:

```html
<script>
  // comment
  console.log("Hallo!");
  /*
  *
  * multiline comment
  */
</script>
```

in external file:

```html
<script src="path/to/file.js"></script>
```

## data types

- boolean: `true`, `false`
- `null`
- `undefined`
- Number: `42` `3.14159`
- String: `"Hallo!"`
- Object

- note: conversion is automatic

```js
var obj = {prop1: 'value1', 'weird-prop': 3};
console.log(typeof(obj));                // > object
console.log(typeof(obj.prop1));          // > string
console.log(typeof(obj['weird-prop']));  // > number
```

## [function hoisting](http://adripofjavascript.com/blog/drips/variable-and-function-hoisting.html)

```js
/* Function declaration */
foo(); // > "bar"
function foo() {
  console.log('bar');
}
/* Function expression */
baz(); // TypeError: baz is not a function
var baz = function() {
  console.log('bar2');
};
```

## control structures

```js
if (cond) {
} else if {
} else {
}

// loops
for (var i = 0; i < 10; i++) { }  // use continue and break
while (cond) { }

// switch
switch (value) {
    case 1: ...; break;
    default: ...
}

// try and catch:
try {
    throw expr;  // anything, actually
} catch (value) {
    // ...
} finally {
    // ...
}
```

```js
var arr = [3, 5, 7];
arr.foo = 'hello';  // remember: arrays are just objects!
// go over properties
for (var i in arr) {
   console.log(i);  // "0", "1", "2", "foo"
}
// go over iterable properties
for (var i of arr) {
   console.log(i);  // 3, 5, 7
}
```

## conversion:

- js does most of conversion for you
- [`parseInt()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseInt)
- [`parseFloat()`](https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Global_Objects/parseFloat)

### unary plus

```js
'1.1' + '1.1' // '1.11.1'
(+'1.1') + (+'1.1') // 2.2
// Note: the parentheses are added for clarity, not required.
```

## getting elements

```js
// all images with class="wide"
document.document.querySelectorAll("img.wide")

document.getElementById(id)
document.getElementsByTagName(name)
document.getElementsByClassName(name)
document.createElement(name)
document.removeChild(element)
document.appendChild(element)
document.head
document.body
```

### element properties

`document`

- `.innerHTML`, `.attribute`, `.setAttribute`, `.style.<css-attribute>`, `.on<event>`

## jQuery

```js
$("selector").action();
$('button.continue').html('Next Step...');
```

```js
.css("atribute", "value");
.attr("id", "value");
.append();
.remove();
.on("event", func(){...})
```

### Ajax

```js
$.ajax({
    url: '//api.icndb.com/jokes/random',
    data: {
        firstName: 'Hans',
        lastName: 'Dampf'
    },
    success: function (data) {
        $('blockquote').text(data.value.joke);
    }
});
```

```js
$.ajax({
    url: '//api.icndb.com/jokes/random'
    })
    .done(function (data) {
        $('blockquote').text(data.value.joke);
    });
```
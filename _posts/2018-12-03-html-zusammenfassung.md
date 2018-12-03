---
layout: post
title: "HTML Cheatsheet"
comments: true
description: "HTML zusammenfassung"
keywords: "html, wt"
---

# 1. HTML

```html
<!DOCTYPE html>
```

## [global atributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes#List_of_global_attributes)

- **id=""** unique identifier
- **class=""** css class(es)
- **style=""** inline css

```html
<html>
<!-- MUST contain head -->
<head>
  <meta charset="utf-8" />
  <title>Page Title</title>
  <meta name="viewport" content="width=device-width, initial-scale=1">
  <!-- external stylesheet -->
  <link rel="stylesheet" type="text/css" media="screen" href="main.css" />
  <!-- external script -->
  <script src="main.js"></script>
</head>
<!-- MUST contain body -->
<body>

</body>
</html>
```

- Reserved charakters:

  | &  | <  |  > | "  |
  |----|----|----|----|
  | `&amp;`  | `&lt;`  | `&gt;`  | `&quot;` |

- _[list of reserved charakters](https://dev.w3.org/html5/html-author/charref)_

## TAGS

- [**html**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/html)
  - **lang=""** declare language of web page, used by screen readers

  ```html
  <!DOCTYPE html>
  <html lang="de">
    <head>...</head>
    <body>...</body>
  </html>
  ```

***

- [**head**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/head)

  ```html
  <html>
    <head>
      <title>Document title</title>
    </head>
  </html>
  ```

  - Note: **Modern**, HTML5-compliant browsers automatically construct a `<head>` element if the tags are omitted in the markup

***

- [**body**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body)
  - must be second element inside `<html>` elemnt
  - permited contend [Flow contend](https://developer.mozilla.org/en-US/docs/Web/HTML/Content_categories#Flow_content)
  - [Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/body#Attributes)

***

- [Metadata Contend](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#Metadata_content)
- [Flow Contend](https://developer.mozilla.org/en-US/docs/Web/Guide/HTML/Content_categories#Flow_content)

### [Inline Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Inline_elements#Elements)

- [a](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a) (anchor, hyperlink)
  - categories: _Flow Contend, phrasing contend, interactive content, palpable contend_
  - **href=""** URL or URI, `#<id>` navigating the page to _id_
    - works with: `mailto:`, `tel:`
  - **target=""** specify browsing context: `_self` same tab, `_blank` new tab, `_parent`, `_top`
  - **type=""**  specify [MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types#Syntax)
  - **download=""** make the browser download instead

  ```html
  <a href="https://www.mozilla.com/">External Link</a>
  <a href="https://example.com">Website</a>
  <a href="mailto:nowhere@mozilla.org">Email</a>
  <a href="tel:+123456789">Phone</a>
  ```

  Clickable image:

  ```html
  <a href="https://developer.mozilla.org/en-US/" target="_blank">
    <img src="https://mdn.mozillademos.org/files/6851/mdn_logo.png"
         alt="MDN logo" />
  </a>
  ```

***

- [**img**](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML#How_do_we_put_an_image_on_a_webpage) (image)
  - categories: _Flow Contend, phrasing contend, embedded content, palpable contend_  
  - supported formats: _JPEG, GIF, PNG, SVG, BMP_
  - [loading errors](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#Image_loading_errors)
  - [Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#Attributes)
  - **src=""** image source: same dir, subdir, url
  - **sizes=""**, **srcset=""** for multiple resolutions
  - **alt=""** alternatve discription if cannot be displayed
    - **used for:** search engines, [text based browsers](https://en.wikipedia.org/wiki/Lynx_%28web_browser%29), disabled img to safe data, [screen reader](https://en.wikipedia.org/wiki/Screen_reader)
    - don't use _alt_ on decorative images, even better use [CSS bachground imgages](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML#CSS_background_images)
    - **contend**: pay attention to describing images, use alt="" if the img described in the text
    - `alt=""` indicates decorative images
  - **heigth=""** heigth in Pixels, **CSS prefered**
  - **width=""** width in Pixels, **CSS prefered**

  Examples:

  ```html
  <!-- same dir -->
  <img src="dinosaur.jpg">
  <!-- sub dir -->
  <img src="images/dinosaur.jpg">
  <!-- url, width, height -->
  <img src="https://www.example.com/images/dinosaur.jpg"
      width="400"
      height="341">

  <!-- with discription -->
  <img src="images/dinosaur.jpg"
      alt="The head and torso of a dinosaur skeleton;
            it has a large head with long sharp teeth">
  
  <!-- mozilla example -->
  <img class="fit-picture"
     src="/media/examples/grapefruit-slice-332-332.jpg"
     alt="Grapefruit slice atop a pile of other slices" />
  ```

***

- [**span**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/span)
  - categories: _Flow Contend, phrasing contend_
  - used to style text with `id=""` and `class=""`
  - only [global attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Global_attributes)
  Example:

  ```html
  <p>Add the
  <span class="ingredient">basil</span>,
  <span class="ingredient">pine nuts</span> and
  <span class="ingredient">garlic</span>
  to a blender and blend into a paste.</p>
  ```

***

- [**em**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/em)(emphasize)
  - categories: _Flow Contend, phrasing contend, palpable content_
  - only global attributes

  Example:

  ```html
  <p>This is <em>not</em> a drill!<p>
  ```

***

- [**strong**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/strong)
  - categories: _Flow Contend, phrasing contend, palpable content_
  - only global attributes

  Example:

  ```html
  <p>
  ... the most important rule, the rule you can never forget, no matter how much he cries, 
  no matter how much he begs:
  <strong>never feed him after midnight</strong>.
  </p>
  ```

***

- [**button**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button)
  - categories: _Flow content, phrasing content, interactive content, listed, labelable, submitable form-associated, palpable contet_
  - [Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/button#Attributes)
  - **disabled** disables button if present
  - **name=""** is submited with the form data
  - **type=""** `submit`(submits form to server, default) `reset`(resets to init values) `button`(no defeault behavior, used to trigger scripts)
  - **value=""** initial value
  - **form=""** element the button is associated with

  Example:

  ```html
  <button class="favorite styled"
          type="button">
    Add to favorites
  </button>
  ```

***

- [**input**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)
  - categories: _Flow content, listed, submittable, resettable, form-associated element, phrasing content_
  - [**type=""**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#Form_%3Cinput%3E_types), default: `text`
    - `button`, `text`, `checkbox`, `radio`, `file`, `password`, `color`(HTML5), `range`(HTML5), `search`(HTML5), `date`(HTML5), `email`(HTML5), `number`(HTML5)
  - [**disabled**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#disabled) if present input is desabled
  - [**list=""**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#list) id of `<datalist>`
  - [**placeholder=""**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input#The_placeholder_attribute)
  - **id=""** (DOM), **name=""** (`<form>`)
  
  Note: assistive technologies are using labels!
  
  Example:

  ```html
  <label for="name">Name (4 to 8 characters):</label>

  <input type="text"
        id="name"
        name="name"
        required
        minlength="4"
        maxlength="8"
        size="10">
  ```

***

- [**label**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label)
  - categories: _Flow content, form-associated element, phrasing content_
  - [Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/label#Attributes)
  - **for=""** the _id_ of the associated element
  - **form=""** the _id_ of the associated form

  Example:

  ```html
  <div class="preference">
    <label for="cheese">Do you like cheese?</label>
    <input type="checkbox" name="cheese" id="cheese">
  </div>

  <div class="preference">
    <label for="peas">Do you like peas?</label>
    <input type="checkbox" name="peas" id="peas">
  </div>

  <label>Click me <input type="text"></label>

  <label for="username">Click me</label>
  <input type="text" id="username">
  ```

***

- [**audio**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/audio)/[**video**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/video)
  - prefered to embed media
  - [check compatiblity](https://caniuse.com/)
  - **src=""** URL to the media
  - **autoplay** if specifeid media will autplay
  - **controls** broswer displays controls if present
  - **reload=""** `none`, `metadate`, default: `auto`
  - **type=""** [MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types#Discrete_types): `audio/mp3`, `video/mp4` ...

***

- [**iframe**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe)
  - categories: _Flow Contend, phrasing contend, embedded contend, interactive contend, palpable contend
  - [Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#Attributes)
  - [**title=""**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#Accessibility_concerns) should always describe iframe contend
  - [Scripting](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/iframe#Scripting) scripts from the iframe can get acsess to the window object

  Example:

  ```html
  <iframe id="inlineFrameExample"
          title="Inline Frame Example"
          width="300"
          height="200"
          src="https://www.openstreetmap.org/export/embed.html?bbox=-0.004017949104309083%2C51.47612752641776%2C0.00030577182769775396%2C51.478569861898606&layer=mapnik">
  </iframe>
  ```  

***

- [**br**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br)
  - categories: _Flow contend, phrasing contend_
  - do **not** use `<br>` [to create seperate paragraphs](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/br#Accessibility_concerns)

  Example:

  ```html
  Mozilla<br>
  331 E. Evelyn Avenue<br>
  Mountain View, CA<br>
  94041<br>
  USA<br>
  ```

***

### [Block Level Elements](https://developer.mozilla.org/en-US/docs/Web/HTML/Block-level_elements#Elements)

- [**table**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/table)
  - all attributes are deprecated

  Example:

  ```html
  <p>Table with colgroup</p>
  <table>
    <colgroup span="4"></colgroup>
    <tr>
      <th>Countries</th>
      <th>Capitals</th>
      <th>Population</th>
      <th>Language</th>
    </tr>
    <tr>
      <td>USA</td>
      <td>Washington, D.C.</td>
      <td>309 million</td>
      <td>English</td>
    </tr>
    <tr>
      <td>Sweden</td>
      <td>Stockholm</td>
      <td>9 million</td>
      <td>Swedish</td>
    </tr>
  </table>
  ```

***

- [**h1 ... h6**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements)
  - categories: _Flow contend, heading contend, palpable contend
  - [do not skip header levels](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/Heading_Elements#Navigation)
  - avoid `h1` more than once on a page
  - heading information may be used to construct table of contents
  - do not use lower levels to decrease font size, -> use CSS

  Example:

  ```html
  <h1>Beetles</h1>
    <h2>External morphology</h2>
        <h3>Head</h3>
            <h4>Mouthparts</h4>
        <h3>Thorax</h3>
            <h4>Prothorax</h4>
            <h4>Pterothorax</h4>
  ```

***

- [**p**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/p)
  - categories: _Flow contenet, palpable contet
  - Acsessibility: not use empty `<p></p>`, `<p>` tags are recodnized by scree readers

  Example:

  ```html
  <p>
  Geckos are a group of usually small,
  usually nocturnal lizards. They are found
  on every continent except Australia.
  </p>
  ```

***

- [**ol**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ol) (ordered list)
  - categories: _Flow content_
  - **reversed** (HTML5) displays in reversed order when present
  - **start=""** (HTML5) speciefies start value for nunmbering
  - **type=""** `"a"` lowercase latters, `"A"` uppercase letters, `"i"` lowercase roman, `"I"` upper roman, `"1"` numbers

  Example:

  ```html
  <ol>
    <li>Mix flour, baking powder, sugar, and salt.</>
    <li>In another bowl, mix eggs, milk, and oil.</li>
    <li>Stir both mixtures together.</li>
    <li>Fill muffin tray 3/4 full.</li>
    <li>Bake for 20 minutes.</li>
  </ol>
  ```

- [**ul**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/ul) (unordered list)
  - categories: _Flow control_
  - use CSS: list-style-type: <...>; `spave-counter`, `disc`, `circle`

  CSS:

  ```css
  list-style-type: disc;
  list-style-type: circle;
  list-style-type: square;
  list-style-type: decimal;
  list-style-type: georgian;
  ```

  Example:

  ```html
  <ul>
  <li>first item</li>
  <li>second item
  <!-- Look, the closing </li> tag is not placed here! -->
    <ul>
      <li>second item first subitem</li>
      <li>second item second subitem
      <!-- Same for the second nested unordered list! -->
        <ul>
          <li>second item second subitem first sub-subitem</li>
          <li>second item second subitem second sub-subitem</li>
          <li>second item second subitem third sub-subitem</li>
        </ul>
      </li> <!-- Closing </li> tag for the li that
                  contains the third unordered list -->
      <li>second item third subitem</li>
    </ul>
  <!-- Here is the closing </li> tag -->
  </li>
  <li>third item</li>
  </ul>
  ```

***

- [**div**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div)
  - categories: _Flow contend_
  - [Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/div#Attributes) only global
  - divs are not represet anything they are used to group contend for styling porpuses with `id=""` and `class=""`

  Example:

  ```html
  <div class="warning">
    <img src="/media/examples/leopard.jpg"
         alt="An intimidating leopard.">
    <p>Beware of the leopard</p>
  </div>
  ```

***

- [**form**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/form)
  - "old style" web programming, since it redirects the user to a new page, _still used to indicate grouping_
  - categories: _Flow contend, palpable contend
  - **autocomplete=""** `off`, `on`,
  - **target=""** `_self`, `_blank_`, `_top`, `_parent`

  Example:

  ```html
  <form action="" method="get" class="form-example">
    <div class="form-example">
      <label for="name">Enter your name: </label>
      <input type="text" name="name" id="name" required>
    </div>
    <div class="form-example">
      <label for="email">Enter your email: </label>
      <input type="email" name="email" id="email" required>
    </div>
    <div class="form-example">
      <input type="submit" value="Subscribe!">
    </div>
  </form>
  ```

***

- [**hr**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/hr) (Horizontal Rule)
  - categories: _Flow content_

  Example:

  ```html
  <p>§1: The first rule of Fight Club is: You do not talk about Fight Club.</p>

  <hr>

  <p>§2: The second rule of Fight Club is: Always bring cupcakes.</p>
  ```

### Acsessibility

- **dont** use tables for layouts
- propper controls (`<botton>` instead of `<div onclick="...">`)
- use `<labels>` to `<input>`
- use propper `alt=""` on `<img>`
  - test: user [screenreader](https://de.wikipedia.org/wiki/Screenreader)
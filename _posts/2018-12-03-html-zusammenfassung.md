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

### Inline Elements

- [a](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/a)
  - categories: _Flow Contend, phrasing contend, interactive content, palpable contend_
  - **href=""** URL or URI, `#` for top of the page
    - works with: `mailto:`, `tel:`
  - **target=""** specify browsing context: `_self` same tab, `_blank` new tab
  - **type=""**  specify [MIME type](https://developer.mozilla.org/en-US/docs/Web/HTTP/Basics_of_HTTP/MIME_types#Syntax)

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

- [**img**](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML#How_do_we_put_an_image_on_a_webpage)
  - categories: _Flow Contend, phrasing contend, embedded content, palpable contend_  
  - supported formats: _JPEG, GIF, PNG, APNG, SVG, BMP_
  - [loading errors](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#Image_loading_errors)
  - [Attributes](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/img#Attributes)
  - **src=""** image source
    - **img source:** same dir, subdir, url
  - **alt=""** alternatve discription if cannot be displayed
    - **used for:** search engines, [text based browsers](https://en.wikipedia.org/wiki/Lynx_%28web_browser%29), disabled img to safe data, [screen reader](https://en.wikipedia.org/wiki/Screen_reader)
    - don't use _alt_ on decorative images, even better use [CSS bachground imgages](https://developer.mozilla.org/en-US/docs/Learn/HTML/Multimedia_and_embedding/Images_in_HTML#CSS_background_images)
    - **contend**: pay attention to describing images, use alt="" if the img described in the text
    - `alt=""` indicates decorative images
  - **heigth=""** heigth in Pixels
  - **width=""** width in Pixels

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

- [**input**](https://developer.mozilla.org/en-US/docs/Web/HTML/Element/input)

---
weight: 5
title: "CSS"
date: 2022-12-15
lastmod: 2023-08-01
draft: false
author: "Jose Benitez"
description: "CSS fundamentals guide."
images: []
resources:
- name: "featured-image"
  src: "css.jpeg"

tags: ["CSS"]
categories: ["Educational"]

twemoji: false
lightgallery: true
---


### Linking CSS with HTML

- ##### Add to HTML file in the head section:
    - **link**: link tag
        - **rel**: relationship attribute set as "stylesheet"
        - **href**: location of the CSS document
- ##### CSS basics:
    - A good resource for choosing color is [html color picker](https://www.google.com/search?q=html+color+picker&oq=html+color+picker&aqs=chrome..69i57j0i512l9.2641j0j9&sourceid=chrome&ie=UTF-8)
    - <u>Rule</u>: styled output for a section
        - <u>Selector</u> = selector elements tell css which section to style
        - <u>Declaration(s)</u> = different ways you can modify a section
    

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Example Page</title>
    <link rel="stylesheet" href="css/screen.css">
  </head>
  <body>
    <h1>Sample Landing Page</h1>

    <p>
      Paragraph <span>with</span> only one sentence.
    </p>

    <p class="special-p">
      Paragraph <span>with</span> only one sentence.
    </p>

  </body>
</html>
```


```css

/* file: css/screen.css */

h1 {
    color: orange;
    text-align: center;
}

p {
    color: #869960;
}

```

---

### CSS Selectors
- <u>Type selectors:</u> name of an element and targets every element with that selector in a page. 
- <u>Descendant selectors:</u> drilling into a subsection to modify it further
- <u>Class selectors:</u> special cases where you can't use a type selectors. Specify the class in the tag you want to change and make sure to initialize the selector with a period. 
```css

/* file: css/screen.css */

/* Type selectors */
h1 {
    color: orange;
    text-align: center;
}

/*Descendant selectors*/
body p span{
    color: green;
}

/* Class selectors */
.special-p {
    background-color: yellow;
}

/* You can mix them all */
body .special-b{
    background-color: LightGray;
}

/* Less specific */
footer p{
    color: white;
}

/* More specific thus more prioritized  */
body footer p{
    color: red;
}


```

### Box Model
- <u>padding</u>: space between the content and the edges
- <u>border</u>: outline around the outer edge of the box. specify thickness type and color
- <u>margin</u>: space between boxes
    - <u>margin-bottom</u>: pushes down 
- <u>width</u>: works well with pixels;
- <u>heightv </u>: works well with pixels;
- <u>box-sizing</u>: with <i>border-box</i> the box takes the size of the width,height you specified. 

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Example Page</title>
  </head>
  <body>
    <div class="box-a"> Box A></div>
    <div class="box-b"> Box B></div>
  </body>
</html>
```

```css

/* file: css/screen.css */
.box-a {
    background-color: LightGray;
    padding: 30px;
    border: 3px solid black;
    margin-bottom: 20px;
    width: 200px;
    height: 150px;
    box-sizing: border-box;
}

.box-b {
    background-color: orange;
    padding: 30px;
    border: 3px solid black;
    width: 200px;
    height: 200px;
}


```

### Floats
- <u>max-width</u>: cutoff for parageraphs
- <u>margins</u>:
 - <u>margin-left</u>: setting it to auto will put the right amount of space in the left margin
 - <u>margin-right</u>: setting it to auto will put the right amount of space in the right margin
- <u>float</u>: floats towards one direction and wraps the text around it
- <u>clearfix method</u>: fix for the blind spot where we arrange the paragraphs in columns and the parent content doesn't recognize the children after the float


```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Example Page</title>
    <link rel="stylesheet" href="css/screen.css">
  </head>

  <body>

    <div class="container">

        <header>
            <h1>Sample Landing Page</h1>
            <p> Insert slogan here</p>
        </header>
            <div class="content-area group">
                <div class="main-area">
                    <p>
                        This is the main area (or column). Lorem ipsum dolor sit amet...
                       
                    </p>
                </div>

                <aside class="sidebar">
                    <p>
                        This is the idebar. Lorem ipsum dolor sit amet, consectetur ...
                    </p>

                </aside>

                <div class="fix"></div>

            </div>


        <footer> TM 2022 CalendarINC</footer>



    </div>

  </body>
</html>
```


```css

/* file: css/screen.css */

.container{
    /* paragraph cutoff */
    max-width: 940px;

    /* center paragraph */
    margin-left: auto; 
    margin-right: auto; 

}   

.content-area {
    border-top: 3px solid black;
    border-bottom: 3px solid black;

}

.main-area {
    width: 66%
    float: left;
}
.sidebar {
    width: 34%
    float: left;
}

.fix {
    /* clears the floats so the parent element is aware of its children's contents */
    clear: both;
}

/* clearfix method */

.group: before,
.group: after {
    content: "";
    display: table;
}
.group: after{
    clear: both;
}
.group{
    zoom:1;
}

/* end of clearfix method */

```

### CSS Fonts
- <u>font-family</u>
- <u>font-weight:</u> 
- <u>font-size</u>
- <u>font-family</u>
- <u>font-family</u>

### Image React on Hover
  - Making an image slightly go up when mouse placed over it.
```css
img {
    transition: transform 0.5s;
}

img:hover {
    transform: translateY(-5px);
}
```
```html

<img src="/path/to/image.jpg" alt="Alt text">

```

---
weight: 5
title: "HTML"
date: 2022-12-17
lastmod: 2023-08-01
draft: true
author: "Jose Benitez"
description: "HTML fundamentals guide."
images: []
resources:
- name: "featured-image"
  src: "html.png"

tags: ["HTML"]
categories: ["Educational"]
lightgallery: true
---
---

### Document Structure

- **DOCTYPE**: lets the web browser know it's ok to use the most modern version of HTML
- **html**: root of the document
  - **head**:
    - **meta**: specifies character set
      - UTF-8 is for generally used for English
    - **title**: tab and site title
  - **body**:
    - **headers**:
      - h1, h2, h3, h4, h5, h6 (descending order)
    - **paragraph**
      - just p

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Example Page</title>
  </head>
  <body>
    <h1>Sample Landing Page</h1>
    <p>
      Paragraph with only one sentence.
    </p>
  </body>
</html>
```

---

### Linking Pages

- **a**: tag for a link
  - **href**: requires the <u>hypertext reference attribute</u>

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Homepage</title>
  </head>
  <body>
    <h1>Homepage</h1>
    <p>
      Welcome to the homepage. Learn more about my
      <a href="favorite-languages.html">favorite language</a>
      .
    </p>
  </body>
</html>
```

---
### Images
- **img**: image tag
  - **src**: attribute where you specify the location of the image 
  - **alt**:  attribute that serves as a basic description of the image (alternative text)


```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Homepage</title>
  </head>
  <body>
    <h1>Homepage</h1>
    <p>
      Welcome to the homepage. Learn more about my
      <img src= "image.png" alt="description of image">
    </p>
  </body>
</html>
```

---
### Audio
- **audio**: image tag
  - **controls**: shows pause play volume options
- **source**: source tag
  - **src**: attribute where you specify the location of the audio 
  - **type**:  specify the audio type


```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Homepage</title>
  </head>
  <body>
    <h1>Homepage</h1>
    <p>
      This is an audio file:
      <audio controls>
        <source src="audio/song.mp3" type="audio/mpeg"> //Browser should pick this one
        <source src="audio/song.ogg" type="audio/ogg"> //If it doesn't recognize mpeg it'll pick this one
        <a href="audio/song.mp3"></a> //Alternative for outdated browsers 
      </audio>  
    </p>
  </body>
</html>
```


---
### Video
- **video**: image tag
  - **controls**: shows pause play volume options
- **source**: source tag
  - **src**: attribute where you specify the location of the video 
  - **type**:  specify the video  type
- **iframe**: youtube video tag
  - **width**: width attribute
  - **height**: height attribute
  - **src**: youtube link to video


```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Homepage</title>
  </head>
  <body>
    <h1>Homepage</h1>
    <p>
      This is a video file:
      <video controls>
        <source src="video/example.mp4" type="video/mp4"> //Browser should pick this one
        <source src="video/example.webm" type="video/webm"> //If it doesn't recognize mp4 it'll pick this one
        <source src="video/example.ogv" type="video/ogg"> //If none of the other ones work it'll pick this one
        Your web browser if outdated and does not support HTML video. Please consider <a href="http://browsehappy.com/">updating</a>. 
      </video>  
    </p>
  </body>
</html>
```


---
### Vector Graphics
What is a vector graphic? It's basically an image that doesn't loose quality when zooming in. It's comprised of adjustable shapes. 

**Figma** and **XD** are good resources for vector graphics. 

Append either by copy pasting the contents into the code or by referencing the image using svg as the type. 

---
### Lists
- **ul**: unordered list tag
  - **li**: list item is a bullet
- **ol**: ordered list tag
  - **li**: list item is a number type bullet
- **dl**: description list tag
  - **dt**: term attribute
  - **dd**: attribute that describes the term

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Homepage</title>
  </head>
  <body>
    <ul>
      <li>Order</li>
      <li>Doesn't</li>
      <li>Matter</li>
    </ul>

    <ol>
      <li>Order</li>
      <li>DOES</li>
      <li>Matter</li>
    </ol>

    <dl>
      <dt>Term1</dt>
      <dd>description1</dd>
      <dt>Term2</dt>
      <dd>description2</dd>
      <dt>Term3</dt>
      <dd>description3</dd>
    </dl>

  </body>
</html>
```

---
### Bold and Italics
- **strong**: bold tag
- **b**: bold tag
- **em**: emphasis (italics) tag. a screening software would pronounce it differently
- **i**: italic tag without word emphasis in pronunciation

---
### Special Characters
```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Homepage</title>
  </head>
  <body>
    <ul>
      <li>Ampersand: &amp; </li>
      <li>Copyright: &copy;</li>
      <li>Registered symbol: &reg;</li>
      <li>Trademark symbol: &trade;</li>
    </ul>

  </body>
</html>
```

---
### Semantics and Structural Elements
- **header**: tag for elements that go in the beginning of the page
- **footer**: tag for elements that go in the bottom of the page
- **article**: the content wrapped inside the tag is considered as one of the subtopics
- **aside**: related to the page's main topic but independent from surrounding tags
- **nav**: include links for navigation links inside the website
- **div**: general purpose block-level element with no semantic meaning. stands for division. useful for css classes. 
- **span**: general purpose inline element with no semantic meaning.useful for css classes. 
```html
<!DOCTYPE html>
<body>
  <header>
    <h1>My Website</h1>
    <nav>
      <ul>
        <li><a href="/">Home</a></li>
        <li><a href="/about">About</a></li>
        <li><a href="/contact">Contact</a></li>
      </ul>
    </nav>
  </header>
  <main>
    <article>
      <h2>Welcome to My Website!</h2>
      <div class="article-body">
        <p>Lorem <span class="brand-color">ipsum</span> dolor sit amet, consectetur adipiscing elit. Proin malesuada ante quis enim efficitur, in aliquam sapien fringilla. Donec volutpat diam et nunc viverra, id lobortis enim condimentum. Suspendisse bibendum, ante quis iaculis malesuada, dolor est ullamcorper lacus, id euismod est mauris a elit. Mauris non diam sit amet turpis viverra ullamcorper vel eu lectus. Suspendisse vehicula, diam a semper suscipit, arcu lacus mollis est, sit amet facilisis libero erat et tellus. Vestibulum ante ipsum primis in faucibus orci luctus et ultrices posuere cubilia Curae; Duis eleifend, arcu nec auctor varius, mauris nisi iaculis est, eu consectetur elit ante et dui. Vestibulum nec nisi nec diam ornare condimentum. Ut pretium porta erat, ut condimentum erat interdum et. Duis lacus lectus, suscipit et orci eu, facilisis accumsan leo.</p>
      </div>
    </article>
    <aside>
      <h3>Popular Posts</h3>
      <ul>
        <li><a href="/post1">Post 1</a></li>
        <li><a href="/post2">Post 2</a></li>
        <li><a href="/post3">Post 3</a></li>
      </ul>
    </aside>
```

---

### Forms
- **form**: tag that surrounds everything related to the input box
  - **input**: element to initialize input field (no closing /input is required)
    -**type**: attribute to specify which type of input it is
    -**id**: attribute use in conjunction with the <i>for</i> attribute in label. 
    -**value**: attribute to specify value like "Submit" for example
    -**name**: identifier so other programming languages can use the input element
  -**label**: tag to label the input box
    -**for**: used in conjunction with the id attribute in input string(name them the same).
  


```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Example Page</title>
  </head>
  <body>
    <form>
      <label> First Name:
        <input type="text" name="firstName">
      </label>

      <label for="lastName">First Name:</label>
      <input id="lastName" type="text" name="lastName">

      <input type="submit" value="Submit" >
    </form>
  </body>
</html>
```

---
### Input Types


```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Example Page</title>
  </head>
  <body>

    <form>

      <label for="email">Email:</label>
      <input id="email" type="email" name="email">
      <input type="submit" value="Save!">

      <label for="telephone">telephone:</label>
      <input id="telephone" type="tel" name="telephone">
      <input type="submit" value="Save!">

      <label for="yourMessage">Your Message:</label>
      <textarea id="yourMessage" name="yourMessage"></textarea>
      <input type="submit" value="Save!">

    </form>

  </body>
</html>
```

### Foreign Fields

- **select**:
  - **option**: attribute to print the bullet in form of dropdown list
    -**name**: important to identify the name of the option selected for backend purposes
- **fieldset**: tag used in radio
  - **legend**: wraps all of the inputs and labels with the text specified
  - **input**:  NO end tag because it doesn't accept text
    - **type**:specify the radio type
    - **id**: pair the id with the for attribute in label.
    - **name**: specify for identification and backend purposes
    - **value**: specify for backend purposes 

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>HTML Foreign Fields</title>
  </head>
  <body>
    
    <!-- Dropdown: -->
    <label for="favoriteColor">What is your favorite color?</label>
    <select id="favoriteColor" name="favoriteColor">
      <option name="colorRed">Red</option>
      <option name="colorGreen">Green</option>
      <option name="colorBlack">Black</option>
    </select>

    <!-- Radio: -->
    <fieldset>
      <legend>What is your favorite meal?</legend>
      <input type="radio" id="breakfast" name="favoriteMeal" value="meal1">
      <label for="breakfast">Breakfast</label> 
      <input type="radio" id="lunch" name="favoriteMeal" value="meal2">
      <label for="lunch">Lunch</label> 
      <input type="radio" id="dinner" name="favoriteMeal" value="meal3">
      <label for="dinner">Dinner</label> 
    </fieldset>

    <!-- Checkbox: -->
    <fieldset>
      <legend>Which meals do you enjoy? (check all that apply)</legend>
      <input type="checkbox" id="breakfast" name="favoriteMeal" value="meal1">
      <label for="breakfast">Breakfast</label> 
      <input type="checkbox" id="lunch" name="favoriteMeal" value="meal2">
      <label for="lunch">Lunch</label> 
      <input type="checkbox" id="dinner" name="favoriteMeal" value="meal3">
      <label for="dinner">Dinner</label> 
    </fieldset>



  </body>
</html>
```

### Tables
- Don't use tables for column structure in a page!
- **table**: table tag
  - **thead**: good practice to include headers under this tag
    - **tr**: table row attribute
      - **th**: table header attribute
  - **tbody**: good practice to include the data under this tag
    - **tr**: table row attribute
      - **td**: table data attribute
  - **tfoot**: good practice to include the bottom row under this tag
    - **tr**: table row attribute
      - **td**: table data attribute



```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Example Page</title>
  </head>
  <body>
    
    <table>
      <thead>
        <tr>
        <th>Name</th>
        <th>Aisle</th>
        <th>Price</th>
        <th>Quantity</th>
      </tr>
      </thead>

      <tbody>
        <tr>
          <td>Bread</td>
          <td>3</td>
          <td>$3.00</td>
          <td>1</td>
        </tr>
        <tr>
          <td>Milk</td>
          <td>1</td>
          <td>$2.50</td>
          <td>3</td>
        </tr>
      </tbody>

      <tfoot>
        <tr>
          <td>Total</td>
          <td>N/A</td>
          <td>5.50</td>
          <td>N/A</td>
        </tr>
      </tfoot>

    </table>

  </body>
</html>
```



---
weight: 5
title: "React.JS"
date: 2023-01-14
lastmod: 2023-01-14
draft: false
author: "Jose Benitez"
description: "React fundamentals"
images: []
resources:
- name: "featured-image"
  src: "reactjs.png"

tags: ["React"]
categories: ["Educational"]
lightgallery: true
---

### What is React?
 - Javascript library for building UIs. 
 - Strictly front-end, meaning it runs in the browser.
 - React builds a SPA (Single Page Application) 
   - You have a single HTML page
   - Routing and other interactive features compile to a javascript bundle that is loaded by the browser.
- Usually in combination with other technologies to crate a full stack app.
- It has an entire ecosystem of libraries of packages you can install to make it function as a full-fledged framework.
- The top 3 frameworks in the industry are:
  1) React
  2) Vue
  3) Angular

### Why React?
- Reusable components with their own state.
  - Vanilla JS can get very messy very quickly.
- JSX (Javascript Syntax Extension) allows us to write dynamic HTML.
- The apps are very interactive because it uses the virtual DOM
  - The Document Object Model allows you to update parts of the page without reloading it. 
  - React DOM = responsible for rendering
- Very big in the industry. 
  - Good for team projects. 
- Great for performance and testing.

### States
- A state is an object that determines how a component renders and behaves.
- Any data that you bring into your components is part of the state.
  - Often we want to share this data across multiple components. That's when we use:
    - Global state = App state = state that is available to the entire UI (not just to a single component).

### Hooks 
- React Hooks = functinos that let us hook into the React state and lifecycle features from function components.
  - useState = returns a stateful value and function to update it.
  - useEffect = perform side effects in function components.
    - One of the biggest uses for useEffect is to make http requests when the page loads.
  - Other hooks:
    - useContext
    - useReducer
    - useRef

### Getting Started
- Steps:
    1) Environment: 
       - **NPM** (Node Package Manager)
         - If you don't have it, go to [node.js.org](https://nodejs.org) and click on the download button.
         - Necessary to create the react project folder.
       - **React Developer Tools**
         - Chrome extension useful to see the components, props, and state of the React app.
    2) Initialize Project: 
        ```bash
        npx create-react-app Name-Of-Your-Project
        ```
    3) Open React Project in Code Editor:
        ```bash
        cd Name-Of-Your-Project
        code . #Opens it in VS Code (in my case)
        ```
    4) Running Project Locally:
        ```bash
        npm start
        ```
    5) Useful Extensions:
        - ES7 React/Redux/GraphQL/React-Native snippets
            ```javascript
            rafce
            ```
### React Folders
-  Breaking down each folder:
  1) Public: 
       - index.html = contains the SPA
            ```html
                <html>
                    <body>
                            <noscript>
                                You need to enable JavaScript to run this app.
                            </noscript>
                            <div id='root'></div>
                    </body>
                </html>
            ```
     - favicon.ico

   2) Src: where we store all of our components
       - App.js = root component
       - App.css = basic styling
       - logo.svg = picture that must be imported wherever it's used
       - index.js = entry point for React
            ```javascript
            //These reference the packages found in package.json in the highest level.
            import React from 'react';
            import ReactDOM from 'react-dom'; 
            import App from './App'; //Assuming the root component is called "App.js"



            ReactDOM.render(
                <React.StrictMode>
                    <App />
                <React.StrictMode>,

                //Inserting the App from above where the div with 'root' is found in index.html
                document.getElementById('root') 
            );
            ```

### Components
- Components can be Functions or Classes. 
  - In React we're using JSX and it has some subtle differences from HTML:
    - Use className attribute not class attribute
    - Use htmlFor attriubt not for attribute
- JSX expressions can only return one parent element.
  - Example in App.js:
    ```javascript
    import logo from './logo.svg';
    import './App.css';

    function App(){
        const name = 'Jose'
        const age  = 20
        const x = true

      return (
          <div className="App">
              <header classsName="App-header">
                  <img src={logo} className="App-logo" alt="logo" />
                  <p>
                    Hello {name}
                    Next year you will be {age + 1}
                    Ternary operator says {x ? 'Yes' : 'No'}

                  </p>
              </header>
          </div>
      );
    }

    export default App
    ```

### Props
- Props allow for dynamically changing and assigning variables.
- In this example let's create a header component called Header.js and call it in App.js:

```javascript
import PropTypes from 'prop-types'
//Write impt if using the ES7 extension  

const Header = ({title}) => {
    // Alternatively  = (props) =>
    return (
        <header>
            <h1>{title}</h1> 
            // Alternatively {props.title}
        </header>
    )
}

Header.defaultProps = {
    title : 'Default Title',
}

export default Header
```

```javascript
import Header from './components/Header'

const App = () => {
    return (
        <div className = 'container'>
            <Header title='Official Title'/>
        </div>
    )
}
```

### Styling
- You can style the page using three different methods:
1) Importing a CSS file
2) In-line JSX styling (very similar to CSS but instead of ';' at the end of the line put comas to separate; use Camel Case as well so no dashes)
3) Variable called headingStyle that ultimately has a CSS rule

    ```javascript

    // Way #2
    import React from 'react'
    import PropTypes from 'prop-types'

    const Header = (props) => {
    return (
        <header>
            <h1 style={{color: 'red', backgroundColor:'black'}}>{props.title}</h1>
        </header>
    )
    }

    export default Header
    ```

    ```javascript

    // Way #3
    import React from 'react'
    import PropTypes from 'prop-types'

    const Header = (props) => {
    return (
        <header>
            <h1 style={headingStyle}>{props.title}</h1>
        </header>
    )
    }

    const headingStyle = {
        color: 'red', backgroundColor:'black'

    }

    export default Header
    ```
            



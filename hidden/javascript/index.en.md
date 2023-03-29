---
weight: 5
title: "JavaScript"
date: 2022-12-10
lastmod: 2023-01-08
draft: true
author: "Jose Benitez"
description: "JS fundamentals guide."
images: []
resources:
- name: "featured-image"
  src: "js.png"

tags: ["JavaScript"]
categories: ["Educational"]

twemoji: false
lightgallery: true
---


---
### What is JS
- High level, interpreted programming language
  - Interpreted means it's executed directly (doesn't use a compiler)
- Conforms to the ECMAScript specification
- Runs on the client/browser as well as on the server (Node.js)
  - Node.js is a javascript run time
- JavaScript is not statically typed meaning you don't have to specify the data type at compile time. 

### Console
- JavaScript Console documentation: [MDN Console](https://developer.mozilla.org/en-US/docs/WEB/API/console)

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>Homepage</title>
  </head>
  <body>
    <h1>JS Crash Course</h1>

    <script src="main.js"></script>

  </body>
</html>
```
```javascript
console.log('Hello World');
console.error('This is an error');
console.warning('This is an warning');
```

### Variables
- **Assignment Key Words**:
  - **Var**: globally scoped
    - Since it's globally scoped it can cause problems so avoid it unless you're sure to use it in a specific case. 
  - **Let**: variable that can be reassigned
  - **Const**: variable that can't be changed (it stands for constant)
- **Data Type**:
  - Strings:
  - Numbers
    - Note there are no floats or decimals
  - Boolean 
  - Null
  - Undefined
  - Symbols

```javascript
const name= "John";
const age = 30;
const rating = 4.5;
const isCool = true;
const x = null;
const y = undefined;
let z;

console.log(typeof name); //string
console.log(typeof age); //number
console.log(typeof rating); //number
console.log(typeof isCool); //boolean
console.log(typeof x); //object
console.log(typeof y); //undefined
console.log(typeof z); //undefined

//Concatentation
console.log('My name is'+ name +' and I am '+ age);
//Template String
console.log(`My name is ${name} and I am ${age}`);
    //Variable Assignment:
    const hello = `My name is ${name} and I am ${age}`;
    console.log(hello)
```

### Properties and Methods
- Properties:
  - Don't have parenthesis

    ```javascript
    const s = 'Hello World!';
    console.log(s.length); //12
    ```

- Methods: function associated with an object.
  - Have parenthesis  
    ```javascript
    const s = 'Hello World!
    console.log(s.toUpperCase()); //HELLO WORLD!
    console.log(s.toUpperCase()); //hello world!
    console.log(s.substring(0, 5).toUpperCase()); //HELLO
    console.log(s.split('')); //['H', 'e', 'l', 'l', 'o', ' ','W', 'o', 'r', 'l', 'd', '!']
    ```

### Arrays
- new: is a constructor key word
- push: add to an array
- unshift: add to the beginning of an array
- pop: drop the last element of the array
- isArray: returns a boolean 
- indexOf: returns the index of the specified value in array

```javascript

//Possible way of initializing an array:
const numbers = new Array(1,2,3,4,5);
//Most popular way of initizliaing an array:
const fruits = ['apples', 'oranges', 'bananas']; 
//Add to the end of an array:
fruits.push('grapes');'apples', 'oranges', 'bananas','grapes'
fruits.unshift('mangos')'mangos','apples', 'oranges', 'bananas','grapes'
fruits.pop(); 'mangos','apples', 'oranges', 'bananas'
Array.isArray(fruits);//true
fruits.indexOf('oranges');//2
```

### Object Literals 
- Object Literals : key value pairs

```javascript
const person={
  firstName : 'John',
  lastName : 'Doe',
  age: 30,
  hobbies: ['music', 'painting', 'sports'],
  address: {
    street: '50 main st',
    city: 'Boston',
    state: 'MA'
  }
}

console.log(person.firstName, person.lastName);// John Doe
console.log(person.hobbies[1]); //painting
console.log(person.address.street); //50 main st

// Example 1:
  const todos = [
    {
      id : 1,
      text: 'Take out the trash',
      isCompleted: true
    },
    {
      id : 2,
      text: 'Meeting with boss',
      isCompleted: true
    },
    {
      id : 3,
      text: 'Dentist appt',
      isCompleted: false
    }
  ];

  const todoJSON = JSON.stringify(todos);
  console.log(todoJSON);

```


### Iteration
- For loops are used for iterations and they require 3 attributes: 
  - starting point
  - end point
  - change constant
- High order array methods:
  - forEach: used for iterating through arrays
  - map: returns an array 

```javascript
//For
for(let i = 0; i <= todos.length; i++){
  console.log(`For Loop Number: ${i}`);
}

//While
let i=0;
while(i<10){
  console.log(todos[i].text);
  i++;
}

//Popular for loop:
for(let todo of todos){
  console.log(todo.id);
}

//High order array methods

  //forEach:
  todos.forEach(function(todo){
    console.log(todo.text);
  });

  //map:
  const todoText = todos.map(function(todo){
    return todo.text; //This example will create an array of the text values in the object literals
  });

  //filter:
  const todoCompleted = todos.filter(function(todo){
    return todo.isComplete === true;//This example will create an array of the object literals where isComplete is true
  });

  //filter + map:
  const todoCompleted = todos.filter(function(todo){
    return todo.isComplete === true;
  }).map(function(todo){
    return todo.text;
  });
  ```

  ### Conditionals
  - if statements:
    - What's the difference between '==' and '==='?
      - Triple equal sign checks if the data types match while double equal sign doesn't.
  - Ternary Operator:
    - syntactic sugar to shorten an if else statement
  - Switches:
    - Another way to evaluate a condition
    - It's very case based

  ```javascript
  const x = 10;
  const y = 4;


  if(x === 10){
    console.log('x is 10');
  } else if(x > 10){
    console.log('x is greater than 10');
  } else{
    console.log('x is less than 10');
  }

  if(x > 5 || y < 10){
    console.log('x is greater than 5 or y is more than 10');
  } //deoesn't run


  //Ternary Operator
  const color = x > 10 ? 'red' : 'blue';

  //Switch
  switch(color){
    case 'red':
      console.log('color is red');
      break;
    case 'blue':
      console.log('color is blue');
      break;
    default:
      console.log('color is not red or blue');
      break;
  }
  ```

### Functions
- **function**: key word to define a function
-  Fat Arrow:
   -  Preceded by the inputs and followed by the output


```javascript

//This is one way to do it
function addNums(num1 = 1, num2 = 1){
  console.log(num1+num2);
}
addNums(5,5)

//This is another way to do it
const addNums = (num1 = 1, num2 = 1) => num1 + num2;

console.log(addNums(5,5));

//Fat Arrow:
todos.forEach((todo)=> console.log(todo));

```

### Object Oriented Programming
- **Constructor Function**:
  - They should start with a capital letter
  - **Parameters**: properties you want to be able to set
    - Write them inside the parentheses 
  - **Properties**: 
    - Set them as properties of the object
    - Use **this** key word

```javascript

//Constructor Function
function Person(firstName, lastName, dob){
  this.firstName = firstName;
  this.lastName = lastName;
  this.dob = new Date(dob);
  this.getBirthYear = function(){
    return this.dob.getFullYear();
  }
}

//Prototypes:
  Person.prototypes.getFullName = function(){
    return `${this.firstName} ${this.lastName}`;
  }

//Instantiate an object
const person1 = new Person('John', 'Doe', '4-3-1980');
const person2 = new Person('Mary', 'Smith', '3-6-1970');

console.log(person1); // * displays the object literal * 
console.log(person2.dob); //Fri Mar 06 1970 00:00:00 EST
console.log(person2.getBirthYear()); //1970
console.log(person1.getFullName()); //John Doe
```


### Classes
- Syntactic sugar for constructor functions


```javascript

//Class:
  class Person{
    constructor(firstName, lastName, dob) {
      this.firstName = firstName;
      this.lastName = lastName;
      this.dob = new Date(dob);
    }

    getFullName(){
       return `${this.firstName} ${this.lastName}`;
    }
  }

  //Instantiate an object
  const person1 = new Person('John', 'Doe', '4-3-1980');
  const person2 = new Person('Mary', 'Smith', '3-6-1970');

  console.log(person1); // * displays the object literal * 
  console.log(person2.dob); //Fri Mar 06 1970 00:00:00 EST
  console.log(person1.getFullName()); //John Doe
```

### DOM
- DOM: Document Object Model
- For the below example assume we're working with a webpage where the user can input their name and email. 


```javascript
// Single element
console.log(document.getElementbyId('my-form'));
console.log(document.querySelector('.container'));

//Multiple element
console.log(document.querySelectorAll('.item')); //preferred
console.log(document.getElementbyClassName('item')); //renders an html collections (which don't allow you to use array methods)
console.log(document.getElementbyTagName('li')); 

// Example 1:
const items = document.querySelectorAll('.item');
items.forEach((item)=> console.log(item));

//Example 2:
const ul = document.querySelector('.items');
ul.remove(); //This method removes the written html

//Example 3:
const ul = document.querySelector('.items');
ul.lastElementChild.remove(); //Removes the last item list

//Example 4:
const ul = document.querySelector('.items');
ul.firstElementChild.textContent = 'Hello';

//Example 5:
const ul = document.querySelector('.items');
ul.remove(); //This method removes the written html

//Example 6:
const ul = document.querySelector('.items');
ul.lastElementChild.innerHTML = '<h1>Hello</h1>'; //adds html dynamically

//Example 7:
const btn = document. querySelector('.btn');
btm.style.background = 'red';
```


### Events
- addEventListener
  - **click**
  - **mouseover**
- (e) : event object
  - Has a bunch of attributes
    - position of the mouse
    - movementX
    - movementY
    - target
      - className
- preventDefault: 
  - prevent the default behaviour so it doesn't flash and go away
- querySelector
  - the '#'in the querySelector is used with ids
  - the '.' in the querySelector is used with CSS custom rule names


```javascript

//Example 1:
const btn = document. querySelector('.btn');
btm.addEventListener('click', (e) => { //(e) is the event object
  e.preventDefault(); //prevent the default behaviour so it doesn't flash and go away
  console.log(e);
});

//Example 2: making UI interactive
const btn = document. querySelector('.btn');
btm.addEventListener('mouseover', (e) => { //(e) is the event object
  e.preventDefault();
  document.querySelector('#my-form').style.background= '#ccc';
  document.querySelector('body').classList.add('bg-dark');
});

```

```javascript
//Real World Example:
const myForm = document.querySelector('#my-form');
const nameInput = document.querySelector('#name');
const emailInput = document.querySelector('#email');
const msg = document.querySelector('.msg');
const userList = document.querySelector('#users');

myForm.addEventListener('submit', onSubmit);

function onSubmit(e) {
  e.preventDefault();

  //Managing cases where both fields are not filled
  if(nameInput.value === '' || emailInput.value === ''){
    // alert('Please enter fields');
    msg.innerHTML = 'Please enter all fields'
    setTimeout(() => msq.remove(), 3000); //Is removed after 3 secs 
  } else{ //Adding 
    const li = document.createElement('li');
    li.appendChild(document.createTextNode(`${nameInput.value} : ${emailInput.value}`));

    userList.appendChild(li);

    //Clear fields
    nameInput.value = '';
    emailInput.value= '';
  }
}
```
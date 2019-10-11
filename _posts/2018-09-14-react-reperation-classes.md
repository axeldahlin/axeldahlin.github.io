---
layout: post
title:  "React preparation: Classes"
date:   2018-09-14 20:01:19 +0100
categories: ["react", "javascript"]
tags: ["react", "javascript"]
permalink: /:categories/:title
---
React apps are typically built with the latest JavaScript syntax so knowing it is essential.  It also lets us write clean and good looking code.

Classes is one such next generation feature that was introduced in ECMAScript 2015.

You could say that a class is a blueprint for a JavaScript objects. Classes are created with the class key word and can have methods and properties. When we create a new objects using a class we do that with the new key word.
```
class Dog {
  constructor(color) {
    this.fur = 'fluffy';
  }
  sound() {
    console.log('Bark!');
  }
}

let fido = new Dog;
fido.sound();
console.log(fido.fur);

// Logs:
// Bark!
// fluffy
```
Properties is basically variables attached to classes. And methods is basically functions attached to classes. We can access these methods and variables like in the example above.

Classes is a core feature of React. In reacts we build apps out of components. These component is either a class or a function.

Classes can inherit methods and properties it extends from another class. The extended class is called a subclass. This concept is important in React. When you define a React component you extend you class from React.Component. This gives your class access to essential React methods.

Here is an example of how a subclass inherits methods and properties from another class:
```
class Animal {
  constructor() {
    this.eyeCount = 2;
  }
  bathe () {
    console.log(this.name + ' took a swim!')
    this.fur = 'wet';
  }
}

class Dog extends Animal {
  constructor() {
    super();
    this.fur = 'fluffy';
    this.name = 'Fido'
  }
  sound() {
    console.log( this.name + ' says: Bark!');
  }
}

let dog = new Dog;
console.log(dog.fur);
dog.bathe();
console.log(dog.fur);
console.log(dog.eyeCount);

// Logs:
// fluffy
// Fido took a swim!
// wet
// 2
```
Because the dog class extends the animal class dog have access to both the bathe() method and the eyeCount property. Even though they are never declared in the Dog class. Important to note here is that the super() method is used in the constructor in the Dog class. It executes the constructor of the parent class so that the subclass have access to it too.

ES7 syntax of properties and classes used in React
The next generation JavaScript offers a cleaner syntax for initializing properties and classes. It is this new syntax that is used when building React apps.

### Initializing properties
As we saw the example above the ES6-way of writing properties is to set them up in the constructor function like this:
```
// ES6

constructor() {
  this.property = 'value'; 
}
```
The new way of doing this is to skip the constructor method completely like this:
```
// ES7

property = 'value'; 
```
### Initializing methods
Here is the old way of initializing a method in a class:
```
// ES6

method() {...}
```
And here is the new way:
```
// ES7

method = () => {...}
```
What we are basically doing is that we are storing a function in a property. And the function is an arrow function. This is important because when we are using arrow functions the this keyword will point to what we would expect it to, instead of the window/global object. The this keyword deserves its own article though.

Here is the previous example written with this new syntax:
```
class Animal {
  eyeCount = 2;
  
  bathe = () => {
    console.log(this.name + ' took a swim!')
    this.fur = 'wet';
  }
}

class Dog extends Animal {
   fur = 'fluffy';
   name = 'Fido'
  
  sound = () => {
    console.log( this.name + ' says: Bark!');
  }
}
```
### Wrap up
This new syntax is really cool. But it important to point out that it we can not just run it in the browser. Before we to that we need to compile it into the old way of writing JavaScript. We do that using Babel. Luckily that is taken care of for us when we create a React app. But it important to know that that is whats happening behind the scenes.